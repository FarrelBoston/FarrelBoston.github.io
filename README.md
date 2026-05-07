# Farrel Brest — PMM Portfolio

A clean, fast, static portfolio built for GitHub Pages.
No build tools. No frameworks. Just HTML, CSS, and a JSON data file.

---

## File Structure

```
/
├── index.html       ← Main page (hero + nav + grid + about + footer)
├── styles.css       ← All styles and responsive layout
├── projects.json    ← All your project data (edit this to update content)
└── README.md        ← This file
```

---

## Deploy to GitHub Pages (5 minutes)

### Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) and log in (or create a free account).
2. Click **New repository**.
3. Name it exactly: `YOUR-USERNAME.github.io` (replace `YOUR-USERNAME` with your GitHub username).
4. Set visibility to **Public**.
5. Click **Create repository**.

### Step 2 — Upload your files

**Option A — GitHub web UI (easiest):**

1. Open your new repository.
2. Click **Add file → Upload files**.
3. Drag in all 4 files: `index.html`, `styles.css`, `projects.json`, `README.md`.
4. Click **Commit changes**.

**Option B — Git CLI:**

```bash
git init
git add .
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. In your repository, go to **Settings → Pages**.
2. Under **Source**, select **Deploy from a branch**.
3. Choose branch: `main` | folder: `/ (root)`.
4. Click **Save**.

Your site will be live at `https://YOUR-USERNAME.github.io` within 1–2 minutes.

---

## Update Your Content

### Add a new project

Open `projects.json` and add a new object to the array:

```json
{
  "id": 8,
  "title": "Your Project Title",
  "company": "Company Name",
  "tagline": "Short punchy tagline.",
  "metric": "Full metric description",
  "metricShort": "Short stat for card",
  "description": "1-2 sentences describing what you did and the outcome.",
  "tags": ["GTM", "Messaging"],
  "ctas": [
    { "label": "See the work", "url": "https://your-link.com", "primary": true }
  ]
}
```

### Update an existing project

Find the matching object by `"id"` in `projects.json` and edit the fields.

### Add real CTA links

Replace the `"url": "#"` placeholders in each project's `"ctas"` array with your actual URLs.

### Update your name / contact links

Open `index.html` and search for the following comments to find the right spots:

- `<!-- Replace # with your LinkedIn URL -->` — nav LinkedIn link
- `<!-- Replace # with real URLs -->` — footer links
- `<a href="mailto:your@email.com">` — footer email

---

## Customisation Tips

### Change the color scheme

All colors are CSS variables in `styles.css`. Edit the `:root` block at the top:

```css
:root {
  --navy:       #0f1629;   /* page background */
  --blue:       #2563eb;   /* primary accent */
  --blue-light: #3b82f6;   /* hover accent */
  /* ... */
}
```

### Change fonts

Fonts are loaded via Google Fonts at the top of `styles.css`:

```css
@import url('https://fonts.googleapis.com/css2?family=Fraunces...');
```

Replace with any Google Fonts URL. Then update the `--font-display` and `--font-body` variables.

### Add a profile photo

Inside `index.html`, find the `about-inner` div and add an `<img>` tag:

```html
<img src="photo.jpg" alt="Farrel Brest" style="border-radius: 12px; width: 100%; max-width: 320px;" />
```

Upload `photo.jpg` to your GitHub repo alongside the other files.

---

## Performance Notes

- **No JavaScript frameworks** — page loads in under 0.5s on most connections.
- **Google Fonts** are the only external dependency; they load asynchronously.
- **No images by default** — add your own without worrying about optimization (keep under 200KB per image).
- **Fully responsive** — 1 column on mobile, 2 on tablet, 3 on desktop.

---

## Common Issues

| Problem | Fix |
|---|---|
| Page not loading after deploy | Wait 2–3 min; check Settings → Pages is set to `main` branch |
| Cards not appearing | Make sure `projects.json` is in the same folder as `index.html` |
| Fonts not loading | Check internet connection; fonts load from Google CDN |
| Changes not showing | Hard refresh (`Ctrl+Shift+R` / `Cmd+Shift+R`) or wait for GitHub cache |

---

Built with HTML + CSS + vanilla JS. Hosted free on GitHub Pages.
