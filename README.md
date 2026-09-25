# SICE SOC — Itinerary (PWA)

A tactical calendar, weekly schedule and agenda planner. Installable on your
phone as an app — works offline, no app store needed.

## What was fixed / added

- **Critical bug fix**: an unclosed comment in the original file was silently
  disabling reminders, the WhatsApp export, and the calendar's initial
  render. One character fix — the app now actually finishes loading and
  reminders fire correctly.
- **Mobile layout**: bigger tap targets, no accidental zoom when tapping an
  input field, safe-area padding so content clears the notch/home bar,
  tighter calendar grid on small phones.
- **Installable PWA**: `manifest.json` + `service-worker.js` + icons, so it
  can be added to your home screen and opens like a native app (works
  offline once installed).

## Files

```
index.html          — the app
manifest.json        — PWA install config
service-worker.js    — offline caching
icons/                — app icons (192px, 512px, apple touch icon)
```

## Deploy to GitHub Pages (free hosting, no server needed)

1. Go to https://github.com/new and create a new repository (e.g.
   `sice-itinerary`). Keep it **Public** (required for free GitHub Pages).
2. On the repo page, click **Add file → Upload files**.
3. Drag in every file from this folder, **keeping the `icons/` folder
   structure intact** (drag the whole `icons` folder in, don't flatten it).
4. Commit the upload (green **Commit changes** button).
5. Go to **Settings → Pages** (left sidebar).
6. Under **Build and deployment → Source**, choose **Deploy from a branch**.
7. Branch: `main`, folder: `/ (root)` → **Save**.
8. Wait ~1 minute, then refresh — GitHub shows your live URL, something like:
   `https://<your-username>.github.io/sice-itinerary/`

That URL is your app, live on the internet, for free.

## Install it on your phone

**Android (Chrome):**
1. Open your GitHub Pages URL in Chrome.
2. Tap the **⬇️ Install App** button in the app header (or Chrome's menu →
   **Add to Home screen**).
3. Confirm — it now sits on your home screen like any other app.

**iPhone (Safari):**
1. Open your GitHub Pages URL in Safari (must be Safari, not Chrome).
2. Tap the **Share** icon (square with an arrow) at the bottom.
3. Scroll down, tap **Add to Home Screen** → **Add**.
4. It now opens full-screen from your home screen, no browser bar.

The app shows this same instruction automatically on iPhone if it detects
you haven't installed it yet.

## Notes on data

All entries are stored in your phone's local browser storage
(`localStorage`) — nothing is sent to a server. This means:
- Your data stays on your device only.
- If you clear your browser's site data, or switch phones, entries won't
  carry over automatically. There's no backup/export/import built in yet —
  say the word if you want that added (e.g. export to a file you can
  re-import).

## Updating later

Any time you want changes, edit `index.html` (or ask for a new version),
re-upload the changed file(s) to the same GitHub repo (**Add file → Upload
files**, same names — GitHub asks to confirm the overwrite), commit, and
the live URL updates within about a minute. Everyone who installed it will
get the update automatically next time they open the app online.
