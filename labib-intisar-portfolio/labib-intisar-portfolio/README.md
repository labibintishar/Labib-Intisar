# Labib Intisar — Portfolio

A single-page academic portfolio for **Labib Intisar**, Urban &amp; Regional Planning graduate (RUET), focused on sustainable development, geospatial modeling, and disaster-risk research.

Built as a self-contained static site: one `index.html`, a folder of assets, and no build step. It uses a tasteful 3D hero terrain and an animated GIS layer-stack (Three.js), an interactive study-area map (Leaflet + OpenStreetMap), scroll animations, a custom reticle cursor, downloadable CV, and certificate previews.

## Folder structure

```
.
├── index.html          ← the whole site
├── .nojekyll           ← tells GitHub Pages to serve files as-is
├── README.md
└── assets/
    ├── favicon.svg
    ├── share-card.png                              ← social link-preview image
    ├── labib-intisar.jpg                           ← portrait
    ├── Labib-Intisar-CV.pdf                         ← downloadable CV
    ├── cert-gis-climate-action.jpg                  ← certificate preview (lightbox)
    ├── cert-core-humanitarian.jpg                   ← certificate preview (lightbox)
    ├── certificate-gis-climate-action.pdf           ← certificate download
    └── certificate-core-humanitarian-standard.pdf   ← certificate download
```

## Deploy on GitHub Pages

1. Create a new repository on GitHub (e.g. `portfolio`). To serve it at `https://<username>.github.io/` instead of a sub-path, name the repo exactly `<username>.github.io`.
2. Upload **everything in this folder** (the `index.html`, `assets/` folder, `.nojekyll`, and `README.md`) to the repository — keep the structure intact.
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**, select the `main` branch and the `/ (root)` folder, then **Save**.
5. Wait ~1 minute. Your site will be live at `https://<username>.github.io/` (or `.../<repo-name>/` for a project repo).

> Tip: the `.nojekyll` file is already included so GitHub Pages serves the files exactly as they are.

## Local preview

Open `index.html` in a browser, or run a tiny local server from this folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

An internet connection is needed for the web fonts, the 3D scenes (Three.js), and the map tiles (Leaflet / OpenStreetMap), which load from public CDNs.

## Updating content

Everything lives in `index.html`:

- **Text, education, publications, certifications** — edit the relevant `<section>` directly.
- **Publication links** — the `href` on each `ResearchGate ↗` link.
- **Map study sites** — the `var sites = [ ... ]` array inside the `<script>` near the bottom.
- **Swap a photo / CV / certificate** — replace the file in `assets/` (keep the same filename), or change the filename and update its reference in `index.html`.

## Social link previews

`index.html` points `og:image` / `twitter:image` at `assets/share-card.png` (relative). Most platforms render this once the site is live. For the most reliable previews, change those two tags to the full URL after deploying, e.g.:

```html
<meta property="og:image" content="https://<username>.github.io/assets/share-card.png" />
<meta name="twitter:image" content="https://<username>.github.io/assets/share-card.png" />
```

---

© Labib Intisar. Site content, CV, photo, and certificates are personal and not licensed for reuse.
