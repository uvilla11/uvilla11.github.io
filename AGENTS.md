# AGENTS.md

## What this is

A single-file static portfolio site (`index.html`, ~780 lines). All HTML, CSS, and JS live in that one file. No build system, no framework, no dependencies, no package.json.

## How to preview

Open `index.html` directly in a browser, or:

```bash
open index.html          # macOS
python3 -m http.server   # then visit localhost:8000
```

## Structure

- `index.html` — the entire site: HTML structure, inline `<style>`, inline `<script>`
- `DESIGN.md` — visual theme, color palette (OKLCH), typography, motion decisions
- `PRODUCT.md` — brand voice, audience, design principles, anti-references
- `*.md`, `*.pdf`, `*.jpeg`, `*.png` — resume, capstone reports, posters, project assets (linked from the site, not part of the build)

## Architecture

- **Theme**: `data-theme="dark"` on `<html>` toggles dark mode. Stored in `localStorage`. CSS custom properties under `[data-theme=dark]` swap the palette.
- **Routing**: Hash-based (`#detail/nasa-psyche`, `#blog/hall-effect-positioning`, etc.). Detail pages and blog posts are hidden `<article class="page">` elements toggled by JS. No router library.
- **Animations**: Scroll-driven where possible (native `animation-timeline:scroll()`). `IntersectionObserver` drives `.reveal` → `.in` transitions. All motion respects `prefers-reduced-motion: reduce`.
- **WebGL**: A GLSL shader runs on `<canvas id="webgl-bg">` behind the hero — flowing PCB-trace-like lines responding to mouse position. Degrades to CSS gradient if WebGL unavailable.
- **Particles**: Canvas 2D particle system on `<canvas id="particles-canvas">` — ambient drifting particles. Hidden on touch devices and reduced motion.
- **Custom cursor**: Three-layer cursor (dot + ring + label). Hidden on touch devices (`@media(hover:none)`). Grows on interactive elements.
- **SVGs**: Inline, stroke-based technical diagrams. All use `currentColor`/accent. No external image files for diagrams.

## Conventions to follow

- Colors are OKLCH, defined as CSS custom properties in `:root` and `[data-theme=dark]`. Accent is violet-blue — never random.
- Typography: Archivo (headings/body), JetBrains Mono (data/labels/specs). Mono is for literal material, never decoration.
- Animations: Use custom easing vars (`--ease-out`, `--ease-quart`, etc.). Check `REDUCE` and `HOVER` JS vars before attaching motion. Max interactive transitions ≤250ms.
- Accessibility: `prefers-reduced-motion` kills all movement (opacity-only fallbacks). Keyboard-accessible `[data-href]` rows get `tabindex=0` + `role="button"`. Focus-visible outline on all interactive elements.
- No gradient text. No decorative imagery. Technical diagrams are the imagery.

## Routes

| Hash | Content |
|------|---------|
| `#` or empty | Home page (default) |
| `#work`, `#experience`, `#about`, `#blog`, `#contact` | Scroll to section |
| `#detail/nasa-psyche` | NASA Psyche project detail |
| `#detail/solarsense` | SolarSENSE project detail |
| `#detail/shadeshift` | ShadeShift project detail |
| `#detail/microgrid` | Microgrid project detail |
| `#detail/room-weather` | Room Weather project detail |
| `#blog/hall-effect-positioning` | Blog: Hall-Effect Positioning |
| `#blog/tinyml-on-8bit` | Blog: TinyML on 8-Bit MCU |
| `#blog/kicad-pcb-walkthrough` | Blog: KiCad PCB Walkthrough |
| `#blog/questioning-xendee` | Blog: Questioning XENDEE Results |

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `j` / `k` | Navigate between project rows |
| `Enter` | Open focused project |
| `Esc` | Go back / close overlay |
| `/` | Focus first project row |
| `?` | Toggle keyboard shortcuts overlay |
| `t` | Toggle theme |

## Gotchas

- Adding a new project means: (1) a `.row` in `#work` with `data-categories` and optional `data-href`, (2) an `<article id="detail-*">` page, (3) a `data-href` link on the row. The hash router handles the rest.
- Adding a new blog post means: (1) a `.blog-card` in `#blog` with `data-href="#blog/slug"`, (2) an `<article id="blog-slug">` page.
- The site has no transpilation — write modern JS that works in current browsers only.
- WebGL shader is in GLSL (inline in JS). The fragment shader uses `precision highp float` and `#version 300 es` for WebGL2, falls back to WebGL1.
- Footer says "HAND-BUILT, NO FRAMEWORK" — keep it that way.
- The contact form uses Formspree (`xpzvwdav`). Replace the form ID if switching services.
