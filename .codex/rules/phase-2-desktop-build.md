---
description: Phase 2 rules for responsive-first Velocity section builds from Figma.
---

# Phase 2: Desktop Build, Responsive from the Start

Desktop screenshots are the primary fidelity target, but every section must ship with mobile, tablet, and desktop states in the first implementation.

## Required Workflow Per Section

1. Read `SITE_MAP.md` for `fileKey`, source URL, route, and section `nodeId`.
2. Call available Figma design-context tooling for exact text, styles, layout, colors, spacing, and assets.
3. Call available Figma screenshot tooling for visual reference.
4. Build from live Figma data, not summaries or memory.
5. Wire assets from `IMAGE_MANIFEST.md`.
6. Run the Phase 3 checklist before moving to the next section.

## Fidelity Rules

- EXACT TEXT: use character-for-character Figma text.
- NO INVENTED FEATURES: no animations, scroll effects, parallax, hover treatments, gradients, or decorative elements unless present in Figma or requested.
- LAYOUT FROM SCREENSHOT: column count, alignment, stacking, and image treatments must match the screenshot.
- COLORS FROM TOKENS: map Figma colors to Velocity tokens, then use Tailwind classes.
- TYPOGRAPHY FROM TOKENS: use `text-*`, `leading-*`, `tracking-*`, font weights, and theme font stacks.

## Units: Tailwind Utility Classes

Do not use em conversion. Use Tailwind utilities generated from Velocity tokens:

| Figma px | Tailwind class | Source |
| --- | --- | --- |
| 4px spacing | `p-1`, `gap-1` | spacing scale |
| 8px spacing | `p-2`, `gap-2` | spacing scale |
| 12px spacing | `p-3`, `gap-3` | spacing scale |
| 16px spacing/font | `p-4`, `gap-4`, `text-base` | spacing/type tokens |
| 24px spacing/font | `p-6`, `gap-6`, `text-2xl` | spacing/type tokens |
| 32px spacing | `p-8`, `gap-8` | spacing scale |
| 48px spacing/font | `p-12`, `gap-12`, `text-5xl` | spacing/type tokens |
| 64px spacing | `p-16`, `gap-16` | spacing scale |

For non-scale values, add semantic tokens when patterns repeat. Arbitrary values are documented one-off exceptions only.

## Layout Model

```astro
<section class="w-full py-space-section-sm md:py-space-section-md lg:py-space-section-lg bg-background">
  <div class="container">
    <div class="grid grid-cols-1 gap-space-content-md md:grid-cols-2 lg:gap-space-content-lg">
      ...
    </div>
  </div>
</section>
```

Use `.container` for max width and semantic inline padding. Use `invert-section` for dark/contrast sections.

## Responsive-First Contract

- Base classes are mobile-first.
- `sm:`, `md:`, `lg:`, and `xl:` progressively enhance layout.
- Every grid/flex layout must declare breakpoints, for example `grid-cols-1 md:grid-cols-2 lg:grid-cols-3`.
- Every media block must have stable aspect ratio, object-fit, sizes, width constraints, or equivalent responsive constraints.
- Navigation must include its mobile state in the first build. Use `max-[991px]:` only for nav collapse or documented Figma needs.
- Phase 4 is hardening, not the first responsive pass.

## Component Reuse

Before creating markup, check existing Velocity components. Use them where they fit. If a pattern appears in two or more sections, extract it into `ui` or `blocks` before composing `sections`.

Reusable components use CVA for variants and `cn()` for class composition.
