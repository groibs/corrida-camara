# Corrida da Câmara — Design System

A visual identity system for **Corrida da Câmara** ("Chamber Run"), a civic
street-race event. The brand mixes the formality of a public/government
sponsor with the celebratory energy of a road race: bold condensed
wordmark, a confetti pattern of arcs and diamonds, and a six-color
high-saturation palette.

> "Corrida" = race · "Câmara" = chamber (legislative council).
> Likely a 5K/10K civic event hosted by a municipal Câmara.

## Source materials

All inputs are originals uploaded by the user (Portuguese-language assets).
Stored in `uploads/` for reference and copied/curated into `assets/`.

| Source file | What it is |
| --- | --- |
| `uploads/logo 1.png` | Primary logo — green + magenta pattern, black wordmark on white |
| `uploads/logo 2.png` | Alt logo — orange + purple pattern variant |
| `uploads/logo 3.png` | Logo lockup on cyan background |
| `uploads/logo 4.png` | Primary logo (clean white bg) |
| `uploads/logo 5.png` | Green + purple pattern on cyan |
| `uploads/logo 6.png` | Green + purple pattern variant |
| `uploads/logo 7.png` | Orange + purple pattern on lime green background |
| `uploads/Prancheta 1.png` | Logo lockup on orange background |
| `uploads/paleta de coresv.png` | Official 6-swatch color palette |
| `uploads/Apresentação.pdf` | *(Referenced but not present in `uploads/` — see Caveats)* |

No codebase, Figma file, or product copy was provided — this is an
**event identity system**, not a product. The system is therefore
optimized for: event posters, social campaigns, registration sites,
race-bib numbering, results screens, and slide decks.

---

## Index

| File / Folder | Purpose |
| --- | --- |
| `README.md` | This file — brand fundamentals, content, visuals, iconography |
| `SKILL.md` | Agent-skill entrypoint (for Claude Code / skill loaders) |
| `colors_and_type.css` | All CSS variables + semantic type classes |
| `assets/logos/` | All logo variants (primary, color-pairs, on-color) |
| `assets/palette-reference.png` | Original color-dot reference |
| `preview/` | Small HTML cards rendered in the Design System tab |
| `ui_kits/event-site/` | Event registration / results landing page |
| `slides/` | Sample slide templates in the brand voice |

---

## CONTENT FUNDAMENTALS

The brand only ships a handful of marks and a palette — no body copy was
provided. The recommendations below are inferred from the **visual tone**
(loud, sporty, civic-celebratory) and from conventions of Brazilian
municipal running events.

### Voice
- **Language**: **Portuguese (Brazil)** as primary. English as optional
  secondary for international visitors. Never mix mid-sentence.
- **Tone**: Energetic, inviting, civic-warm. Treat the reader as a
  participant ("você") not a spectator. Communal, not corporate.
- **Pronouns**: **"Você"** (you) and **"nós / a gente"** (we/us). Use
  imperatives generously — running brands earn the right to say "vai",
  "corre", "inscreva-se", "bora".

### Casing
- **Wordmark + display headlines**: ALL CAPS. Heavy, condensed, shouty —
  it matches the heaviness of the logo and the energy of a starting gun.
- **Body**: Sentence case. Never all-caps body copy — it kills legibility.
- **Eyebrows / labels / buttons**: ALL CAPS with `letter-spacing: .12em`.
- **Numerals (times, distances, bib numbers)**: Always tabular and large.
  Race times = the hero data.

### Examples (illustrative — confirm with stakeholder before shipping)
- Hero: **"CORRE COM A GENTE."** ("Run with us.")
- Hero alt: **"5K · 10K · ZERO DESCULPAS."** (date-stamped)
- Section eyebrow: **PERCURSO** / **INSCRIÇÕES** / **RESULTADOS**
- CTA: **INSCREVA-SE** · **VER O PERCURSO** · **BAIXAR KIT**
- Microcopy: "Largada às 7h. Café e água no fim. Traz o crachá."
- Confirmation: "Você está dentro. ✓"
- Empty state: "Os resultados aparecem aqui assim que a primeira pessoa
  cruzar a linha."

