# Waypoint website

Marketing site for Waypoint — the smart personal map. Plain static HTML/CSS, no build step.

## Structure

```
index.html          Landing page
privacy/index.html  Privacy policy, served at /privacy
styles.css          Shared styles (design tokens, components, responsive)
assets/             Logo, app screenshots, category marker pins
```

## Develop / preview

No build step. Serve the folder with any static server:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

(Open via a server rather than `file://` — the pages use root-relative paths like `/assets/…`.)

## Deploy

Any static host (Cloudflare Pages, Netlify, GitHub Pages, S3) works. The `privacy/index.html`
layout means `/privacy` resolves cleanly on every host. Point the host at the repo root.

## Notes

- The app screenshots in `assets/` (`app_map`, `app_list`, `app_results`) are real product
  shots from the design handoff. Replace the files in place to update them.
- Fonts: Inter Tight, Instrument Serif, JetBrains Mono (Google Fonts).
- Primary color `#E54B3C`; category accents come from the marker pins.
