# Velocity Starter for Temlis Pipeline

This project is the Velocity Astro 6 + Tailwind v4 starter adapted as the Temlis Figma-to-website pipeline.

## Always Read

For Figma-to-code, token, component, or pipeline work, read:

- `docs/temlis-pipeline/velocity-architecture.md`
- `.claude/rules/velocity-architecture.md` for Claude workflows
- `.codex/rules/velocity-architecture.md` for Codex workflows
- The phase rule matching the work being performed

The `.claude/rules/*` and `.codex/rules/*` files are not magic unless a command, skill, or agent imports or summarizes them. Keep those references explicit.

## Token Architecture

- `src/styles/tokens/primitives.css`: OKLCH primitive color scales.
- `src/styles/tokens/typography.css`: fluid type scale, line-height, tracking, weights.
- `src/styles/tokens/spacing.css`: fixed 4px base scale plus semantic section/container/content spacing.
- `src/styles/tokens/borders.css`: semantic border widths and colors.
- `src/styles/themes/default.css`: semantic colors, fonts, shadows, radii, heading/body defaults.
- `src/styles/global.css`: Tailwind v4 `@theme` bridge and global utilities.

Stable structure:

- Keep the base spacing scale `--space-1` through `--space-96`.
- Keep the import cascade and `@theme` bridge.
- Change token values for each Figma project, not the architecture.

## Core Rules

- Use Tailwind classes generated from Velocity tokens.
- Do not use legacy em scaling, `--size-container`, `--size-font`, `--size-container-ideal`, or `--container-padding`.
- Prefer semantic utility classes: `py-space-section-lg`, `px-space-container-xl`, `gap-space-content-md`, `gap-space-heading`, `border-heavy`, `border-border-strong`.
- Use `.container` for centered layout and semantic inline padding.
- Reuse existing `src/components/ui/` components before creating new ones.
- Extract repeated Figma patterns into `ui` or `blocks`, then compose sections in `sections`.
- Use CVA for reusable component variants and `cn()` from `src/lib/cn.ts` for class merging.
- Figma MCP/source-of-truth first: inspect design context and screenshots before building.

## Pipeline

- `/brief`: Phase 0, create `PROJECT_BRIEF.md` and map tokens.
- `/build`: Phases 0-5, build from Figma.
- `/qa`: Phase 3/4 QA and responsive hardening.

Codex equivalent workflow lives in `.codex/AGENTS.md` and `.codex/skills/`. Claude equivalent workflow lives in `.claude/agents/`, `.claude/rules/`, and `.claude/commands/`.
