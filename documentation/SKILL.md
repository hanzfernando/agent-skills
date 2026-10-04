---
name: documentation
description: Write, update, restructure, and review technical documentation for clarity, onboarding, setup reproducibility, operational usefulness, API references, architecture notes, and engineering communication quality.
---

# Documentation

## Priorities

- Write for the reader's task and likely familiarity with the system.
- Keep instructions accurate, concise, scannable, and reproducible.
- For procedures, state prerequisites, commands, expected outcomes, and relevant failure recovery or operational risks.
- Organize content from common paths to advanced or exceptional cases.
- Explain acronyms and necessary domain terms; remove jargon and detail that do not help the task.
- Use realistic examples where they resolve ambiguity.
- Verify claims against implementation and configuration; check links and safely runnable examples. Mark unverified steps and blockers instead of claiming reproducibility.

## Matching the doc to its job

Identify which kind of document is needed before writing, since each has a different job:

- **README** — orientation and getting-started; keep it short and link out rather than absorbing everything.
- **Runbook / operational doc** — task-oriented for on-call or ops use; lead with the steps, not the background.
- **API reference** — generated or kept in sync with the implementation (OpenAPI/Swagger) where possible, rather than hand-maintained prose that drifts.
- **Architecture note / ADR** — records a decision and its context for future readers, not a how-to.

Use a table, numbered procedure, or diagram when it communicates the reader's task more clearly; request flows, boundaries, and state machines often benefit from diagrams.

## Keeping docs live

Use the project's documentation source of truth; prefer versioning with code when location is open to choice. Link to canonical contracts and decisions rather than duplicating them.

## Reviews

Assess correctness and missing information before prose style. Identify ambiguous steps, hidden assumptions, onboarding or operational risks, and maintenance concerns. Locate issues by file/section, explain the reader impact, and recommend concrete edits. Use rewritten examples only when they improve clarity.
