---
description: Phase 4 responsive hardening rules.
---

# Phase 4: Responsive Hardening

Phase 4 does not create responsive behavior from scratch. Phase 2 sections must already work on mobile, tablet, and desktop. This phase hardens edge cases.

## Checkpoints

- Test 320px, 390px, 480px, 768px, 991px, 1024px, 1280px, and the Figma desktop width.
- Fix horizontal overflow, cropped content, overlapping text, unstable media, and broken nav states.
- Use Tailwind responsive prefixes as the primary mechanism.
- Use `max-[991px]:` only for nav collapse or documented Figma exceptions.
- Keep semantic spacing tokens as the main section rhythm.

## Output

Update `QA_REPORT.md` with responsive findings, fixes, screenshots if available, and remaining risks.
