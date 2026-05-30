---
description: Set up Keystatic CMS for the current project (Astro or Next.js) — installs packages, writes config, scaffolds Admin UI, wires images, and renders example content end-to-end
argument-hint: [collection-names?]
---

Set up Keystatic CMS for this project.

Args (optional): $ARGUMENTS

Read `.codex/rules/keystatic-reference.md`, then set up Keystatic end-to-end for this Astro project. If `PROJECT_BRIEF.md` exists, use it to suggest collection schemas instead of only installing a boilerplate posts collection. Default storage to local unless the user asks otherwise.

After the agent finishes, summarize for the user:
- Framework + storage mode
- Collections created (names only)
- Admin UI URL
- The example page that proves the loop works
- One-line "next step" suggestion (switch to GitHub for prod, or add more fields)
