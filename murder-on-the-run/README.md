# Murder on the Run — installable PWA

An audio-first detective mystery, played on the move. Two full cases, a living
suspicion board, run modes, ranks, a weekly investigation, achievements, and an
evidence board — now installable to your phone's home screen and playable offline.

## Files

| File | What it is |
|------|-----------|
| `index.html` | The whole game (HTML + CSS + JS, self-contained). |
| `manifest.json` | App name, colours, icons, standalone display. |
| `service-worker.js` | Caches the app shell so it runs fully offline after first load. |
| `icon-192.png` / `icon-512.png` | Home-screen icons. |
| `icon-512-maskable.png` | Adaptive icon for Android. |

> All files must sit in the **same folder**, and the app must be served over
> **https** (or `localhost`) for the service worker to activate. Opening
> `index.html` directly from disk will run the game but won't install as a PWA.

## Deploy to GitHub Pages (recommended — you already use it)

1. Put these files in a repo, e.g. a `murder-on-the-run/` folder in
   `lizzierunner.github.io`, or their own repo.
2. **Settings → Pages** → serve from your branch (root or `/docs`).
3. Visit the https URL Pages gives you. On your phone:
   - **iPhone (Safari):** Share → *Add to Home Screen*.
   - **Android (Chrome):** menu ⋮ → *Install app* / *Add to Home screen*.
4. Launch from the home-screen icon — it opens full-screen, no browser chrome,
   and works with no signal.

## Deploy to Replit

1. New static/HTML repl → upload all files to the **root**.
2. Click **Run**; open the https preview on your phone and install as above.

## Verify the PWA (DevTools → Application)

- Manifest loaded ✓
- Service worker activated ✓
- Icons present ✓
- Display mode: standalone ✓
- Toggle **Offline** and reload — it should still play ✓

## Notes

- Fonts (Cormorant Garamond / Josefin Sans) load from Google Fonts online and
  fall back to system serif/sans offline — the game is fully playable either way.
- Progress (solved cases, rank, weekly investigation, commendations) is saved in
  the browser via `localStorage`, per device.
- Next planned step: wiring **Pursuit mode** to real pace/cadence (GPS or device
  motion) — the reason this needed to be a real, installable app first.
