# StoryStem — GitHub Pages Site

Single-page website for [StoryStem](https://github.com/yourusername/storystem-website).

## Deploy to GitHub Pages (one-time setup)

1. Create a new repo on GitHub (e.g. `storystem-website` or use `yourusername.github.io` for a user site).

2. Push this folder:

```bash
cd storystem-website
git init
git add index.html assets/ README.md
git commit -m "Add StoryStem landing page"
git branch -M main
git remote add origin git@github.com:YOUR_USERNAME/storystem-website.git
git push -u origin main
```

3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main / (root)**.

4. Your site will be live at `https://YOUR_USERNAME.github.io/storystem-website/` (or `https://YOUR_USERNAME.github.io/` if using a user site repo).

## Before you go live

Update these Gumroad URLs in `index.html` (search for `gumroad.com`):

- **Kit listing:** `https://storystem.gumroad.com/l/matatu-kit`
- **48-page guide:** `https://storystem.gumroad.com/l/matatu-guide`

Replace with your actual product links once published on Gumroad.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire site (no build step) |
| `assets/matatu-hero.jpg` | Hero photo of the assembled Matatu robot |
| `assets/videos/storystem-intro.mp4` | Company intro video (About section, ~1:45) |
| `assets/videos/storystem-intro-poster.jpg` | Poster frame for company intro |
| `assets/videos/matatu-explainer.mp4` | Product explainer video (Programs section, ~1:50) |
| `assets/videos/matatu-explainer-poster.jpg` | Poster frame for product explainer |

## Video compression

Source footage from a camera/SD card should be compressed before committing. Target ~10–15 MB per file for GitHub Pages:

```bash
ffmpeg -i SOURCE.mp4 -vf scale=-2:720 -c:v libx264 -crf 28 -preset slow -c:a aac -b:a 128k assets/videos/OUTPUT.mp4
ffmpeg -ss 5 -i assets/videos/OUTPUT.mp4 -vframes 1 -q:v 2 assets/videos/OUTPUT-poster.jpg
```

Adjust `-ss` to pick a better poster frame if needed.
