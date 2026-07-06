# AGENTS.md

## Cursor Cloud specific instructions

This repository is a single, self-contained **static website**: `index.html` (all markup, inline CSS, and inline vanilla JS) plus the `images/` folder. It is deployed to GitHub Pages via `.github/workflows/deploy-pages.yml`.

- **No dependencies / no build step / no package manager.** There is nothing to install and nothing to compile. There is no lint or automated test suite.
- **Run it (dev):** serve the repo root over HTTP, e.g. `python3 -m http.server 8000` from `/workspace`, then open `http://localhost:8000/`. Opening `index.html` as a `file://` URL mostly works too, but a static server best matches GitHub Pages behavior.
- **Internet access is needed for full styling.** Tailwind CSS (`cdn.tailwindcss.com`) and Google Fonts (`fonts.googleapis.com`, `fonts.gstatic.com`) load from CDNs at runtime. Without network access the page still renders but is largely unstyled.
- **Core interactive features** (all inline JS in `index.html`): the EN/AR language toggle (`data-translate-key` dictionary, includes RTL) and the image lightbox. Verify these when changing markup or the inline script.
