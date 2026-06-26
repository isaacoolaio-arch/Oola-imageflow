# ImageFlow Pro — PWA Image Editor & Compressor

A fully offline-capable PWA for editing, compressing, and processing images. No backend, no API keys, no server needed.

## Features

- **Magic Wand Background Remover** — click to remove backgrounds using flood-fill with tolerance control
- **Background Changer** — solid color, gradient, custom image, blur, or pattern
- **Full Editor** — brightness, contrast, saturation, blur, filters, rotate, flip, draw, text overlay, watermark
- **Bulk Compress** — process all images at once with presets, download as ZIP
- **Fully offline** — works without internet after first load
- **Installable** — add to home screen on mobile or desktop

## File Structure

```
imageflow-pwa/
├── index.html          # Main app shell
├── manifest.json       # PWA manifest
├── sw.js               # Service worker (offline)
├── css/
│   └── style.css       # All styles
├── js/
│   ├── app.js          # All app logic
│   └── jszip.min.js    # ZIP download library
├── icons/
│   ├── icon-192.png    # App icon
│   └── icon-512.png    # App icon
└── .github/
    └── workflows/
        └── deploy.yml  # Auto-deploy to GitHub Pages
```

## Deploy to GitHub Pages

### Option 1 — GitHub Actions (recommended, auto-deploys on push)

1. Create a new GitHub repo (e.g. `imageflow-pwa`)
2. Push all files:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/YOUR_USERNAME/imageflow-pwa.git
   git push -u origin main
   ```
3. Go to repo **Settings → Pages → Source** → select **GitHub Actions**
4. Your app will be live at `https://YOUR_USERNAME.github.io/imageflow-pwa/`

### Option 2 — Manual GitHub Pages

1. Push files to your repo
2. Go to **Settings → Pages → Source** → select **Deploy from branch → main → / (root)**
3. Done — live in ~2 minutes

## Usage

### Background Removal
1. Open an image
2. Click the 🪄 **Magic Wand** tool in the editor toolbar
3. Click on the background area you want to remove
4. Adjust **Tolerance** (higher = removes more similar colors)
5. Click multiple spots to remove more areas
6. Use **Background Changer** panel to add a new background

### Bulk Compression
1. Add multiple images
2. Go to **Bulk** tab
3. Choose preset or set custom width/quality/format
4. Click **Process all** → **ZIP download**

## Tips

- **For product photos** (white/plain backgrounds): tolerance 20–40 works well
- **For complex backgrounds**: use lower tolerance and click multiple areas
- **Export as PNG** when background is transparent, WebP for best compression
- The app caches itself after first load — works fully offline
