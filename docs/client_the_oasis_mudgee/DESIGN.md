# The Oasis Mudgee — Approved Demo Direction A

## Intent

Create a quiet, premium bridge between discovery and the existing Timely booking flow. The page must explain the brand and stable service categories before asking a visitor to leave for live availability.

## Brand invariants

- Preserve the supplied official logo without redrawing or restyling it.
- Preserve exactly: “A sanctuary for self-love, specialising in all things beauty and wellness.”
- Preserve the three stable service labels:
  - Advanced facials & massage
  - Lashes, brows & waxing
  - Makeup, tanning & nails
- English is the merchant-facing page language.
- Do not invent reviews, qualifications, awards, prices, availability or staff claims.

## Visual system

- Direction: A — editorial split hero, followed by a light service story.
- Palette:
  - Obsidian: `oklch(0.13 0.012 325)`
  - Paper: `oklch(0.985 0.004 75)`
  - Ink: `oklch(0.19 0.012 325)`
  - Mulberry: `oklch(0.38 0.105 350)`
  - Mist: `oklch(0.93 0.006 75)`
- Display type: Tenor Sans; body type: Source Sans 3; robust system fallbacks included.
- Shape language: precise rectangular panels, circular light motif, hairline rules, restrained 2px–4px radii.
- Imagery: original generated editorial stills only; neutral white, obsidian and deep mulberry; no people, labels or client material.

## Layout and responsive behaviour

- Desktop hero: 43/57 split, black brand panel on the left and room image on the right.
- Service section: three alternating image/text bands with generous white space.
- Care section: dark editorial statement with an orbit motif; no fake social proof.
- Contact section: location, verified public channels and Timely boundary.
- Mobile: stacked hero, compact navigation, image crops remain legible, persistent bottom booking action.

## Motion and accessibility

- One restrained hero entrance and subtle in-view reveals for service media.
- No continuous decorative motion. `prefers-reduced-motion` disables transitions.
- Semantic landmarks, keyboard-visible focus, high contrast, 44px minimum actionable targets.

## External-system boundary

The page owns brand, trust, service understanding and contact context. Timely owns live menu detail, prices and availability. The demo has no CMS, database, form handler, payment, account or booking implementation.
