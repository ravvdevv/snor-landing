# Claude Code instructions

This repository is the static Snor landing site. Follow the repository-wide instructions in `AGENTS.md`.

Before changing release metadata, publishing APKs, or deploying the site, read `deployment.md` and follow its checklist. The site is deployed by Vercel from `main`; Android APKs are distributed through this repository's GitHub Releases, not committed to Git.

Keep `index.html`, `README.md`, and `llms.txt` aligned with the current release. Verify release assets, checksums, and the production deployment before reporting success. Preserve unrelated changes and never commit secrets or signing material.
