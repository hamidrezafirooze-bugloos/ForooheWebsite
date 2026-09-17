# Zino — Landing Page Copy & AI Prompts

Everything below is written for the **brand/design showcase** reading (you presenting the identity). Where product-marketing wording differs, an alt line is given.

---

## PART A — Page structure + copy (section by section)

### 1. Hero
- **Eyebrow:** ZINO · PATIENT SUPPORT
- **Headline (pick one):**
  - "Support, in every direction."
  - "Care that reaches back."
  - "Two shapes. One promise: you're not alone."
- **Sub-line:** "A patient-support identity built around a single idea — two people reaching toward each other."
- **Scroll cue:** "Scroll to explore the identity"
- _Product alt headline:_ "Your recovery, supported every step."

### 2. Concept / the idea
- **Section title:** "The idea"
- **Body:** "Zino's mark is two blades that lean into one another — a patient and a supporter, meeting in the middle. Read together they form a **Z**; read closely they become a **figure with open arms**. It's a logo about being lifted, not just treated."

### 3. Construction / anatomy
- **Section title:** "Built to interlock"
- **Body:** "One shape, mirrored and turned, hooks into its twin. The offset echo behind each blade gives the mark depth and a sense of motion — support that's always moving toward you."
- _(This is the section that animates the two blades sliding together — use `zino-shape-a.svg` + `zino-shape-b.svg`.)_

### 4. Logo system
- **Section title:** "One system, every context"
- **Labels:** Vertical · Horizontal · Symbol · Monogram · Figure
- **Body:** "From a favicon to a clinic wall, the identity holds together across every size and surface."

### 5. Color
- **Section title:** "A calm, clinical blue"
- **Body:** "Indigo for trust, azure for clarity, on a deep navy that lets the gradient glow. Blue is the color patients associate with safety and care."
- Show swatches: `#2C3A94`, `#128FCD`, `#110F26`, `#FFFFFF`.

### 6. Typography
- **Section title:** "Galano Grotesque"
- **Body:** "A rounded geometric sans — friendly enough to reassure, precise enough to trust. Bold for the name, light and letter-spaced for the calm supporting voice."

### 7. Applications
- **Section title:** "In the world"
- **Body:** "App screens, a card in a hand, a tote in a waiting room — the mark at work."

### 8. Footer
- **Sign-off:** "Zino — patient support."
- **CTA (showcase):** "Get in touch" / _(product):_ "Download the app"
- **Micro:** "Identity & interface. [Year]."

### Tagline bank
- "You're not alone in this."
- "Support that reaches back."
- "Care, in every direction."
- "Lifted, not just treated."

---

## PART B — AI generation prompts

> Style constants to paste into any prompt: **deep navy background `#110F26`, brand blues indigo `#2C3A94` + azure `#128FCD`, gradient accents, minimalist, modern, clean, lots of negative space, soft studio lighting, healthcare/medtech feel, no clutter.**

### B1. Animated logo (text-to-video / motion tool)
> A minimalist logo reveal on a deep navy background (#110F26). Two smooth rounded blue blades — one indigo (#2C3A94), one azure (#128FCD) — glide in from opposite edges and interlock in the center to form a single geometric symbol, with a soft pale-blue echo trailing each shape. A faint outlined letter "Z" draws itself in behind them like a light stroke. Once locked, the shapes settle with a gentle bounce and a subtle glow pulse. Below, the wordmark "zino" and the tracked-out words "patient support" fade up. Elegant, calm, premium medtech motion; 4 seconds; ease-in-out; seamless loop; 4K; transparent or navy background.

_Tip: if your tool exports **Lottie/JSON**, request that for a crisp, tiny web animation. Otherwise export **MP4 + WebM with alpha**._

### B2. App UI mockups (2–3 screens)
> Clean healthcare mobile app UI, patient-support product, iOS style. Screens: (1) home dashboard with a friendly greeting, next appointment card, medication reminder, and a "talk to your supporter" button; (2) chat/support screen; (3) recovery-progress screen with a simple ring chart. Deep navy and white theme with indigo #2C3A94 and azure #128FCD accents, rounded cards, generous spacing, Poppins-like rounded geometric font, soft shadows, minimalist, accessible, calm. High fidelity, 1080×2340, front-flat view.

### B3. Phone-in-hand lifestyle
> A person's hand holding a modern smartphone showing a calm blue healthcare app, soft natural window light, blurred warm neutral background, shallow depth of field, minimalist, premium, editorial product photography. Leave clean space around the phone for text. Cool blue UI glow. 3:2.

### B4. Stationery / print
> Minimalist medical brand stationery flat-lay: business card, letterhead, and envelope on a deep navy surface. Card front is navy with a small centered gradient blue symbol; back is solid azure #128FCD. Subtle embossing, top-down studio shot, soft shadows, lots of negative space, premium branding mockup. Leave the card face partly clear for the logo.

### B5. Apparel / environment
> A cotton tote bag (or lanyard / clinic wall sign) in deep navy with a single centered blue gradient logo mark, hanging in a bright minimalist clinic waiting room, soft daylight, shallow depth of field, professional mockup photography, clean and calm. Space kept clear where the logo sits.

### B6. Abstract hero background (drop your logo on top)
> Abstract flowing gradient waves in indigo #2C3A94 and azure #128FCD over deep navy #110F26, soft volumetric light, subtle particle bokeh, smooth silky motion-blur ribbons, large empty area in the center for a logo, minimalist, premium medtech aesthetic, 16:9, 4K. No text.

### B7. (Optional) transparent hi-res logo via AI
> You already have vector + transparent PNGs in this package, so you don't need this. If you ever regenerate: "Isolated Zino symbol, two interlocking blue gradient blades, on a pure transparent background, centered, high resolution, no shadow, no background." (Then remove background if the tool can't do true alpha.)

### Prompt hygiene
- Always name the exact hex values so colors stay on-brand.
- Add "leave clear/empty space for the logo" to any mockup you'll overlay the real vector onto (sharper than AI-rendered logos).
- For UI mockups, prefer overlaying the real `zino-symbol.svg` afterward rather than trusting AI to draw the logo correctly.
