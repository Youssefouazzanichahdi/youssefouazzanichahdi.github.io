# Your Academic Site

A clean, static academic homepage. No build step, no dependencies — just HTML and CSS. Edit and push.

## Files

```
├── index.html          # Homepage (about, news, selected pubs)
├── publications.html   # Full publication list
├── teaching.html       # Courses and supervised students
├── talks.html          # Talks and conferences
├── notes.html          # Blog / informal writing
├── assets/
│   ├── style.css       # All styling (one file, well-commented)
│   └── photo.jpg       # Your portrait (replace this)
└── papers/
    └── cv.pdf          # Your CV (replace this)
```

## Deploying to GitHub Pages

Three steps. Your site will be live at `https://yourusername.github.io`.

### 1. Create the repository

On GitHub, create a new **public** repository named exactly `yourusername.github.io` — replace `yourusername` with your actual GitHub username. The name must match this pattern; that's how GitHub Pages recognizes it as your personal site and serves it from the root.

Leave it empty — don't initialize with a README, since we already have files to push.

### 2. Push the files

In a terminal, from inside the `academic-site` folder:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

(Use `git@github.com:...` instead of `https://...` if you have SSH keys set up.)

### 3. Enable Pages (usually automatic)

For repos named `username.github.io`, GitHub Pages turns on automatically. To verify:

- Go to your repo on GitHub.
- Click **Settings → Pages** (in the left sidebar).
- Under **Build and deployment**, source should be **Deploy from a branch**, branch **main**, folder `/ (root)`.

Within 1–2 minutes, your site is live at `https://yourusername.github.io`.

That's it. Every time you push a commit to `main`, the site updates automatically.

### Later: adding a custom domain (optional)

If you ever want a friendlier URL like `yourname.com` instead of `yourusername.github.io`, you can buy a domain (~$10–15/year from Namecheap, Cloudflare, Gandi, OVH, etc.) and point it at GitHub Pages in about 5 minutes. The github.io URL keeps working either way. You don't need this now — and many established academics never bother with it.

## Editing the site

Everything you need to personalize is in the HTML files. The placeholders to replace:

- `Your Name` — used in titles, headers, footers
- `Your Institution` — current affiliation
- Email, Google Scholar, arXiv, GitHub links — in the contact row in `index.html`
- Photo: drop a square-ish JPG at `assets/photo.jpg`
- CV: drop your PDF at `papers/cv.pdf`

The publication entries in `index.html` (selected) and `publications.html` (full list) are independent — keep the selected list short (3–5 papers) and the full list complete.

For local preview before pushing:
```bash
cd academic-site
python3 -m http.server 8000
# open http://localhost:8000
```

## Adding a new paper

In `publications.html`, copy any `<li>` inside `.pub-list` and edit the fields:

```html
<li>
  <span class="pub-title">Title of the paper.</span>
  <span class="pub-authors">With Coauthor.</span>
  <span class="pub-venue"><em>Venue</em>, 2026.</span>
  <span class="pub-links">
    <a href="...">arXiv</a> · <a href="...">PDF</a>
  </span>
</li>
```

The numbering is automatic (CSS counters).

## Why this stack?

- **No Jekyll, no Hugo, no build step.** Faster to edit, no toolchain to break.
- **No JavaScript framework.** Loads instantly. Will still work in ten years.
- **Two Google Fonts only** (EB Garamond + JetBrains Mono). Removable if you prefer system fonts.
- **One CSS file**, ~250 lines, fully commented and using CSS variables — easy to retheme.

If you later want a blog with markdown posts, the cleanest upgrade is to add Hugo or 11ty without changing the design. But the current setup is honestly fine forever for a research site.
