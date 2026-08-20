# Table Tennis Tournament — GitHub Pages starter

This folder is ready to upload as-is to a new GitHub repository and turn into a free public website. No server, no build step, no ongoing hosting cost — everything runs in the browser.

## What's in here

- `index.html` — landing page listing each monthly tournament, plus a link to the builder tool.
- `tool.html` — the interactive draft / schedule / scoring tool (same file shared in chat).
- `tournaments/` — where you'll drop each month's **read-only** exported snapshot.

## One-time setup (no command line needed)

1. Go to **github.com** → **New repository**. Name it something like `tt-tournament` (choose Public — GitHub Pages needs a public repo unless you're on a paid plan).
2. Open the new repo → **Add file → Upload files**. Drag in `index.html` and `tool.html` from this folder, and separately create the `tournaments` folder by uploading `tournaments/README.md` (GitHub creates the folder automatically from the file path).
3. Commit the upload (the default commit message is fine).
4. Go to **Settings → Pages**. Under "Build and deployment," set **Source: Deploy from a branch**, **Branch: main**, folder **/ (root)**. Save.
5. Wait about a minute, then refresh that Settings → Pages screen — it will show your live URL:
   `https://<your-username>.github.io/<repo-name>/`

That's your permanent link. Share it with your club.

## Every month, after a tournament finishes

1. Open `tool.html` (locally, or at `https://<your-username>.github.io/<repo-name>/tool.html`) and finish entering results.
2. Click **Download shareable HTML** (bottom of the Schedule or Standings tab). This saves a static, read-only file — recipients can't edit anything in it.
3. Rename the downloaded file to something like `2026-09.html` (year-month is a good convention).
4. In your GitHub repo, go to the `tournaments` folder → **Add file → Upload files** → upload that renamed file.
5. Open `index.html` in the repo (click it, then the pencil/edit icon), and add one line inside the `<ul>...</ul>` list:
   ```html
   <li><a href="tournaments/2026-09.html">September 2026</a></li>
   ```
6. Commit. Give it about a minute — the live site updates automatically, no redeploy step needed.

## A note on the interactive tool vs. the shared snapshots

- `tool.html` is the **live working copy** — draft picks, pairing selection, and score entry all happen here, and it auto-saves in whichever browser you're using it from.
- Each file in `tournaments/` is a **frozen snapshot** — exactly what things looked like the moment you clicked "Download shareable HTML." It won't update itself; export a fresh one any time you want to share newer results.
- If you want people to see *live* scores updating during the tournament (not just a snapshot afterward), that needs a small shared database and is a bigger step up — happy to help design that if you want it later; this starter kit covers "share results after/during a tournament via a link," which is what was asked for here.

## If you'd rather use git/command line instead of the web upload

```bash
git init
git remote add origin https://github.com/<your-username>/<repo-name>.git
git add .
git commit -m "Initial tournament site"
git branch -M main
git push -u origin main
```
Then continue from step 4 above (enabling Pages in Settings).
