# Design

## Visual Theme

"Engineer's bench" — instrument-panel precision. The portfolio of someone who designs PCBs and writes firmware, expressed through exact geometry, technical diagrams, and committed color. Light and dark themes, both first-class.

## Color Palette (OKLCH)

Strategy: **Committed** — violet-blue carries identity, not a 5% garnish.

Light theme:
- `--bg`: oklch(0.985 0.002 264) — near-white, hint of cool
- `--surface`: oklch(0.96 0.006 270)
- `--ink`: oklch(0.18 0.02 270) — near-black violet-cast
- `--ink-2`: oklch(0.42 0.03 270) — secondary text (≥4.5:1 on bg)
- `--accent`: oklch(0.5 0.23 275) — deep violet
- `--accent-2`: oklch(0.55 0.2 255) — electric blue
- `--line`: oklch(0.88 0.01 270)

Dark theme:
- `--bg`: oklch(0.16 0.015 275) — deep violet-black (not pure black; the violet cast IS the brand)
- `--surface`: oklch(0.21 0.02 275)
- `--ink`: oklch(0.95 0.01 270)
- `--ink-2`: oklch(0.72 0.02 270)
- `--accent`: oklch(0.75 0.14 275) — lifted violet for contrast
- `--accent-2`: oklch(0.78 0.12 250)
- `--line`: oklch(0.3 0.02 275)

No gradient text. Accent used solid: headings' key words, data values, links, diagram strokes.

## Typography

- **Display/headings**: Archivo (variable, weight 500–800, width axis for display). Machined-signage grotesque — precise without being sterile.
- **Data/labels/code**: JetBrains Mono (400/600). Used for spec values, chip designators, dates, tags — his literal material, never decoration.
- Body: Archivo 400/450. Max 70ch.
- Scale: fluid clamp(), ratio ≥1.25. Display max 5.5rem. Letter-spacing floor -0.03em.
- `text-wrap: balance` on headings.

## Imagery

Custom inline SVG technical diagrams — precise, grid-aligned, stroke-based:
- PCB trace pattern (hero backdrop, subtle)
- Lander/rover geometric line art + PCB motif (NASA project)
- Trapezoidal commutation waveform (BLDC project)
- Soil-moisture signal bars (SolarSENSE)
- SCARA 2-link kinematic diagram (robot arm)
No sketchy/doodle styles. All diagrams stroke `currentColor`/accent, consistent 1.5px weight.

## Components

- Featured project: full-width, diagram left / copy right, spec-value row
- Secondary projects: compact rows with inline diagram thumbnails (not identical cards)
- Experience: single-column timeline, mono dates
- Buttons/links: solid accent, scale(0.97) on :active, 160ms ease-out
- Theme toggle: sun/moon, instant swap (no theme transition animation on toggle > 200ms)

## Motion

- Custom curves: `--ease-out: cubic-bezier(0.23,1,0.32,1)`; `--ease-io: cubic-bezier(0.77,0,0.175,1)`
- Hero: one orchestrated entrance (staggered 60ms, translateY 12px + opacity, 500ms)
- Scroll reveals: content visible by default, enhanced via IntersectionObserver adding transform-from state only when JS+motion allowed
- UI interactions ≤ 250ms
- `prefers-reduced-motion`: opacity-only fallbacks

## Layout

- Max width 1120px, fluid gutters clamp(20px, 5vw, 64px)
- Section spacing varies: hero full-viewport, projects generous, experience tighter rhythm
- No repeated section-eyebrow grammar; sections open with the heading itself
