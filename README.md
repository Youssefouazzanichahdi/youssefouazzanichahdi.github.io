# Academic site — Youssef Ouazzani Chahdi

A clean, static academic homepage with a persistent left sidebar (photo, identity, nav, links)
and content on the right. No build step, no dependencies — just HTML and CSS. Edit and push.

## Files

```
├── index.html          # Homepage (about, news, selected pubs)
├── publications.html   # Full publication list
├── teaching.html       # Courses and supervised students
├── talks.html          # Talks and conferences
├── assets/
│   ├── style.css       # All styling (one file, commented, CSS variables)
│   └── photo.jpg       # Portrait (shown cropped to a portrait frame)
├── papers/
│   └── cv.pdf          # CV
└── googlee81a4979ba22bfc9.html   # Google Search Console verification
```

## Deploying to GitHub Pages

Your site will be live at `https://yourusername.github.io`.

1. On GitHub, create a **public** repo named exactly `yourusername.github.io`.
2. From inside this folder, push the files:

```bash
git init
git add .
git commit -m "Sidebar redesign"
git branch -M main
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

3. For `username.github.io` repos, Pages turns on automatically. To verify: **Settings → Pages**,
   source **Deploy from a branch**, branch **main**, folder `/ (root)`. Live within 1–2 minutes.

Every push to `main` updates the site.

Local preview before pushing:
```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Editing

- **Photo** — replace `assets/photo.jpg`. It's displayed in a 4:5 portrait frame. If your face
  ends up off-centre, tweak `object-position` in `.photo img` (in `assets/style.css`).
- **Contact / Scholar links** — in the `.contact` block near the top of each HTML file.
- **CV** — replace `papers/cv.pdf`.
- **Adding a paper** — in `publications.html`, copy any `<li>` inside `.pub-list` and edit the
  title, authors, and venue. The `value="N"` attribute sets the printed number.

## Retheming

Everything lives in `:root` at the top of `assets/style.css`:

- `--accent` — the oxblood accent (links, active nav, section labels). Swap this one value to
  recolour the whole site.
- `--sidebar-w` / `--content-w` — layout widths.
- Fonts: **Inter** (body/UI) + **JetBrains Mono** (dates, labels), loaded from Google Fonts.
  Swap the `<link>` in each file's `<head>` and the `--sans` / `--mono` variables to change them.

## Why this stack

- No Jekyll, no Hugo, no build step. Faster to edit, nothing to break.
- No JavaScript framework. Loads instantly, will still work in ten years.
- Two Google fonts. One ~350-line CSS file, fully commented, driven by CSS variables.
