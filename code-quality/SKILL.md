---
name: code-quality
description: Improve code readability and maintainability during refactors, code reviews, or implementation with consequential choices about naming, control flow, duplication, abstraction, error handling, or test seams. Use for local code structure; routine edits alone do not require this skill.
---

# Code Quality

## Priorities

- Make intent, business rules, names, and control flow easy to understand.
- Follow project conventions and preserve intended behavior; challenge patterns with demonstrated correctness or maintenance costs.
- Keep functions, components, and modules cohesive with clear boundaries.
- Balance duplication against abstraction; abstract only when it makes change safer or clearer.
- Preserve type safety, validation, error handling, and edge-case behavior.
- Prefer targeted, root-cause fixes over clever code, broad rewrites, or stacked patches.
- Update useful comments and documentation when behavior changes; do not discard context casually.

## Testability

Write code so behavior can be tested without excessive mocking — favor pure functions, explicit dependencies, and clear seams between business logic and I/O. Use existing tests to protect refactors; add tests for changed logic or uncovered risks, proportional to the change and project expectations. Inspect dependency seams when testing needs excessive mocking.

## Working behavior

Before a refactor, inspect callers and tests for behavior that must survive, including error and side-effect ordering. Evaluate alternatives when the first implementation is complex, fragile, or inconsistent. Challenge assumptions with evidence and explain material tradeoffs. Avoid excessive helpers, generic utility layers, and abstractions that hide intent.

## Reviews

Lead with actionable findings ordered by impact; include file or code locations and explain the consequence and suggested correction. Use severity labels only when they improve prioritization:

- **Critical:** likely broken behavior, security exposure, or data loss.
- **Major:** significant maintainability, performance, or architecture risk.
- **Minor:** localized readability, naming, or consistency issue.
- **Suggestion:** optional improvement.

After findings, summarize strengths or refactor examples only when useful. Do not manufacture findings to fill a template.
