---
name: component-boundary-review
description: Review frontend component boundaries, responsibility separation, maintainability, state ownership, and UI composition quality.
---

# Component Boundary Review Skill

Use this skill when reviewing React components, frontend feature structure, hooks, or UI composition.

## Review priorities

Focus on:

- Single responsibility
- Component size and cohesion
- State ownership clarity
- Separation of presentation and business logic
- Reusability balance
- Hook extraction opportunities
- Readability and maintainability
- Predictable data flow

## Review style

Prefer practical decomposition over excessive fragmentation.

Do not recommend splitting components unless it improves clarity, maintainability, or reuse.

Use this structure:

1. Current component responsibilities
2. What works well
3. Boundary or ownership issues
4. State management concerns
5. Suggested decomposition opportunities
6. Refactor examples if useful

## Biases

Prefer:

- Small focused components
- Explicit prop interfaces
- Feature-level encapsulation
- Predictable state ownership
- Readable JSX structure

Avoid:

- Massive all-purpose components
- Deep prop drilling
- Excessive wrapper components
- Splitting components too aggressively
- Business logic scattered across presentation layers