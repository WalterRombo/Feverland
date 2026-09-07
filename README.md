# Feverland

A capture → triage → prioritise tool for getting ideas and tasks out of your head, with separate mirrored streams for personal and work.

## How it works

- **Capture** — one box, no thinking. Everything goes here first, mixed together, exactly like the pocket notebook.
- **Triage** — sort each item one at a time. First choose where it belongs (Personal / Work / Bin), then whether it's an active task ("Do") or an idea for later ("Someday"). Personal items also get an optional tag: Creative/hobby or Administrative.
- **Today** — your ranked list, split by stream, with the top 3 visually distinct from the rest. Reorder with the up/down arrows.
- **Someday** — parked ideas per stream, filterable by tag on the personal side.
- **Review** — a weekly check: anything stuck unsorted for 7+ days, someday items gone quiet for 30+ days (keep or let go), and a quick read on your current active load per stream.

Everything is stored locally in the browser (`localStorage`) — nothing leaves your device, and there's no account or sync. If you want it synced across devices later, that could be added the same way Itinerary uses getpantry.cloud.

## Files

- `index.html` — the whole app (no build step: React + Babel Standalone from CDN)
- `manifest.json` — PWA manifest for "Add to Home Screen"
- `sw.js` — service worker for offline use and caching
- `icon-192.png`, `icon-512.png` — app icons (simple placeholder — swap these for anything you prefer)

## Deploying to GitHub Pages (same workflow as Parabola)

1. Create a new repo (e.g. `feverland`) and add these files to it via **GitHub Desktop**.
2. Commit and push to `main`.
3. On GitHub.com: repo → **Settings → Pages** → set source to `main` branch, root folder.
4. Wait a minute or two, then visit `https://<your-username>.github.io/feverland/`.
5. On your phone, open that URL and use **Add to Home Screen** (Safari: Share → Add to Home Screen; Android Chrome: menu → Add to Home Screen) to install it like an app.

## Notes / things you might want to tweak

- Renaming: it's called "Feverland" throughout the UI (`<h1>` in `index.html`) and in `manifest.json` — change both if you want a different name.
- The service worker cache is versioned as `feverland-v1` — bump this string in `sw.js` if you make future edits and want the phone's cached copy to refresh.
- "Done" tasks currently just disappear from the Today list rather than going to an archive — easy to add a Done/history view later if you want to look back on completed work.
