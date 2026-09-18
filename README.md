# Zino — Brand Showcase

A design showcase for **Zino · patient support**, presenting **two identity directions** to compare and pick from: the geometric two-blade mark and a human-figure mark. `index.html` is a chooser landing page; each direction is its own full site.

## Quick start
No build step — it's a static site.

```bash
# any static server works, e.g.
npx serve .
# or
python3 -m http.server 8000
```
Then open the printed URL (the chooser), or go straight to `geometric.html` / `human.html`.

## Structure
- `index.html` — chooser landing page (two cards → the two directions)
- `geometric.html` — Direction One: the geometric identity (animated symbol, concept, construction, logo system, color, typography, app mockup)
- `human.html` — Direction Two: the human-figure identity (sibling project, own assets/tokens)
- `assets/` — logo SVGs/PNGs, seamless pattern, phone mockup (geometric); `assets/logo/` (human)
- `reference/` — brand reference, design tokens (CSS/JSON), copy & AI prompts, for both directions
- `CLAUDE.md` — architecture + conventions + TODO for both sites (read this first if continuing the build)

## Brand quick facts
- Geometric: Indigo `#2C3A94`, Azure `#128FCD`, canvas navy `#110F26`
- Human: Zino blue `#0072BC`, accent `#29ABE2`, canvas navy `#131026`
- Type: **Galano Grotesque** (Bold wordmark / Regular body) for both. Poppins is the in-page fallback until the font is licensed.

See `reference/zino-brand-reference.md` for the geometric direction's full spec.
