---
description: Phase 0 rules for creating PROJECT_BRIEF.md and mapping Figma tokens into Velocity token files.
---

# Phase 0: Velocity Project Brief

Phase 0 extracts the first Figma page/frame and maps the design into the existing Velocity token architecture. It does not create a separate `global.css`, em scaling system, or framework scaffold.

## Required Figma Workflow

1. Detect available Figma MCP/tools for metadata, design context, and screenshot access.
2. Read metadata for the provided Figma URL and identify the first page/frame.
3. Read design context for that page/frame.
4. Capture a screenshot for visual reference.
5. If Figma tools are unavailable, stop and report the missing capability.

## Extract

- Source URL, fileKey, first page, first analyzed frame, and frame width.
- Brand, accent, neutral, text, background, border, and state colors.
- Font families, weights, sizes, line heights, and letter-spacing.
- Spacing patterns for sections, containers, grids, cards, and headings.
- Border widths, border colors, radius values, shadows, and image treatments.
- Reusable component patterns: buttons, cards, badges, inputs, nav items, stats, testimonials, pricing cards, logo items.
- Interactions explicitly present in Figma.

## Token Mapping

Update values in these existing files:

| Figma data | Target |
| --- | --- |
| Brand/accent/grayscale colors | `src/styles/tokens/primitives.css` as OKLCH scales |
| Semantic colors | `src/styles/themes/default.css` |
| Font stacks | `src/styles/themes/default.css` plus `@fontsource-variable/*` imports in `src/styles/global.css` |
| Font scale | `src/styles/tokens/typography.css` and `@theme --font-size-*` bridge |
| Line heights and tracking | `src/styles/tokens/typography.css` |
| Section/container/content spacing | `src/styles/tokens/spacing.css` semantic tokens |
| Spacing utilities | `src/styles/global.css` `@theme --spacing-space-*` bridge |
| Border widths/colors | `src/styles/tokens/borders.css` and `@theme` bridge |
| Shadows/radii | `src/styles/themes/default.css` |
| Frame width | `src/styles/global.css` `--container-max` |

The base spacing scale `--space-1` through `--space-96` stays fixed. Only semantic spacing changes per project.

## Tailwind Bridge Requirement

Verify that token files feed Tailwind classes through `@theme`. Required examples:

```css
@theme {
  --font-size-3xl: var(--text-3xl);
  --spacing-space-section-lg: var(--space-section-lg);
  --spacing-space-container-xl: var(--space-container-xl);
  --spacing-space-content-md: var(--space-content-md);
  --border-width-heavy: var(--semantic-border-width-heavy);
  --color-border-strong: var(--border-color-strong);
}
```

## Output: PROJECT_BRIEF.md

Create `PROJECT_BRIEF.md` at the project root with:

- Figma source URL, fileKey, first analyzed page/frame, and screenshot reference.
- Color mapping from Figma to `primitives.css` and `themes/default.css`.
- Font mapping to `@fontsource-variable` packages/imports and `--theme-font-*`.
- Typography mapping to `--text-*`, `--leading-*`, `--tracking-*`, and `@theme --font-size-*`.
- Spacing mapping to `--space-*` semantic tokens and utility classes.
- Border, radius, and shadow decisions.
- Component inventory and recommended destinations (`ui`, `blocks`, `sections`).
- Figma fidelity exceptions that cannot cleanly map to existing tokens.

## Prohibited Legacy Work

- Do not create or use `--size-container-ideal`.
- Do not create or use `--size-font`.
- Do not create or use `--container-padding`.
- Do not convert design values to em.
- Do not relocate or replace `src/styles/global.css`.