### Emoji & symbols
- **Emoji**: avoid in headlines and official communications. Allowed
  sparingly in social copy (🏃 🏁 🥇) but never as a substitute for an
  icon in product UI.
- **Unicode glyphs as decoration**: yes — `·` (middle dot) is the brand's
  unofficial separator between distance, date, and city: `5K · 10K · 12.10`.
  An arrow `→` is fine for "next" cues.
- **The "Â" accent over CÂMARA** is treated as a graphic element — it's
  colored separately in the wordmark and is sometimes drawn as a tiny
  chevron/runner-pennant. Preserve this when possible.

### Numbers, dates, units
- Dates: `DD.MM.AAAA` (Brazilian) — e.g. `12.10.2026`. Spell month in
  prose: `12 de outubro`.
- Distances: `5K`, `10K`, never `5km` in display copy. Body copy: `5 km`.
- Times: `00:42:18` (HH:MM:SS), monospaced, tabular.
- Currency: `R$ 89,90`.

### Vibe in one line
> The energy of confetti at a finish line, with the seriousness of a
> public-institution stamp. Loud, civic, communal — never corporate.

---

## VISUAL FOUNDATIONS

### Colors
A six-color high-chroma palette (see `assets/palette-reference.png` and
`colors_and_type.css` for the canonical tokens):

| Token | Hex | Role |
| --- | --- | --- |
| `--brand-lime` | `#a3ef15` | **Primary** — hero surfaces, CTAs, accent highlight on "Â" |
| `--brand-cyan` | `#22acdd` | Secondary surface, sport/water |
| `--brand-orange` | `#f58a1f` | Energy accent, finish-line warmth |
| `--brand-magenta` | `#e9118c` | Confetti highlight, links, attention |
| `--brand-purple` | `#5c2d90` | Depth, contrast, civic-formal counterweight |
| `--brand-black` | `#131313` | Wordmark, primary text |

**Pairing rules:**
- Lime + magenta = primary energy pair (logo default).
- Orange + purple = secondary "carnival" pair (logo alt).
- Cyan as a backdrop is allowed but should never carry the wordmark in
  cyan — black wordmark holds the lockup.
- Black is always the wordmark and the body-text color. White is the
  cleanest surface.
- Never combine more than 3 brand colors in one composition (excluding
  black + white).

### Typography
Brand wordmark is a **heavy, slightly condensed, blocky display sans**
with cropped/cut terminals. The closest free substitutes are:
- **Big Shoulders Display Black (900)** — display / hero
- **Archivo Black** — secondary headlines
- **Barlow** — body, UI, sport-utility neutral
- **JetBrains Mono** — race times, bib numbers, results tables

> ⚠️ **Substitution flag.** The original wordmark is a custom or licensed
> face — we are approximating with Google Fonts. Please supply the
> licensed font file (TTF/OTF) if you have it; drop into `fonts/` and
> we'll swap the `@font-face` rules in `colors_and_type.css`.

**Type rules:**
- Display headlines ALWAYS uppercase, weight 900, line-height ~0.9.
- Body never goes below 14px on screen. On race materials, ≥18px.
- Numerals (timing/bibs) tabular and monospaced — never proportional.

### Backgrounds
- **Solid color fields** are the default — full-bleed brand colors
  (lime, cyan, orange, magenta, purple). No gradients in standard use.
- **Pattern fill**: the confetti pattern (arcs + diamond shards) is the
  brand's signature texture. Use it as a header band, a divider, or
  oversized full-bleed at hero scale. Never tile it small.
- **No photos with overlays**, no `bg-noise.png` grain, no mesh
  gradients, no glassmorphism.
- **Imagery** (when added later) should be high-saturation, daylight,
  warm-leaning event photography — runners, crowds, finish lines. Not
  studio. Not desaturated.

### Layout
- Hard-cornered, grid-driven. Wordmark is rectangular and chunky — the
  layouts echo that with strong horizontal bands and big numeric blocks.
- Generous whitespace around the wordmark — clearspace = the height of
  the "C" in CORRIDA, minimum.
- Asymmetric is welcome. Confetti can break out of frames.
- Default page max-width on web: 1280px content / 1440px chrome.

