# SKRATCH STUDIO — landing page

Single-page landing site for SKRATCH STUDIO, a Vilnius barbershop. Design
direction **Option A · Cover Story** (magazine-cover hero + editor's letter,
dark theme). Static — no build step, no framework: plain HTML + one CSS file +
images, with a small vanilla-JS language toggle.

## Run locally

```bash
npm start            # serves ./public at http://localhost:3000
# or, with no dependencies:
python3 -m http.server 3000 --directory public
```

A static server is required; opening `index.html` from the filesystem won't load
the assets correctly.

## Structure

```
public/                 # the live site (this is what gets deployed/served)
  index.html            # Option A, with EN/LT toggle + lazy-loaded images
  brand.css             # shared brand tokens (colors, fonts, reset)
  assets/               # web-optimized images (~2.2 MB total)
handoff/                # original design handoff + full-resolution source images
```

`public/assets/*` are compressed/resized derivatives of the originals in
`handoff/assets/*` (23 MB → ~2.2 MB). Keep `handoff/` as the source of truth for
re-exporting images later; it is not part of the served site.

## Language toggle (EN / LT)

- English is the inline content (good for SEO and no-JS fallback). The toggle in
  the cover topline swaps to Lithuanian and back.
- Translations live in the `LT` object in the inline `<script>` at the bottom of
  `public/index.html`. To edit copy: change the English in the markup **and** the
  matching `LT["key"]` string (elements are paired by `data-i18n="key"`).
- The choice is remembered in `localStorage`; first-time visitors default to
  Lithuanian if their browser language is `lt`, otherwise English.

## Brand system (`brand.css`)

- `--negro` #151818 · `--gris` #D4D5CF · `--blanco` #F6FBFA
- `--naranja` #F57422 (primary accent) · `--quemado` #D64900
- Body font **Outfit**, editorial accents **Instrument Serif** (both via Google
  Fonts `<link>` — no local font files).

## Before launch — still to do

- **Real photography:** the gallery images (`work-*.jpg`) are licensed Unsplash
  stand-ins; swap in real shop photography. Hero and merch mockups are brand assets.
- **Real content:** address (`Vilniaus g. 00`), phone (`+370 600 00000`), hours,
  prices, and social links are placeholders.
- **Booking:** the "Book your chair" buttons link to `#` — wire to a provider
  (e.g. Fresha) when the account is ready.
- **Translation review:** have a native speaker proof the Lithuanian copy.

## Deploy

Static site — drop `public/` on Netlify, Vercel, or any static host.
