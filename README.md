# SKRATCH STUDIO — landing page

Static landing page for SKRATCH STUDIO, a Vilnius barbershop. Imported from the
Claude Design project "New page design options".

The page is a **review canvas** showing three design directions side by side, so
you can compare them live and pick one to ship:

- **Option A · Cover Story** (`public/option-a.html`) — magazine-cover hero +
  editor's letter, dark theme.
- **Option B · The Kiosk** (`public/option-b.html`) — masthead nav, marquee,
  bento-grid services, light theme.
- **Option C · The Feature** (`public/option-c.html`) — editorial spread, orange
  ribbon, multi-column feature text, light theme.

All three share the brand tokens in `public/brand.css`. The comparison canvas
(`public/index.html`) embeds the three options via the `public/design-canvas.jsx`
viewer (React + Babel loaded from a CDN — no build step).

## Run locally

```bash
npm start            # serves ./public at http://localhost:3000
# or, with no dependencies:
python3 -m http.server 3000 --directory public
```

A static server is required (the option pages load over HTTP); opening
`index.html` directly from the filesystem will not work.

## Assets

Real photography is intentionally shown as striped placeholders (`.ph`) in the
designs. Two merch mockups load from `public/assets/`:

- `assets/mockup-tee.png`, `assets/mockup-cap.png` — currently **placeholder**
  images. Replace them with the originals from the Claude Design project
  (`assets/mockup-tee.png` / `assets/mockup-cap.png`); they exceeded the design
  connector's download size limit, so they could not be imported automatically.

The Option A footer wordmark is rendered as styled text rather than the
`wordmark-white.png` logo image — swap in the logo later if preferred.

## Deploy

It's a static site — drop `public/` on Netlify, Vercel, or any static host.

## Roadmap

- Pick one of A / B / C as the live single-page site.
- Localize the chosen option to **English + Lithuanian** (language toggle).
- Wire the "Book your chair" buttons to a booking provider (e.g. Fresha).
- Replace placeholder photography and merch mockups with real shots.
