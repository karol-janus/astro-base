---
name: temlis-brief
description: Use for Phase 0 of the Temlis pipeline: extract the first Figma page/frame and map design tokens into Velocity token files and PROJECT_BRIEF.md.
---

# Temlis Brief

Read:

1. `.codex/rules/velocity-architecture.md`
2. `.codex/rules/phase-0-brief.md`

Workflow:

1. Detect available Figma metadata, design-context, and screenshot tools.
2. Inspect the first page/frame from the Figma URL.
3. Extract colors, typography, spacing, borders, radii, shadows, fonts, frame width, and reusable patterns.
4. Map values into existing Velocity token files only.
5. Ensure `src/styles/global.css` bridges tokens to Tailwind utility classes.
6. Create `PROJECT_BRIEF.md` with the required mapping contract.

Stop if Figma tooling is unavailable. Do not invent design data.
