# SkyCheck — weather PWA

Search any city or zip code and get current conditions, a 48‑hour hourly strip, a 10‑day forecast, sunrise/sunset, and a live clock in that location's local time. °F by default with a °C toggle. No API keys, no build step, no backend.

Files: `index.html` (the whole app), `manifest.json`, `sw.js` (offline app shell), `icon-192.png`, `icon-512.png`.

Data: Open‑Meteo (forecast + city geocoding, free, no key) and Zippopotam.us (US zip → coordinates).

## Host it (needs HTTPS for the "install" prompt)

Pick one:

1. **GitHub Pages** — create a repo, upload these five files to the root, Settings → Pages → deploy from `main`. URL: `https://<user>.github.io/<repo>/`.
2. **Netlify Drop** — go to app.netlify.com/drop and drag the folder in. Instant HTTPS URL.
3. **Cloudflare Pages / Vercel** — same idea, static upload.

Local preview: `python3 -m http.server 8080` in this folder, then open http://localhost:8080 (localhost counts as secure, so the service worker works there too).

## Install on your phone

- **iPhone (Safari):** open the URL → Share → *Add to Home Screen*.
- **Android (Chrome):** open the URL → ⋮ menu → *Install app* / *Add to Home screen*.

## Tweaks

- Forecast length: `FORECAST_DAYS` in `index.html` (Open‑Meteo allows up to 16).
- Default unit: change `'F'` in `let unit = ... || 'F'`.
- Colors: the `--bg1/--bg2` variables per weather theme at the top of the stylesheet.
