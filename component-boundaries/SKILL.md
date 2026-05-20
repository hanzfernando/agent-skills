---
name: component-boundaries
description: Design, implement, refactor, and review frontend component boundaries, responsibility separation, maintainability, state ownership, hooks, and UI composition. Use when Codex is building or changing React components, frontend feature structure, or component APIs.
---

# Component Boundaries Skill

Use this skill when implementing or reviewing React components, frontend feature structure, hooks, or UI composition.

## Boundary priorities

Focus on:

- Single responsibility
- Component size and cohesion
- State ownership clarity
- Separation of presentation and business logic
- Reusability balance
- Hook extraction opportunities
- Readability and maintainability
- Predictable data flow

## Implementation style

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
