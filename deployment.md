# Snor Landing Deployment and Release Guide

This repository contains the static marketing site for Snor. The site is hosted on Vercel at https://www.snor.site/; APK binaries are distributed as GitHub Release assets in this repository. Do not commit APK binaries or signing keys to Git.

## Deployment model

- **Website:** Vercel project `snor-landing`, connected to this GitHub repository.
- **Production branch:** `main`. Pushing a reviewed commit to `main` triggers Vercel's Git integration.
- **Release downloads:** GitHub Releases at https://github.com/ravvdevv/snor-landing/releases.
- **Application source/build:** the separate `ravvdevv/snor` repository. Confirm its version and release assets before updating this site.

## Publishing a new Android release

1. Confirm the app version in `pubspec.yaml` in the Snor app repository and confirm the matching Git tag/release is intended.
2. Build architecture-specific APKs from the app repository:

   ```bash
   flutter pub get
   flutter test
   flutter build apk --release --split-per-abi
   ```

   Expected outputs are `app-armeabi-v7a-release.apk`, `app-arm64-v8a-release.apk`, and `app-x86_64-release.apk` under `build/app/outputs/flutter-apk/`. Do not claim a model works on physical devices unless it was actually tested there.

3. Calculate SHA-256 hashes for every APK and record them in the release notes. Keep a checksum manifest alongside each APK when possible:

   ```bash
   sha256sum app-arm64-v8a-release.apk
   sha256sum app-armeabi-v7a-release.apk
   sha256sum app-x86_64-release.apk
   ```

4. Create a GitHub Release in **this** repository using the exact app version tag, e.g. `v1.0.8`. Attach all available ABI APKs. Also attach the ARM64 APK as `snor-vVERSION.apk` (e.g. `snor-v1.0.8.apk`) because the landing page uses this stable, versioned filename. Avoid duplicate asset names.
5. Write release notes in a Markdown file and pass it with `gh release create ... --notes-file notes.md`. For edits, use `gh release edit TAG --notes-file notes.md`. **Do not** pass escaped `\n` sequences inside a quoted `--notes` argument; they can appear literally in the published release description.
6. Update the release version and download links in all relevant places:
   - `index.html`: SoftwareApplication `softwareVersion`, download/install URLs, version label, file size if changed, and short release summary.
   - `README.md`: current version and download information.
   - `llms.txt`: current version and versioned download URL.
7. Check that every URL points to an asset that exists on the new release. Confirm the release tag is marked latest, verify SHA-256 hashes, and inspect the rendered release body for literal escape sequences or malformed Markdown.
8. Run the local checks below, commit the website/documentation changes, and push to `main`. Wait for the Vercel production deployment to finish before claiming the site is live.

## Website checks

This is a static site; there is no package build step. At minimum:

```bash
git diff --check
python -m http.server 8000
```

Inspect the site locally at `http://localhost:8000`, especially the hero and download sections. Also check JSON-LD for the current version, links, and file size; confirm `sitemap.xml`, `robots.txt`, and `llms.txt` remain valid. Stop the local server after checking.

After pushing to `main`, verify the production deployment in the Vercel dashboard or with the authenticated Vercel CLI, and check the live homepage and download links. Use a manual `vercel --prod` only if the Git integration did not deploy and the CLI is linked to the correct `snor-landing` project. Never guess a project ID or deploy an unrelated directory.

## Safety and release hygiene

- Never commit `.env` files, access tokens, signing keys, keystores, or private credentials.
- Do not overwrite an existing release tag or asset silently. Inspect the current release first.
- Preserve unrelated working-tree changes and generated/local-only files.
- If only a universal APK is available, describe it accurately; do not label it ARM64-only.
- Do not claim that a release is deployed until GitHub release assets and the Vercel production deployment have both been verified.
