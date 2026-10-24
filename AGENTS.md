# Repository instructions

- Read `deployment.md` before any release, download-link update, or deployment work.
- This is a static HTML/CSS/JavaScript site. Do not introduce a build system or dependencies for routine content edits.
- The production site is hosted on Vercel from `main`; APK files belong in GitHub Release assets, never in Git history.
- Keep the homepage, `README.md`, `llms.txt`, JSON-LD version metadata, and release asset names in sync.
- Use Markdown notes files for GitHub release descriptions. Never pass literal escaped newline sequences as release-note content.
- Verify asset URLs and SHA-256 values before publishing. Do not claim physical-device/model testing that did not happen.
- Preserve unrelated changes and local-only files. Never expose or commit credentials, signing keys, or keystores.
- Run `git diff --check` and inspect the final diff before committing. Verify the Vercel production deployment after pushing.
