# Demon Time

Photo-proof task tracker for iPhone. Static web app with no build step and no backend. Data stays on the phone (IndexedDB).

## Put it on your iPhone
1. Host this folder on any HTTPS static host, for example:
   - **Netlify Drop:** go to https://app.netlify.com/drop and drag this `demon-time` folder onto the page.
   - **GitHub Pages:** push the folder to a repo, then Settings → Pages → deploy from branch.
2. Open the URL in **Safari** on the iPhone → Share → **Add to Home Screen**.
3. Launch it from the Home Screen icon. It runs full-screen, without the Safari bars.

Tip: always open it from the Home Screen icon. Safari and the installed app keep separate storage.

## Files
- `index.html`: the entire app (UI, storage, camera → JPEG pipeline)
- `manifest.webmanifest`, `sw.js`: Home Screen install and offline shell
- `icon.png` (1600×1600), `icon-512.png`, `icon-192.png`, `apple-touch-icon.png` (180×180): app icon

## Behavior notes
- A task is **Due now** for 60 minutes after its time, then **Overdue** (`DUE_WINDOW_MIN` in `index.html`).
- Photos are downscaled to max 1600 px, saved as JPEG, validated, and read back before the task counts as done.
- History keeps the last 7 days (`RETENTION_MS`).
