---
name: code-quality
description: Guide implementation, refactoring, and review for readable, maintainable code. Use when Codex is writing or changing code, shaping architecture within a feature, balancing DRY, naming things, handling errors, preserving existing patterns, or reviewing code quality.
---

# Code Quality Skill

## Purpose

Use this skill when implementing or reviewing:
- code changes
- pull requests
- feature branches
- refactors
- architectural implementations

Focus on practical engineering quality and long-term maintainability.

---

## Quality Priorities

Focus on:

- Readability and intent clarity
- Maintainability over cleverness
- Consistent naming and folder structure
- Balanced DRY, avoiding both duplication and over-abstraction
- Separation of concerns
- Type safety and validation
- Error handling and edge cases
- Small focused functions/components
- Consistency with existing project conventions

---

## Implementation Behavior

Be direct but constructive.

Do not only follow the first implementation idea. Challenge choices when there is a simpler, safer, or more maintainable alternative.

Question assumptions when architectural, performance, or maintainability concerns exist.

Provide tradeoffs instead of blindly validating decisions.

Prefer evidence-based reasoning over confirmation.

Avoid default agreement without analysis.

Prefer actionable comments over vague feedback.

---

## Output Structure

Use this structure when appropriate:

1. Summary
2. What looks good
3. Issues found
4. Suggested improvements
5. Optional refactor examples

---

## Severity Labels

Use these labels when helpful:

- Critical: likely bug, security risk, data loss, broken behavior
- Major: maintainability, performance, or architecture problem
- Minor: naming, formatting, or readability issue
- Suggestion: optional improvement

---

## Engineering Biases

Prefer:

- Simple readable code
- Explicit business logic
- Clear module boundaries
- Existing project patterns
- Small refactors
- Root-cause analysis over repeated temporary fixes
- Re-evaluating assumptions when incremental fixes repeatedly fail
- Considering alternative approaches if complexity becomes excessive
- Updating outdated comments instead of removing contextual documentation
- Preserving implementation intent when refactoring code

Avoid:

- Premature abstraction
- Excessive helper functions
- Large all-purpose utilities
- Clever code that hides intent
- Rewriting everything when a targeted change is enough
- Stacking patches without understanding the underlying issue
- Removing useful comments or documentation without replacing them with updated context
- Deleting explanatory comments during refactors without preserving intent clarity
