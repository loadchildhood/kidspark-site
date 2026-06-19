# Deploying KidSpark to GitHub Pages

## Steps (takes ~5 minutes)

### 1. Create a GitHub repo
- Go to github.com → click **+** → **New repository**
- Name it exactly: `kidspark-site` (or `yourusername.github.io` for a root domain)
- Set it to **Public**
- Click **Create repository**

### 2. Upload the file
**Option A — drag &amp; drop (easiest):**
- Open the repo on GitHub
- Click **Add file → Upload files**
- Drag `index.html` into the box → click **Commit changes**

**Option B — via terminal:**
```bash
cd /home/m/Documents/stock_research/kidspark-site
git init
git add index.html
git commit -m "Launch KidSpark site"
git remote add origin https://github.com/loadchildhood/kidspark-site.git
git push -u origin main
```

### 3. Enable GitHub Pages
- In the repo, go to **Settings → Pages**
- Under **Source**, select **Deploy from a branch**
- Branch: `main`, folder: `/ (root)` → click **Save**
- Wait 1–2 minutes — your site will be live at:
  `https://loadchildhood.github.io/kidspark-site/`

### 4. Custom domain (optional)
- Buy a domain (e.g. `kidspark.app`) from Namecheap or Google Domains
- In **Settings → Pages → Custom domain**, enter your domain
- Add a CNAME record in your DNS pointing to `loadchildhood.github.io`

## Your site URL
`https://loadchildhood.github.io/kidspark-site/`

Replace loadchildhood with your actual GitHub username.
