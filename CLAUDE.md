# CLAUDE.md — Zino Brand Showcase

Guidance for Claude Code (and any dev) working in this repo.

## What this is
A single-page, **design-showcase** website for **Zino — patient support** (a patient-support app). It presents the brand identity: the animated symbol, concept, construction, logo system, color, typography, and a real app mockup. It is **not** the product marketing site (though it can evolve into one).

Everything derives from the client's original source files (PSD/PDF). Colors were **sampled** from the artwork and the typeface was **read from the PSD type layers** — so the values in this repo are authentic, not guessed.

## Run it
It's a static site, no build step.
```bash
npx serve .            # or: python3 -m http.server 8000
```
Open the served URL. (Opening `index.html` via file:// mostly works, but a server avoids any asset/CORS quirks.)

## Project structure
```
index.html                     ← the entire site (self-contained except assets below)
assets/
  symbol/                       ← vector logo (SVG)
    zino-symbol.svg             ← MASTER layered symbol (animation-ready ids)
    zino-shape-a.svg / -b.svg   ← individual blades
    zino-symbol-white.svg / -navy.svg
    zino-wordmark-stacked-raw.svg   ← traced "zi/no" (potrace output)
    zino-wordmark-horizontal-raw.svg← traced "zino" horizontal
    zino-patient-support-raw.svg    ← traced "patient support"
  png/                          ← transparent PNG exports of the symbol (1x/2x/3x, shapes, mono)
  pattern/                      ← seamless background pattern tile (SVG) + preview
  mockups/                      ← zino-phone-splash.webp/.png (real device, bg removed)
reference/
  zino-brand-reference.md       ← colors, type, usage, file inventory
  zino-tokens.css / .json       ← design tokens
  zino-copy-and-prompts.md      ← landing copy + AI prompts for mockups/animation
CLAUDE.md / README.md
```

## How `index.html` is built (architecture)
One HTML file. No framework, no build. Order inside:
1. `<head>`: Google Fonts (**Poppins** as the web stand-in for Galano Grotesque) + one big `<style>` block using CSS variables (see tokens below).
2. Right after `<body>`: a hidden `<svg><defs>` that defines **reusable wordmark symbols** — `#wmS` (stacked zino), `#wmH` (horizontal zino), `#wmP` (patient support), plus `#footgrad` gradient. These are `<use>`d wherever the wordmark appears (nav, system cards, type specimen, footer). Paths inherit `fill` from the `<use>` (no fill on the symbol paths) so they can be colored solid or with a gradient.
3. Sections in order: `hero` → `concept` → `construction` → `system` → `color` → `type` → `apps` → `footer`.
4. A small `<script>` at the end: nav solidify on scroll, IntersectionObserver reveals (`.reveal`, `.sw`), construction-stage replay, and computing SVG path length for the hero line-draw.

### The symbol (important)
The mark = **two blades, each doubled** (a main + an offset echo copy that creates depth). Each symbol instance is inline SVG in this shape:
```
<g transform="translate(0,404) scale(0.1,-0.1)">
  <g class="shape-a"><path .. a-echo /><path .. a-main /></g>
  <g class="shape-b"><path .. b-main /><path .. b-echo /></g>
</g>
```
- The `transform` is potrace's (the paths live in a flipped, 10× coordinate space). Don't "fix" it — gradients are tuned to it (`y1=1 y2=0`).
- **Depth comes from color, not alpha.** This matches the master vector (`assets/symbol/zino-symbol.svg`) exactly: every path is fully opaque, painted in plain order, no `opacity`, no `mix-blend-mode`, no `isolation`. The echo reads as a distinct offset shape purely because its gradient (`g_A_echo`/`g_B_echo`) is a different, deliberately darker-or-lighter color pair than its main (`g_A_main`/`g_B_main`) — e.g. `g_B_echo` (`#14ADE6`→`#1085C6`) is *brighter* than `g_B_main` (`#37A6C6`→`#0F79BE`), which is what gives the bottom blade's echo its soft, glassy-looking edge without any real transparency. Do **not** reintroduce `opacity="0.5"` echoes or `mix-blend-mode:multiply` on `b-main` — that was tried and made the top blade's echo wash out and the bottom blade darken wherever it overlapped anything behind it; always diff new instances against `zino-symbol-3x.png`.
- Gradients are per-instance `<linearGradient>` with a unique suffix (e.g. `g_A_main_hero`). Keep suffixes unique to avoid ID collisions.

### Hero animation ("2 + trace")
Two blades assemble from opposite sides (`@keyframes inA/inB` on `.pieceA/.pieceB`), a faint symbol **outline strokes itself** (`.flourish .ln`, dashoffset animated via JS-measured length), then the **traced wordmark** (`.hwm`) and `.hps` fade up. The hero lockup coordinates (wordmark placed over the symbol) were taken from the PSD, so the overlap matches the official horizontal lockup exactly. viewBox: `0 -118 700 536`.

## Design tokens (see `reference/zino-tokens.css`)
- Indigo `#2C3A94`, Azure `#128FCD`, Sky `#2AA0E0`, Cyan `#14ADE6`, Pale `#BBDEF4`
- Canvas navy `#110F26`, deep `#0E1330`, cards `#171634`, brand-blue field `#0054A6`, white
- Brand gradient `linear-gradient(135deg,#2C3A94,#128FCD)`
- Font: **Galano Grotesque** (Bold = wordmark, Regular = body). Not free — Poppins is the fallback in-page.

## Conventions
- Keep it dependency-free and single-file where reasonable; assets stay in `assets/`.
- Respect `prefers-reduced-motion` (already handled — a media query disables animations and forces final states).
- Mobile: everything is responsive via `clamp()` and grid breakpoints at 820px / 720px / 520px.
- Don't reference `localStorage`/`sessionStorage` — not needed here.
- The wordmark/lettering has **no live vector in the source** (flattened raster); the `*-raw.svg` files are potrace traces. For production, license Galano Grotesque and set the wordmark as live text, or keep the traced SVGs.

## Status — done
- Symbol decomposed to clean layered SVG; transparency/blend restored to match source.
- Full traced typography (stacked + horizontal + patient support) used across nav, hero, system, type, footer.
- Seamless pattern; color & type sections; real device mockup (bg removed) in Applications.

## TODO / next ideas (open)
- [ ] **Monogram "Z"**: the System → Monogram card still uses a Poppins "Z". Trace the stylized gradient **Z** from the source (`Zino_Logotype_05` monogram) and drop it in.
- [ ] **Hero backdrop**: add the large cursive **Z** line-draw (from the guidelines) behind the hero as an SVG stroke animation.
- [ ] **Animation video**: optionally replace the CSS assemble with a client-supplied Lottie/MP4 (prompt in `reference/zino-copy-and-prompts.md`). Keep CSS version as fallback.
- [ ] **Galano Grotesque**: license + self-host webfont; replace the Poppins fallback in the `--zino-font` stack and the type specimen.
- [ ] **More mockups**: client will supply AI mockups (stationery, apparel, more app screens). Remove their backgrounds and add a small gallery beside the phone in `#apps`.
- [ ] Optional: split the big `<style>`/`<script>` into `assets/styles.css` / `assets/app.js` if the file grows.

## Notes for regenerating assets (if needed)
- Symbol vectors were produced by extracting the 4 PSD smart-object layers → potrace → recolor with sampled gradients.
- Phone mockup background was removed with OpenCV GrabCut, then exported as a 720px-wide transparent WebP.
- Original client source files are **not** in this repo; keep them archived separately.
