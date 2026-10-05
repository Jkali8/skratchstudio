# SKRATCH STUDIO — Landing page (Canva-based version)

Single static page. Plain HTML + inline CSS + no framework. Open `index.html` or run `npx serve .`

## Files
```
index.html
assets/
  canva/hero-bg-crown.png    Hero background photo with the hand-drawn crown baked in
  canva/hero-cutout-crown.png Same client, transparent cut-out (crown baked in, aligned with bg)
  canva/logo-orange.png      Orange SKRATCH STUDIO logo (transparent)
  canva/crown.svg            Hand-drawn crown source vector (already baked into the hero images; not referenced by the page)
  canva/a-ghost.png          Faint white "A" shape — used twice (one rotated 180°) in hero + photo section
  canva/shop-0252..0274.jpg  Shop photography (resized to 1600px)
  canva/shop-cap.jpg         Cap product shot
  iso-circle-black.png       Round "A" badge — top-centre nav logo
  tee-hero.png               Cut-out tee — shop product card
  tee-marble.png             Tee on marble — shop feature image + About background
  wordmark-black.png         Footer logo
```

## Sections (top → bottom)
1. **Hero** — 16:9 frame. Layers: bg photo → 2 white A shapes → cut-out client → orange logo (logo fades in on load). The crown is part of the photo images. Nav HOME / ABOUT / SHOP (#shop) / CONTACT in orange Space Mono, round black badge centred. Orange pill **BOOK NOW** → https://skratchstudio.setmore.com (new tab).
2. **Caption bar** — cream: "FIG. 01 — The taper, finished by hand" / "N° 01 / THE WORK" (numbers orange).
3. **Photo spread** — orange 16:9 frame, white A shapes behind, 5 B&W photos staggered (.p1–.p5, absolute %). Quote: "It's not a copy, it's building, from SKRATCH." (Bodoni Moda italic + Space Mono bold).
4. **Shop** (#shop) — cream. "The Shop" heading + "N° 02 / Merch". Feature image + Studio Tee (€35) + Studio Cap (€28), "Reserve" links → setmore. **Prices and Reserve target are placeholders.**
5. **Caption bar** — "FIG. 02 — The chair, the comb, the craft" / "N° 03 / ABOUT US".
6. **About** — tee-on-marble background, 48px cream frame. Client copy: "SKRATCH is a creative studio built from scratch…" / "We don't follow trends — we build culture, one creation at a time."
7. **Footer** — orange, black wordmark, links, copyright.

## Tokens
- Orange `#ff751f` · card `#fff6f6` · cream `#F2EFE6` · ink `#151818` · white `#fff` · grey `#D4D5CF`
- Google Fonts: **Space Mono** 400/700 · **Outfit** · **Bodoni Moda** (italic)

## Phone layout (≤640px)
- Hero fills the screen (100svh, min 560px). Cut-out + white A's hidden; bg photo covers (object-position 40% 40%) so the crown stays in frame.
- Orange logo vertically centred; round badge top-left; nav links top-right (44px tap targets); BOOK NOW pill near bottom.
- Photo spread: 2-column grid, middle photo full width with the quote centred on it.
- Shop: horizontal swipe carousel, cards snap to centre.
- About: left-aligned text, dark tint over the photo.

## Notes
- Desktop hero + photo spread are 16:9 frames using `container-type:inline-size` + `cqw`; phone overrides live in the `@media(max-width:640px)` block at the end of the <style>.
- Dead CSS/markup safe to delete: `.runhead` (hidden), `.svc-marq`, `.card`, `.row`, `.ribbon`, `.sp-note`.
- Placeholders: footer/social links `#`, FIG. caption copy, shop prices, "Wear the chair home."
- `prefers-reduced-motion` disables the fades.
