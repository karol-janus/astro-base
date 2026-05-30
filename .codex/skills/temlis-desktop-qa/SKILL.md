---
name: temlis-desktop-qa
description: Use for Phase 3 of the Temlis pipeline: QA Figma fidelity, token usage, component extraction, assets, and responsive-first implementation.
---

# Temlis Desktop QA

Read:

1. `.codex/rules/velocity-architecture.md`
2. `.codex/rules/phase-3-desktop-qa.md`
3. `SITE_MAP.md`
4. `IMAGE_MANIFEST.md`

Workflow:

1. Compare each section against Figma design context and screenshot.
2. Verify exact text, layout, typography, colors, assets, and image treatments.
3. Scan for legacy variables, em sizing, raw hex, repeated arbitrary values, and inline styles.
4. Verify semantic utilities such as `py-space-section`, `px-space-container`, `gap-space-content`, and `border-heavy`.
5. Flag duplicated inline patterns that should be extracted.
6. Verify mobile/tablet/desktop states already exist after Phase 2.
7. Write `QA_REPORT.md`.
