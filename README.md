# SKRATCH STUDIO — landing page

Single-page landing site for SKRATCH STUDIO, a Vilnius barbershop. Static — no
build step, no framework: plain HTML with inline CSS + images.

## Sections (top → bottom)
1. **Hero** — 16:9 frame. Layers (back → front): B&W photo, two white "A"
   shapes, cut-out client, orange SKRATCH STUDIO logo (fades in on load). The
   hand-drawn crown is baked into the photo and cut-out images. Nav HOME / ABOUT / SHOP / CONTACT with a round
   black badge centred, and an orange "BOOK NOW" pill
   (→ https://skratchstudio.setmore.com).
2. **Caption separator** — "FIG. 01 — The taper, finished by hand" / "N° 01 / THE WORK".
3. **Photo spread** — orange 16:9 frame, white "A" shapes behind, five staggered
   B&W shop photos, quote "It's not a copy, it's building, from SKRATCH."
4. **Shop** (`#shop`) — "The Shop" / "N° 02 / Merch": feature image + Studio
   Tee (€35) + Studio Cap (€28), "Reserve" links → setmore. Becomes a swipe
   carousel at ≤820px.
5. **Caption separator** — "FIG. 02 — The chair, the comb, the craft" / "N° 03 / ABOUT US".
6. **About** (`#about`) — marble-tee background, cream frame, "The Craft" and
   "Skratch Signature" text blocks (client copy).
7. **Footer** — orange, black wordmark + links + copyright.

## Run locally
```bash
npm start            # serves ./public at http://localhost:3000
# or, with no dependencies:
python3 -m http.server 3000 --directory public
```

## Structure
```
public/                 # the live site (deployed/served)
  index.html            # the page (all CSS inline)
  assets/
    canva/              # hero layers (crown baked in), "A" shape, orange logo, shop + cap photos
    iso-circle-black.png  # round badge, top-centre of hero
    tee-hero.png        # cut-out tee (shop card)
    tee-marble.jpg      # shop feature image + About background
    wordmark-black.png  # footer logo
vercel.json             # static deploy config (serve public/, no build)
handoff-skratch-canva 3/  # design handoff: reference page + full-res source images
```
`public/assets/*` are web-ready derivatives of the handoff images (~2.6 MB
total). Photos are JPEG; images that need transparency (cut-out, "A" shape,
logos) stay PNG.

## Brand tokens (page `:root`)
- Orange `#ff751f` · cream `#F2EFE6` · ink `#151818` · white `#ffffff` · grey `#D4D5CF`
- Fonts (Google Fonts): **Space Mono** (nav, button), **Outfit** (captions,
  about, footer), **Bodoni Moda** italic (quote)

## Phone layout (≤640px)
Overrides live in the `@media(max-width:640px)` block at the end of the `<style>`.
- Hero fills the screen (100svh); cut-out and "A" shapes hidden, photo covers
  with the crown kept in frame. Badge top-left, nav top-right (44px tap
  targets), logo centred, BOOK NOW near the bottom.
- Photo spread becomes a 2-column grid; the middle photo goes full width with
  the quote centred on it.
- Shop is a horizontal swipe carousel; About is left-aligned on a dark tint.

## Before launch — still to do
- **Placeholder content:** Contact nav link and footer links (except About)
  are `#`; FIG. caption copy, shop prices, "Wear the chair home." and the
  Reserve target (currently setmore) need client sign-off.

## Deploy
Static site — `vercel.json` serves `public/` with no build step.
