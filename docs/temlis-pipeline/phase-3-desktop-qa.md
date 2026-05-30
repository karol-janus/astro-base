---
description: Phase 3 rules for QA, fidelity checks, and correction loops.
---

# Phase 3: QA and Auto-Correction

Run this checklist after each section and before moving to the next section.

## Figma Source Check

- Re-read the section `fileKey` and `nodeId` from `SITE_MAP.md`.
- Compare text character-for-character with Figma design context.
- Compare layout, column count, alignment, and image presentation with the Figma screenshot.
- Flag invented elements, copy, animations, transitions, overlays, gradients, and hover effects.

## Velocity Architecture Check

- Uses Tailwind utilities or token-backed CSS variables.
- No legacy `--size-container`, `--size-font`, `--container-padding`, or em conversion.
- Uses `.container` with `--container-max` token for inner layout.
- Uses semantic spacing classes such as `py-space-section-lg`, `px-space-container-xl`, `gap-space-content-md`, and `gap-space-heading`.
- Uses semantic border classes such as `border-heavy`, `border-border-strong`, and `divide-border-muted` when applicable.
- No raw hex colors in components.
- No inline `style` attributes for values achievable with Tailwind or tokens.
- Raw px appears only in token definitions or documented one-off Figma fidelity exceptions.
- Uses `cn()` for class composition where classes are dynamic.
- Uses CVA for reusable component variants.

## Component Extraction Check

- Existing Velocity UI components are reused where applicable.
- Repeated Figma patterns are extracted into `ui` or `blocks`.
- Flag duplicated inline card/item/button/badge/stat/testimonial/logo patterns across two or more sections.

## Responsive Check

- Every section has mobile, tablet, and desktop states after Phase 2.
- No horizontal overflow down to 320px.
- Grids and side-by-side layouts stack predictably.
- Media has stable aspect ratio/cropping and does not overlap text.
- Navigation has a working mobile/collapse state.

## Image Check

- Local image exists under `public/assets/images/`.
- Extension matches detected file type.
- File size is plausible.
- Placeholder usage is documented in `IMAGE_MANIFEST.md`.
- SVG fills are trusted from Figma; remove invented container styling before changing SVG fills.

## QA_REPORT.md Contract

Create or update `QA_REPORT.md` with:

- Sections checked against Figma screenshot/context.
- Differences in text, layout, typography, colors, and assets.
- Raw value exceptions accepted/rejected.
- Component extraction issues.
- Responsive issues per breakpoint.
- Status of fixes and remaining risks.
