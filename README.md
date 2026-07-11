# Ona — public site (GitHub Pages)

Static support + legal pages for App Store Connect. **No app code here.**

Pages:
- `index.html` — landing page
- `support.html` — **Support & FAQ** (this is your App Store Connect *Support URL*)
- `privacy.html` — Privacy Policy (your *Privacy Policy URL*)
- `user-agreement.html` — User Agreement / EULA
- `style.css`, `.nojekyll`

## URLs for App Store Connect

- **Support URL:** `https://currygohan.github.io/ona-legal/support.html`
- **Privacy Policy URL:** `https://currygohan.github.io/ona-legal/privacy.html`

## Publish / update

This folder is its own git repo pointed at your public `ona-legal` repo. After regenerating the pages, commit and push:

```bash
cd legal-site
git add -A
git commit -m "Add support page + zero-tolerance terms"
git push
```

## Enable GitHub Pages (one time)

On GitHub: **ona-legal repo → Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` → Folder: `/ (root)` → Save.**

Wait 1–2 minutes, then confirm `https://currygohan.github.io/ona-legal/support.html` loads. If you get a 404, double-check the branch/folder and that the repo is **public**.

## Regenerating

1. Edit `Ona/Resources/Legal/*.txt` in the app repo.
2. Run `python3 tools/build_legal_pages.py` from the project root — it rewrites every file in this folder (including `support.html`).
3. Commit and push this folder.
