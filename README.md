# Daily Ledger — Deploy & Install

## What's in this folder
- `index.html` — the entire app (UI + logic)
- `manifest.json` — makes it installable as a home-screen app
- `sw.js` — service worker, caches the app for offline use
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png` — app icons

All your data (entries, notes) is stored locally in the browser via `localStorage`.
Nothing is sent to any server. Use the Export button in the app regularly as a backup.

## 1. Push it to GitHub

```bash
cd daily-ledger          # this folder
git init
git add .
git commit -m "Daily Ledger v1"
```

Create a new empty repo on GitHub (e.g. `daily-ledger`), then:

```bash
git remote add origin https://github.com/<your-username>/daily-ledger.git
git branch -M main
git push -u origin main
```

## 2. Enable GitHub Pages

1. On GitHub, open the repo → **Settings** → **Pages**.
2. Under "Build and deployment", set **Source** to `Deploy from a branch`.
3. Branch: `main`, folder: `/ (root)`. Save.
4. Wait ~1 minute. Your app will be live at:
   `https://<your-username>.github.io/daily-ledger/`

## 3. Install on your phone

1. Open that URL in **Chrome** on your Android phone.
2. Tap the **⋮** menu → **Add to Home screen** (Chrome may also prompt you automatically).
3. Confirm. You'll get a real app icon on your home screen that opens full-screen, no browser bar.

## Updating later

Any time you (or I) change a file, just commit and push again:

```bash
git add .
git commit -m "update"
git push
```

GitHub Pages redeploys automatically in under a minute. Since the service worker
caches the app, you may need to close the app fully and reopen it (or pull-to-refresh)
once to pick up changes.

## Notes / known v1 limitations
- The habit list (the 4 items) is fixed in the code for now — you mentioned wanting
  to edit it later; that's an easy follow-up (just ask).
- Data lives only on this phone's Chrome browser. Export to JSON regularly if you
  want a backup or plan to switch phones — Import will restore it.
- No push notifications (see chat — using a phone alarm instead is simpler and
  more reliable without a backend server).