### Corner radii
- **Cards, panels, hero surfaces**: `0` — square edges match the wordmark.
- **Buttons / chips / badges**: pill (`999px`) — softens CTAs against
  the otherwise sharp grid.
- **Inputs**: `8px` for friendliness without going pill.
- Never mix radii inside a single component (don't pill the button but
  round-rect the icon next to it).

### Borders & strokes
- 2px solid black for outlined components — strong, poster-like.
- Hairline `1px rgba(19,19,19,.10)` for utility dividers in tables.
- No dashed/dotted borders.

### Shadows & elevation
- Mostly flat. Soft shadow only for floating UI (modals, tooltips):
  `--shadow-md` / `--shadow-lg`.
- **Hard offset shadow** `6px 6px 0 var(--brand-black)` is a signature
  affordance for primary CTAs and poster cards — gives a sport-print
  feel.
- No inner shadows. No glow.

### Buttons
- **Primary**: lime fill, black text, pill, no shadow OR hard-offset
  black shadow on poster surfaces. Hover: shadow disappears + 2px nudge
  down/right (the "press" feel).
- **Secondary**: white fill, 2px black border, black text, pill.
- **Tertiary / link**: magenta underlined text.
- Disabled: `--bg-3` fill, `--fg-4` text, no shadow, cursor not-allowed.

### Hover & press
- Hover: subtle — translate `-1px` on Y or remove the hard shadow.
  Never opacity-only.
- Press: shadow collapses to `0 0`, button translates `+2px,+2px`
  (poster-press effect). 120ms.
- Focus ring: `0 0 0 3px var(--brand-cyan)` outside the element.

### Animation
- **Easing**: `cubic-bezier(.2,.9,.25,1)` — slight kickback, sport-feel.
- Durations 120/200/360ms. Avoid anything over 400ms in product UI.
- Acceptable motions: arc/diamond confetti drift on hero, ticker scrolls
  for sponsor strips, count-up animations for race times.
- No parallax. No fade-in-on-scroll for body text.

### Transparency & blur
- Avoid both. The brand is opaque and graphic. The only allowed
  semi-transparent surface is the on-image text protection scrim
  (linear gradient `rgba(19,19,19,.0) → .55`).

### Cards
- White surface, 0 radius, 2px black border OR hard-offset shadow.
- Never both border and shadow on the same card.
- Internal padding: 24px minimum.

---

## ICONOGRAPHY

No proprietary icon set was provided with the source materials. Approach:

- **Logo + pattern marks** (the confetti arcs and diamonds) act as the
  brand's signature visual vocabulary. Use them as decorative dividers,
  background tiles, and section anchors before reaching for an icon.
- **No emoji** in product UI. Allowed in social copy only.
- **Unicode `·` `→` `✓` `★`** are acceptable as inline glyphs.
- **For UI iconography** (chevrons, search, hamburger, share, download,
  pin, calendar, clock, map), we link **Lucide** from CDN — a clean
  2px-stroke open-source set that pairs well with Barlow body text and
  doesn't fight the bold display face.

  > ⚠️ **Substitution flag.** Lucide is **not** the brand's official icon
  > set (none was provided). If a different set is preferred (Phosphor,
  > Heroicons, or a custom one), drop SVGs into `assets/icons/` and
  > update this section.

- Icon sizing: `20px` inline with body, `24px` for affordances, `32px`
  for hero/feature icons. Stroke 2px. Color follows text color.
- Icons are never colorized with brand colors in body UI — they inherit
  text. Brand color on icons is reserved for hero/feature moments.

---

## CAVEATS

- `Apresentação.pdf` was referenced in the brief but **not present** in
  the uploaded files at `uploads/`. If a slide template was intended,
  please re-attach and we'll fold its conventions into `slides/`.
- The wordmark face is **a substitution** (Google Fonts: Big Shoulders
  Display). Please share the original `.ttf`/`.otf` if available.
- No product UI, codebase, or Figma file was attached — only marks +
  palette. The "ui_kits/event-site" kit is therefore an inferred
  registration/results template, not a recreation. Please confirm
  direction.
- **No icon set** was provided; Lucide is a sensible neutral substitute.
- **Voice + copy examples** above are inferred from the brand's visual
  energy and Brazilian municipal race conventions — they need a
  stakeholder pass for accuracy.
