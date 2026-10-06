# NASH · Bake / Play — a scroll-story remix of the NASH Artisanal Bakery site

**Built:** 2026-10-06 23:10 (Riyadh) · **Source site:** `C:\Users\alihu\WebstormProjects\NashBakery` (read only, not modified)
**Inspiration:** the "POUR / PLAY" coffee-site reel by enkywebstudio on Instagram — https://www.instagram.com/reel/DeAP-bpsvy3/

## What it is
Same bakery, same photos, same bilingual copy, new choreography. Five pinned scenes that scrub with the scroll, the way the reel does:

1. **Find your NASH bake** — oversized soft-serif headline, the Basque cheesecake in front of it, four product cards floating around (they follow the pointer and fly out as you scroll).
2. **Grind** — coffee beans rain into the grinder's hopper behind a giant "GRIND"; as you scroll the grinder comes apart (lid, hopper, collar, body lift off like the reel's exploded grinder) and fresh grounds pour out of the chute, with ingredient call-outs on leader lines.
3. **Pour** — a gooseneck kettle swings in and tips; a ribbon of espresso pours straight into the glass carafe (the part inside the glass is drawn translucent), with beads of light travelling down the stream and ripples where it lands. The big "POUR" has a stretched "SLOW" echo that settles as you scroll.
4. **Roll** — a giant "ROLL" behind the cinnamon roll; cinnamon flakes and sugar fall on a canvas; the letters split apart as you scroll.
5. **Damascene** — the cookie cluster comes apart into its parts (single cookie, rose buds, petals) with ingredient call-outs on leader lines, like the reel's exploded grinder; rose petals fall.
6. **Pour (matcha)** — a matcha stream pours into the cup, the cup "fills" (0–100 % counter), and the stretched echo word "MATCHA" settles into place (the reel's stretched "Pour" echo).
7. **Sip** — a dark coffee wave rises, the espresso cup rides up with it, and wipes the page to night, with "SIP", opening hours and the order button. The nav switches to cream on dark.

Then a menu teaser that links to the separate menu page, and a footer.

**`menu.html`** is its own page: the helix menu carried over from the original NashBakery site (`menu.html` + `js/menu-helix.js`), re-skinned in the new palette. Every item is a rung of a double helix, English on one strand and Arabic on the other; scrolling turns the helix past a sticky round plate that shows the item closest to the centre, with category chips that jump to each section. Reachable from the nav ("Menu" and "Order"), every call-to-action, and the teaser at the bottom of the main page.

## Details
- **No libraries.** Pinning uses `position: sticky` inside a tall wrapper; progress = how far the wrapper scrolled past the top, smoothed with a 120 ms half-life (feels like GSAP's `scrub: 0.6`).
- **Fonts are self-hosted** (`assets/fonts`, SIL OFL): Fraunces (display, with the SOFT/WONK axes for the retro look), Inter, Reem Kufi and IBM Plex Sans Arabic. The site works offline and straight from disk.
- **Coffee objects** (kettle, carafe, grinder, espresso cup) were generated with Canva's image generator, cut out with U²-Net, and the grinder was sliced into lid / hopper / collar / body for the exploded view (`assets/coffee/`). Beans, grounds, the water arc, drips and the filling carafe are drawn on canvas.
- **Cutouts:** the product photos were cut out from the original site's images with a U²-Net model (see `assets/*.webp`). Loose cookies and petals came from `story.webp`.
- **Arabic / English** toggle in the nav (the original site's Arabic copy, plus new lines for the new scenes). RTL mirrors every scene.
- **Reduced motion:** scenes unpin and show their finished state; canvases are off.
- **Capture hook:** open with `?capture` and call `__step(dt)` to advance the canvases frame by frame (how `preview.mp4` was recorded).

## Files
- `index.html` — the scroll story (inline CSS/JS)
- `menu.html` — the helix menu page (inline CSS/JS, `assets/menu/` photos)
- `assets/` — cutouts, logos, storefront still, fonts
- `preview.mp4` — 20 s scroll-through at 1280×720 · `screenshot.png` — the hero
- `open-site.bat` — opens the site in your default browser

## Ideas for next time
- Replace the drawn matcha stream with a short pour video played frame by frame on scroll.
- Give the Damascene scene a real exploded-view photo set (each ingredient shot separately).
- Add the midnight clock and "open now" status from the original site to the SIP scene.
