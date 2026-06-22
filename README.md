# SKRATCH STUDIO — landing page

Single-page landing site for SKRATCH STUDIO, a Vilnius barbershop. Static — no
build step, no framework: plain HTML + one CSS file + images.

## Sections (top → bottom)
1. **Hero** — full-viewport editorial layout: oversized SKRATCH / STUDIO type, a
   cut-out tee centered, chrome wordmark, burnt-orange ribbon, "Book now" button.
2. **Services** — "SERVICES" ticker + bento grid (Haircut / Beard Trim / Hot
   Shave / Products / Gallery, each with a book button) + vertical accent panel.
3. **About** — marble-tee background with "The Craft" and "Skratch Signature"
   text blocks.
4. **Footer** — dark, centered wordmark + nav + copyright.

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
public/                 # the live site (deployed/served)
  index.html            # the page
  brand.css             # shared brand tokens (colors, Outfit font, reset)
  assets/               # web-optimized images (~2.3 MB total)
vercel.json             # static deploy config (serve public/, no build)
handoff-landing/        # design handoff + full-res source images (gitignored)
handoff/                # earlier "Cover Story" design handoff (gitignored)
```
`public/assets/*` are compressed/resized derivatives of the originals in
`handoff-landing/assets/*` (24 MB → ~2.3 MB). Photos are JPEG; images that need
transparency (cut-out tee, chrome/white wordmarks, circular logo) stay PNG.
The `handoff*` folders are the source of truth for re-exporting images and are
not part of the served site.

## Brand system (`brand.css` + page `:root`)
- `--cream` #F2EFE6 (page) · `--ink` #151818 · `--accent` #F57422 (orange) ·
  `--quemado` #D64900 (ribbon) · `--gris` #D4D5CF
- Body/display font **Outfit**; script accent ("barbería") **Sacramento**
  (both via Google Fonts — no local font files).

## Before launch — still to do
- **Real content:** phone (`+370 600 00000`), address, hours, prices, social
  links, and the nav/footer links (currently `#`) are placeholders.
- **Real photography:** some service/gallery images are licensed Unsplash
  stand-ins; the tee/logo/wordmark renders are brand assets. Swap in real shop
  photography.
- **Booking:** the "Book now" buttons link to `#` — wire to a provider (e.g.
  Fresha) when the account is ready.
- **Lithuanian:** this design ships in English only. The previous "Cover Story"
  version had an EN/LT toggle; it can be re-added here on request.

## Deploy
Static site — `vercel.json` serves `public/` with no build step. Push to GitHub
and import on Vercel (or `vercel --prod` via the CLI). Any static host works too.
