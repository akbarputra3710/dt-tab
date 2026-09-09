# Quick Links

A single-page static site — a personal dashboard of bookmarked tools, grouped
into sections (Email, Repository, Design, AI tools, Testing, etc.). Pure
HTML/CSS/JS, no build step, no dependencies.

## Files

- `index.html` — the entire site (structure, styles, and link data are all in this one file)
- `vercel.json` — tells Vercel this is a plain static site
- `netlify.toml` — tells Netlify this is a plain static site
- `.gitignore` — keeps local tool folders (`.vercel`, `.netlify`, etc.) out of git

## 1. Push to GitHub (Git Bash)

Open Git Bash inside this folder and run:

```bash
git init
git add .
git commit -m "Initial commit: quick links dashboard"
git branch -M main
```

Create an empty repo on GitHub first (no README/license, so it stays empty),
then link and push it — replace `YOUR-USERNAME` and `YOUR-REPO`:

```bash
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

If Git Bash asks for credentials, use a GitHub Personal Access Token as the
password (GitHub no longer accepts account passwords over HTTPS git operations).

## 2. Deploy to Vercel

**Option A — Vercel dashboard (easiest):**
1. Go to https://vercel.com/new
2. Import the GitHub repo you just pushed
3. Framework preset: "Other" (it's plain static HTML, no build needed)
4. Click Deploy

**Option B — Vercel CLI (from Git Bash):**
```bash
npm install -g vercel
vercel login
vercel --prod
```

## 3. Deploy to Netlify

**Option A — Netlify dashboard (easiest):**
1. Go to https://app.netlify.com/start
2. Choose "Import from Git" and select your GitHub repo
3. Build command: leave blank
4. Publish directory: `.`
5. Click Deploy site

**Option B — Netlify CLI (from Git Bash):**
```bash
npm install -g netlify-cli
netlify login
netlify deploy --prod
```

## Updating the site later

Edit the `data` array at the top of the `<script>` block in `index.html` to
add, remove, or reorder links and sections. Then:

```bash
git add .
git commit -m "Update links"
git push
```

Both Vercel and Netlify auto-redeploy on every push to `main` once connected
to the GitHub repo.
