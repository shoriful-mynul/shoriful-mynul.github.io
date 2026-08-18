# Shoriful Islam — Portfolio

A static, framework-free portfolio site (semantic HTML5, CSS3, vanilla JS). No build step — it runs directly on GitHub Pages.

## Structure
```
/
├── index.html
├── .nojekyll
├── css/style.css
├── js/script.js
└── assets/
    ├── images/favicon.svg
    └── resume/cv.pdf   ← add your real resume here
```

## Before you publish — things to replace
This ships with real contact info but **placeholder projects and log entries**, since none were provided in the brief. Search `index.html` for these and swap in real content:

- `#projects` — three sample cards ("Project title one/two/three") plus one empty "next up" slot. Replace title, description, tech tags, and the `href="#"` repo links.
- `#log` — the three "Currently" list items are placeholders ("Add the paper...", "Add what's on the workbench...").
- `#education` — coursework description is generic; tighten once you have more of the degree behind you.
- `assets/resume/cv.pdf` — currently empty; drop your actual CV in as `cv.pdf` (the download button already points here).

## Design notes
- **Fonts:** Fraunces (display), Inter (body), JetBrains Mono (labels/tags) — loaded from Google Fonts via `<link>` in `index.html`. No local hosting needed, but if you want to work offline or drop the external request, self-host the `.woff2` files and update the `@font-face`/`<link>` tags.
- **Colors** live as CSS custom properties at the top of `css/style.css` (`:root`) — change the palette in one place.
- **Navigation** is a fixed left "index tab" spine on desktop that collapses into a top bar with a hamburger menu under 720px. Active-section highlighting is handled by an `IntersectionObserver` in `js/script.js`.
- Motion is minimal by design and respects `prefers-reduced-motion`.

## Deploying to GitHub Pages
1. Push this folder's contents to the root of a repo (e.g. `shoriful-mynul/shoriful-mynul.github.io` for a user site, or any repo for a project site).
2. In the repo, go to **Settings → Pages**, set the source to the `main` branch, root folder.
3. The `.nojekyll` file is already included so GitHub Pages serves the files as-is (skips Jekyll processing, which matters since none of the folders start with `_`, but it's good practice regardless).
4. Wait a minute or two, then visit the URL GitHub Pages gives you.

## Local preview
No build tools required. Either open `index.html` directly in a browser, or serve it locally to avoid any `file://` quirks:
```bash
python3 -m http.server 8000
```
Then visit `http://localhost:8000`.
