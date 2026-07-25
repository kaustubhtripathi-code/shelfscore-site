# HANDOVER — shelfscore-site

Marketing site for **ShelfScore** (ex-NutriScan, the Android food-scanner at
`C:\dev\NutriScan` — read ITS HANDOVER.md for product state). `index.html` + `privacy.html`
(privacy policy added 07-10, linked from footer).

- Repo: `kaustubhtripathi-code/shelfscore-site` · GitHub Pages
  (https://kaustubhtripathi-code.github.io/shelfscore-site/).
- Redeploy = push to default branch.
- The privacy policy page backs the app's store/privacy claims — if data handling in the
  app changes, update `privacy.html` in the SAME change.
- User steps: none pending for the site.

Last audit: 2026-07-12 (state = last commit `718a215`, 2026-07-10).

## 2026-07-25 responsive audit
Audited at 375 / 820 / 1280 in the 7-site pass — **clean, no defects found**: no horizontal
overflow, no dead CTAs, no nav to lose (single-page, no nav bar), grades encoded by letter
*and* colour rather than colour alone. Only change: added `color-scheme:dark` so Windows
renders form controls and scrollbars correctly on the dark background.
