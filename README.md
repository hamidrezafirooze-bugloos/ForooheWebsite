# Zino — Brand Showcase

A single-page design showcase for **Zino · patient support**: animated symbol, concept, construction, logo system, color, typography, and a real app mockup.

## Quick start
No build step — it's a static site.

```bash
# any static server works, e.g.
npx serve .
# or
python3 -m http.server 8000
```
Then open the printed URL.

## Structure
- `index.html` — the whole site (inline SVG + CSS + a little JS)
- `assets/` — logo SVGs, PNG exports, seamless pattern, phone mockup
- `reference/` — brand reference, design tokens (CSS/JSON), copy & AI prompts
- `CLAUDE.md` — architecture + conventions + TODO (read this first if continuing the build)

## Brand quick facts
- Colors: Indigo `#2C3A94`, Azure `#128FCD`, Canvas navy `#110F26`
- Type: **Galano Grotesque** (Bold wordmark / Regular body). Poppins is the in-page fallback until the font is licensed.

See `reference/zino-brand-reference.md` for the full spec.
