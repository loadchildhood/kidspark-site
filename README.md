# KidSpark — Complete Setup Guide

Everything you need to get KidSpark live on GitHub Pages and submitted to the Google Play Store.

---

## Step 1 — Generate Your Icons (do this FIRST)

Open `icon-gen.html` in your browser (just double-click the file).
- Click **Download icon-512.png** → save to `icons/` folder
- Click **Download icon-192.png** → save to `icons/` folder

These PNG files are required by both the PWA manifest and Google Play.

---

## Step 2 — Deploy to GitHub Pages

### 2a. Create a GitHub repository
1. Go to **github.com** and sign in
2. Click **+** → **New repository**
3. Name it: `kidspark-site`
4. Set to **Public** → click **Create repository**

### 2b. Upload files
**Easiest way — drag & drop:**
- Open the repo on GitHub
- Click **Add file → Upload files**
- Drag the entire `kidspark-site/` folder contents into the box
- Click **Commit changes**

**OR via terminal:**
```bash
cd /home/m/Documents/stock_research/kidspark-site
git init
git add .
git commit -m "Launch KidSpark site"
git remote add origin https://github.com/loadchildhood/kidspark-site.git
git branch -M main
git push -u origin main
```

### 2c. Enable GitHub Pages
1. In your repo, click **Settings** tab
2. Click **Pages** in the left sidebar
3. Under **Source**: select **Deploy from a branch**
4. Branch: `main`, Folder: `/ (root)` → click **Save**
5. Wait ~2 minutes → your site is live at:
   `https://loadchildhood.github.io/kidspark-site/`

---

## Step 3 — Convert to Android App with PWABuilder

PWABuilder turns your hosted website into a Google Play APK for free.

1. Go to **pwabuilder.com**
2. Enter your GitHub Pages URL:
   `https://loadchildhood.github.io/kidspark-site/`
3. Click **Start** — it will score your PWA (aim for 100/100)
4. Click **Build My PWA**
5. Select **Android** → click **Generate**
6. Download the `.zip` package — it contains your signed AAB file

**If your score is below 100:**
- Make sure `manifest.json` and `sw.js` are uploaded
- Make sure `icon-192.png` and `icon-512.png` are in the `icons/` folder
- Verify the site loads over HTTPS (GitHub Pages does this automatically)

---

## Step 4 — Create a Google Play Developer Account

1. Go to **play.google.com/console/signup**
2. Sign in with your Google account
3. Pay the **$25 one-time registration fee**
4. Fill in your developer profile:
   - **Developer name:** KidSpark
   - **Email:** your contact email
   - **Website:** `https://loadchildhood.github.io/kidspark-site/`
5. Accept the Developer Distribution Agreement
6. Wait up to 48 hours for account verification

---

## Step 5 — Create Your App Listing

Once your account is active:

1. In Play Console, click **Create app**
2. Fill in:
   - **App name:** KidSpark — Games That Teach
   - **Default language:** English (United States)
   - **App or game:** Game
   - **Free or paid:** Free
3. Click **Create**

### App content setup
Go through each required section in the left menu:

| Section | What to do |
|---------|-----------|
| **App access** | All functionality is available without special access |
| **Ads** | Does not contain ads |
| **Content ratings** | Complete the IARC questionnaire (see store-listings.md) |
| **Target audience** | Ages 5 and up; designed for children |
| **Privacy policy** | `https://loadchildhood.github.io/kidspark-site/privacy.html` |

### Store listing
Copy from `store-listings.md`:
- Title, short description, full description
- Upload screenshots (at least 2 phone screenshots)
- Upload Feature Graphic (1024×500 PNG)

### Icons
- **Hi-res icon:** `icons/icon-512.png` (512×512 PNG)

---

## Step 6 — Upload Your App

1. In Play Console, go to **Release → Production → Create new release**
2. Upload the `.aab` file from the PWABuilder zip
3. Fill in the release notes: "Initial release of KidSpark"
4. Click **Save → Review release → Start rollout**

Google reviews new apps in **3–7 business days**.

---

## File Structure

```
kidspark-site/
├── index.html          Main showcase + hub page
├── manifest.json       PWA manifest
├── sw.js               Service worker (offline support)
├── privacy.html        Privacy policy page
├── icon-gen.html       Open in browser to generate PNG icons
├── store-listings.md   Copy-paste text for Play Store
├── README.md           This guide
├── icons/
│   ├── icon.svg        Vector icon (source)
│   ├── icon-192.png    ← generate with icon-gen.html
│   └── icon-512.png    ← generate with icon-gen.html
├── screenshots/        Put screenshot PNGs here
└── games/
    ├── glacier.html    ❄️ Glacier Gauntlet
    ├── orbit.html      🪐 Orbit
    ├── dropstack.html  🔥 Drop Stack 3D
    └── sunset.html     🌅 Sunset Glow
```

---

## Quick Checklist Before Submitting

- [ ] Icons generated and saved to `icons/` folder
- [ ] Site pushed to GitHub Pages and loading correctly
- [ ] All 4 game "Play Now" buttons work
- [ ] Privacy policy page loads at `/privacy.html`
- [ ] PWABuilder score is 100 (or close)
- [ ] AAB file downloaded from PWABuilder
- [ ] Google Play developer account ($25) activated
- [ ] Content rating questionnaire completed
- [ ] At least 2 phone screenshots uploaded
- [ ] Feature graphic (1024×500) uploaded
- [ ] Privacy policy URL entered in Play Console

---

## Update Your URLs

Replace `loadchildhood` with your actual GitHub username everywhere:
- In `README.md`
- In `store-listings.md` (developer website + privacy policy URL)
- In Play Console listing
