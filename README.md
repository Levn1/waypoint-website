# Waypoint website

Marketing site for Waypoint — the smart personal map. Plain static HTML/CSS, no build step.

## Structure

```
index.html          Landing page
privacy/index.html  Privacy policy, served at /privacy
terms/index.html    Terms of Service, served at /terms
styles.css          Shared styles (design tokens, components, responsive)
assets/             Logo, icons, app screenshots, category marker pins
assets/fonts/       Self-hosted woff2 fonts (no Google Fonts requests)
```

## Develop / preview

No build step. Serve the folder with any static server:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

All internal paths are **relative** (`assets/…`, `../assets/…`) so the site works both at the
GitHub Pages subpath (`/waypoint-website/`) and at the domain root (`waypointmap.co`) — keep it
that way when editing. The `og:url`/`og:image` meta tags are absolute (the spec requires it);
update their host in all three pages when the site moves to waypointmap.co.

## Deploy

Any static host (Cloudflare Pages, Netlify, GitHub Pages, S3) works. The `privacy/index.html`
layout means `/privacy` resolves cleanly on every host. Point the host at the repo root.

## Notes

- The app screenshots in `assets/` (`app_map`, `app_list`, `app_results`) are real product
  shots from the design handoff. Replace the files in place to update them.
- Fonts: Inter Tight, Instrument Serif, JetBrains Mono — self-hosted in `assets/fonts/`
  (latin subset, variable weights), so no visitor data flows to Google Fonts.
- Primary color `#E54B3C`; category accents come from the marker pins.
