---
name: temlis-responsive
description: Use for Phase 4 of the Temlis pipeline: harden responsive edge cases after Phase 2 has already produced responsive sections.
---

# Temlis Responsive Hardening

Read:

1. `.codex/rules/velocity-architecture.md`
2. `.codex/rules/phase-4-responsive.md`
3. `QA_REPORT.md`

Workflow:

1. Test 320, 390, 480, 768, 991, 1024, 1280, and Figma desktop width.
2. Fix overflow, overlap, unstable grids, nav collapse issues, image crop problems, and text fitting.
3. Prefer Tailwind responsive prefixes.
4. Use `max-[991px]:` only for nav collapse or documented Figma exceptions.
5. Update `QA_REPORT.md`.
