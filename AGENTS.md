# AGENTS.md — shelfscore-site

Public marketing site for **ShelfScore** (formerly NutriScan), the owner's Android food-scanner
app (app code is in the separate `shelfscore` repo). Two pages: landing + privacy policy.
Live on GitHub Pages; low-churn. **PUBLIC repo.**

## Stack & layout
Plain static HTML, no build step.
- `index.html`: single-page landing (no nav bar); `privacy.html`: privacy policy linked from the footer
- `assets/` (og-image, promo mp4); `ci/site_check.py`: CI link/asset checker and stager

## Setup
None. Needs `python3` (3.12+) and `node` (checker runs `node --check` on any JS files).

## Run / build / test / lint
- Preview: `python3 -m http.server 8000` (unverified)
- Check (what CI runs; stage outside the repo so no `_site/` is created):
  `python3 ci/site_check.py --repo shelfscore-site --output /tmp/shelfscore-site-_site` (verified 2026-10-11).
  It refuses an existing output dir; delete it before re-running. Never commit `_site/`.

## Environment variables
None required.

## Codex cloud environment
- Setup script: `python3 --version && node --version` (nothing to install)
- Internet during agent phase: off is fine
- Secrets to add: none

## Deployment (do not break)
- GitHub Pages, default branch is **`master`**: https://kaustubhtripathi-code.github.io/shelfscore-site/
- `.github/workflows/ci-cd.yml` checks every push/PR and deploys with `actions/deploy-pages`
  only from `master`. A push to `master` = live. Do not push to `master` without owner
  approval; use a branch + PR. Do not edit the workflow or `ci/` unless asked.

## Rules for agents
- `privacy.html` backs the app's store/privacy claims. If the app's data handling changes,
  update `privacy.html` in the same change; never weaken or contradict it casually.
- Health grades are encoded by letter **and** colour (traffic-light semantic colours are
  intentional and must not be rebranded to house colours).
- Keep `color-scheme:dark`; the page was audited clean at 375/820/1280 px, so check those widths after layout edits.

## Open work
- None pending. `ci/portfolio-20260907` is already merged into `master`.
