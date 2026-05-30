---
description: Run the Velocity/Temlis Figma-to-website pipeline.
argument-hint: [figma-url]
---

# Build Pipeline

Run the Temlis pipeline for `$ARGUMENTS`.

## Preflight

1. Read `docs/temlis-pipeline/velocity-architecture.md`.
2. Detect available Figma metadata, design-context, and screenshot tools.
3. Verify the Figma URL is usable.
4. If Figma tools are unavailable, stop with a clear message.

## Phases

1. Phase 0: create `PROJECT_BRIEF.md` and map Figma tokens into Velocity token files.
2. Phase 1: create `SITE_MAP.md` and `IMAGE_MANIFEST.md`.
3. Pre-Phase-2 validation: every section needs a `nodeId` and screenshot reference.
4. Phase 2: build responsive-first sections from Figma design context and screenshot data.
5. Phase 3: run QA and update `QA_REPORT.md`.
6. Phase 4: responsive hardening.
7. Phase 5: SEO/accessibility/content pass.
8. Final: run `pnpm check`, `pnpm build`, then `pnpm dev` for preview.

Between phases, verify the project still compiles when practical.
