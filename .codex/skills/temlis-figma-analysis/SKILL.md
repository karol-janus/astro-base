---
name: temlis-figma-analysis
description: Use for Phase 1 of the Temlis pipeline: analyze routes, sections, assets, and component inventory from Figma.
---

# Temlis Figma Analysis

Read:

1. `.codex/rules/velocity-architecture.md`
2. `.codex/rules/phase-1-figma-analysis.md`
3. `PROJECT_BRIEF.md`

Workflow:

1. Detect available Figma tools and inspect metadata.
2. Use design context and screenshots for every relevant page/section.
3. Create `SITE_MAP.md` with source URL, fileKey, routes, section node IDs, screenshots, assets, and component inventory.
4. Create `IMAGE_MANIFEST.md` with source nodes, export URLs/methods, local paths, file types, sizes, validation status, and placeholder notes.
5. Map repeated patterns to existing Velocity components or recommended `ui`/`blocks`/`sections` destinations.

Every buildable section must have a `nodeId`.
