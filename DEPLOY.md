# Deploy Portfolio

Static site folder: everything inside `website/` (~28 MB, includes videos).

Live URL examples after deploy:
- `https://YOUR_USERNAME.github.io/portfolio/`
- `https://your-name.netlify.app`

---

## Option 1 — Netlify Drop (fastest, no Git)

1. Open https://app.netlify.com/drop
2. Drag the entire `website` folder onto the page
3. Netlify gives you a URL like `https://random-name.netlify.app`
4. (Optional) Site settings → Domain management → change site name

**Pros:** 2 minutes, no command line  
**Cons:** Manual re-upload when you update files

---

## Option 2 — GitHub Pages (recommended for developers)

### Step 1 — Create repo

1. GitHub → New repository → name: `portfolio` (public)
2. Do **not** add README if you push from local

### Step 2 — Push only the `website` folder

In PowerShell:

```powershell
cd d:\Projects\Portfolio\website

git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/portfolio.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your GitHub username.

### Step 3 — Enable Pages

1. Repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` → folder `/ (root)` → Save
4. Wait 1–3 minutes

Site URL: `https://YOUR_USERNAME.github.io/portfolio/`

### Updates later

```powershell
cd d:\Projects\Portfolio\website
git add .
git commit -m "Update portfolio"
git push
```

---

## Option 3 — Cloudflare Pages

1. https://dash.cloudflare.com → Workers & Pages → Create → Pages
2. Connect GitHub repo (same as Option 2) or **Direct Upload** the `website` folder
3. Build command: leave empty | Output directory: `/`

---

## Before every deploy — checklist

- [ ] Test locally: `python -m http.server 8080` in `website/`
- [ ] Videos play under `assets/videos/`
- [ ] CV opens from Download CV button
- [ ] Google Play links work

---

## Optional — custom domain

Buy a domain (Namecheap, Cloudflare, etc.) then point DNS to GitHub Pages or Netlify (they show exact records in dashboard).

Example: `duchanhdev.com` → CNAME to `YOUR_USERNAME.github.io`

---

## Do NOT upload

The Unity project folders (`master-num-match`, `Jigsnap-Collections`, `Dropthecat`) are huge — only deploy the `website/` folder.
