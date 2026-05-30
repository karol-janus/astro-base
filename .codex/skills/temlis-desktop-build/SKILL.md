---
name: temlis-desktop-build
description: Use for Phase 2 of the Temlis pipeline: build responsive-first Velocity sections from Figma MCP data using Tailwind token utilities.
---

# Temlis Desktop Build

Read:

1. `.codex/rules/velocity-architecture.md`
2. `.codex/rules/phase-2-desktop-build.md`
3. `PROJECT_BRIEF.md`
4. `SITE_MAP.md`
5. `IMAGE_MANIFEST.md`

Workflow for each section:

1. Read `fileKey` and `nodeId` from `SITE_MAP.md`.
2. Call available Figma design-context tooling.
3. Call available Figma screenshot tooling.
4. Check existing Velocity UI components before writing markup.
5. Extract repeated patterns into `ui` or `blocks`.
6. Build with Tailwind utilities from tokens, not raw CSS/em values.
7. Include mobile, tablet, and desktop states in the first pass.
8. Update `QA_REPORT.md` with known exceptions or risks.

Stop if Figma tooling or required section references are missing.
