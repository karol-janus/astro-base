# Codex Temlis Pipeline Entrypoint

This repo is Velocity adapted as the Temlis Figma-to-website pipeline. Before any Figma-to-code work, read:

1. `.codex/rules/velocity-architecture.md`
2. The phase rule matching the task
3. `PROJECT_BRIEF.md`, `SITE_MAP.md`, `IMAGE_MANIFEST.md`, or `QA_REPORT.md` when present

## Core Rules

- Use Tailwind classes generated from Velocity tokens.
- Do not use legacy em scaling, `--size-container`, `--size-font`, `--size-container-ideal`, or `--container-padding`.
- Use semantic utilities: `py-space-section-lg`, `px-space-container-xl`, `gap-space-content-md`, `gap-space-heading`, `border-heavy`, `border-border-strong`.
- Use `.container` for centered layout and semantic inline padding.
- Reuse existing UI components first; extract repeated Figma patterns into `ui`, `blocks`, then compose `sections`.
- Figma MCP first: detect available tools, read design context and screenshots, then build. Stop if Figma tooling is unavailable.
- Phase 2 is responsive-first; Phase 4 only hardens edge cases.

## Phases

- Phase 0: `.codex/rules/phase-0-brief.md` and `.codex/skills/temlis-brief/SKILL.md`
- Phase 1: `.codex/rules/phase-1-figma-analysis.md` and `.codex/skills/temlis-figma-analysis/SKILL.md`
- Phase 2: `.codex/rules/phase-2-desktop-build.md` and `.codex/skills/temlis-desktop-build/SKILL.md`
- Phase 3: `.codex/rules/phase-3-desktop-qa.md` and `.codex/skills/temlis-desktop-qa/SKILL.md`
- Phase 4: `.codex/rules/phase-4-responsive.md` and `.codex/skills/temlis-responsive/SKILL.md`
- Phase 5: `.codex/rules/phase-5-seo.md`

Claude slash commands are reference documents here. In Codex, execution is driven by skills and normal conversation instructions.
