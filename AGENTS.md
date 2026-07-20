# AGENTS.md

## What this is

A dependency-free, single-page portfolio for embedded-systems and robotics engineer Uriah Villa. All production HTML, CSS, and JavaScript live in index.html; there is no package manager, framework, or build step.

## Preview

Open index.html directly in a current browser, or serve the folder with any static HTTP server.

## Source structure

- index.html — the complete site, including four routed case studies
- DESIGN.md — visual direction and interaction principles
- PRODUCT.md — audience, voice, and product requirements
- PDF, PNG, and JPEG files — original portfolio evidence and project artifacts
- Markdown files — source reports and historical documents; these are reference material, not polished public pages

## Architecture

- Theme: data-theme="light|dark" on the HTML element, initialized before paint and stored in localStorage when available.
- Home navigation: standard fragment links such as #work, #experience, and #contact.
- Case routing: minimal hash router for #case/psyche, #case/solarsense, #case/shadeshift, and #case/microgrid.
- Views: one persistent main landmark contains the home view and every case article. The router exposes exactly one view at a time, updates the title, and moves or restores focus.
- Motion: one hero entrance, viewport reveals, and a scroll-progress line. All respect prefers-reduced-motion.
- Contact: Formspree endpoint xpzvwdav, with verified HTTP success and a truthful visible error fallback.
- Mobile navigation: native details menu; desktop navigation remains native anchors.

## Design rules

- The art direction is a restrained “flight-test dossier”: authentic artifacts, exact typography, hairlines, measured values, and clear system boundaries.
- Colors use OKLCH custom properties for light and dark themes.
- Archivo is the primary typeface; JetBrains Mono is reserved for literal data, labels, and technical metadata.
- No gradient text, fake loaders, particle systems, WebGL backgrounds, magnetic controls, marquees, animated counters, or continuous decorative loops.
- Project evidence must be real. Do not publish reconstructed technical details or unsupported performance claims.
- Clearly distinguish course prototypes, simulations, partner projects, and professional employment.
- Public case-study images need intrinsic dimensions, useful alt text, and lazy loading when below the fold.

## Routes

| Hash | Content |
|---|---|
| # or empty | Home |
| #work | Selected work |
| #experience | Professional experience and education |
| #builds | Additional builds |
| #about | Biography and capability matrix |
| #archive | Evidence archive |
| #contact | Contact |
| #case/psyche | ASU Capstone × NASA Psyche |
| #case/solarsense | SolarSENSE |
| #case/shadeshift | ShadeShift |
| #case/microgrid | Critical-facility microgrid study |

## Conventions

- Use native anchors for navigation and native controls for actions.
- Keep one visible main landmark and preserve route focus behavior.
- Maintain WCAG AA contrast, visible focus, semantic headings, and reduced-motion behavior.
- Prefer existing local assets and inline SVG diagrams over new dependencies.
- The academic source documents may be stale or contradictory. When updating facts, reconcile them with Uriah before promoting a number or role claim.
- Keep the footer claim “HAND-BUILT · NO FRAMEWORK” true.

## Adding a case study

1. Add a native link using href="#case/slug".
2. Add an article with class="case-page", id="case-slug", and a data-title inside #casePages.
3. Follow the existing structure: brief, facts, ownership, decisions, validation, limitations, and artifacts.
4. Base every technical statement on a supplied source or a user-confirmed fact.

## Before handoff

- Run a JavaScript syntax check on the final inline script.
- Check duplicate IDs, fragment targets, local asset paths, image alt text, and new-tab rel values.
- Test home anchors, every case route, browser Back, keyboard focus, mobile navigation, both themes, reduced motion, and form failure behavior.
