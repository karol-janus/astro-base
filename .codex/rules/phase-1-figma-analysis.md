---
description: Phase 1 rules for analyzing Figma structure, assets, routes, and component inventory.
---

# Phase 1: Figma Analysis

Phase 1 maps the full Figma file into buildable routes, sections, assets, and reusable components.

## Figma MCP First

Use available Figma tools in this order:

1. Metadata: file structure, pages, and top-level frames.
2. Design context: exact text, styles, layout, components, and asset URLs.
3. Screenshots: visual references for every route/section.

If the runtime has no Figma MCP/tooling, stop with a clear message.

## SITE_MAP.md Contract

Create `SITE_MAP.md` with:

- Figma fileKey and source URL at the top.
- Pages/routes to build.
- For each section: name, route, `nodeId`, section type, screenshot reference, background treatment, local assets, and notes.
- Shared layout dependencies: header, footer, nav, page shell, global wrappers.
- Component inventory with repeated patterns, occurrence counts, recommended destination (`ui`, `blocks`, `sections`), props, variants, and source node IDs.
- Design token summary for colors, typography, spacing, borders, radii, and shadows.

Every buildable section must have a `nodeId`. Phase 2 must never build from prose-only descriptions.

## IMAGE_MANIFEST.md Contract

Create `IMAGE_MANIFEST.md` with:

- Figma layer/node source.
- Export URL from MCP or export method.
- Local path under `public/assets/images/`.
- Detected file type after download.
- File size and validation status.
- Placeholder notes, failed downloads, wrong extensions, SVG placeholders, or rasterization issues.

Use Node.js for batched downloads if shell download tools are blocked. Validate downloaded files with `file` and fix extensions that do not match content type.

## Component Mapping

Before recommending new components, compare Figma patterns to existing Velocity components:

- `src/components/ui/form/Button/`
- `src/components/ui/data-display/Card/`
- `src/components/ui/data-display/Badge/`
- `src/components/ui/data-display/Avatar/`
- `src/components/ui/form/Input/`
- `src/components/ui/overlay/Accordion/`
- `src/components/ui/overlay/Tabs/`
- `src/components/ui/overlay/Dialog/`

Repeated non-generic patterns should become `blocks`; full page bands should become `sections`.
