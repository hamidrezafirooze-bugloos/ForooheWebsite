# Zino — Brand Reference (extracted from source files)

_Patient support app. Values extracted directly from the supplied PSD / PDF files — colors sampled from the artwork, fonts read from the PSD type layers._

## 1. Color palette

### Primary (the two brand dots on the guidelines board)
| Role | HEX | RGB |
|---|---|---|
| Indigo / Violet | `#2C3A94` | 44, 58, 148 |
| Azure / Sky | `#128FCD` | 18, 143, 205 |

### Symbol gradient stops (sampled from the mark)
| Piece | Top | Bottom |
|---|---|---|
| Shape A (drop) | `#2AA0E0` | `#28419A` |
| Shape A echo | `#2569B2` | `#2D3A97` |
| Shape B (blade) | `#37A6C6` | `#0F79BE` |
| Shape B echo | `#14ADE6` | `#1085C6` |
| Lightest highlight | `#BBDEF4` | — |
| Deepest indigo tip | `#203975` | — |

**Brand gradient (recommended for accents/CTAs):** linear `#2C3A94 → #128FCD` (135°).

### Neutrals / backgrounds
| Role | HEX | RGB |
|---|---|---|
| Canvas navy (primary bg) | `#110F26` | 17, 15, 38 |
| Navy deep (sections) | `#0E1330` | 14, 19, 48 |
| Navy raised (cards) | `#1A1836` | 26, 24, 54 |
| Solid blue field (used behind horizontal logo) | `#0054A6` | 0, 84, 166 |
| White | `#FFFFFF` | 255, 255, 255 |

## 2. Typography

**Typeface: Galano Grotesque** (Rene Bieder) — read directly from the PSD type layers.
- **Wordmark "zino":** Galano Grotesque **Bold**
- **"patient support" + supporting text:** Galano Grotesque **Regular**, lowercase, generously letter-spaced (tracking ≈ +200–300 in the tagline).

Galano Grotesque is a commercial font (MyFonts / rene-bieder.com). For the website:
- **Licensed route:** buy the Galano Grotesque webfont kit and self-host (`Bold` + `Regular`, optionally `Light`).
- **Free near-match fallback** (geometric, rounded, single-story `a`): **Poppins**, **Hanken Grotesk**, **Mulish**, or **Sofia Sans**. Poppins is the closest widely-available Google Font.

Suggested CSS stack: `"Galano Grotesque", "Poppins", "Hanken Grotesk", system-ui, sans-serif`.

## 3. Logo variants (in the source)
- **Vertical** — symbol above "zino / patient support"
- **Horizontal** — symbol left, wordmark right
- **Symbol only** — the two interlocking blades
- **Wordmark / monogram** — "zino" with the large gradient **Z** behind it
- **Figure version** — "zino" with the little person (arms raised) formed from the blade — great emotional hero motif for a patient-support brand

**Clear space:** keep at least the height of the symbol's inner notch clear on all sides.
**Min size:** symbol ≥ 24 px; full vertical lockup ≥ 96 px wide.

## 4. What the mark means (for the copy / concept section)
- Two interlocking blades = **patient + supporter**, reaching toward each other.
- Together they read as a stylized **Z** (Zino) and, in the figure lockup, as a **person with arms raised** — recovery, relief, being lifted up.
- Blue palette = trust, calm, clinical cleanliness, care.

## 5. File inventory (this package)
```
symbol/
  zino-symbol.svg          ← master, LAYERED & animation-ready (ids: shape-a[a-echo,a-main], shape-b[b-main,b-echo])
  zino-shape-a.svg         ← upper blade only (with gradient)
  zino-shape-b.svg         ← lower blade only (with gradient)
  zino-symbol-white.svg    ← single-color white (dark backgrounds)
  zino-symbol-navy.svg     ← single-color navy (light backgrounds)
png/
  zino-symbol-1x/2x/3x.png ← transparent, full symbol (461→2766 px wide)
  zino-shape-a-2x.png      ← transparent, upper blade
  zino-shape-b-2x.png      ← transparent, lower blade
  zino-symbol-white-2x.png / zino-symbol-navy-2x.png
pattern/
  zino-pattern-tile.svg    ← 360×360 SEAMLESS tile (use as CSS background-image)
  zino-pattern-preview.svg/.png
reference/
  zino-brand-reference.md  ← this file
  zino-tokens.css / .json  ← ready-to-use design tokens
  zino-copy-and-prompts.md ← landing-page copy + all AI prompts
```
_Note: the wordmark/lettering is not included as vector because the source files are flattened raster (no live vector letterforms). Set "zino" live in Galano Grotesque Bold, or I can trace the wordmark to SVG if you want it as art._
