---
name: component-boundaries
description: Design, implement, refactor, and review React component responsibilities, prop contracts, state ownership, hooks, and feature composition. Use when introducing or changing these boundaries; not purely visual styling or handler edits that leave these boundaries unchanged.
---

# Component Boundaries

## Core checks

- Inspect consumers, props, state, and effects before moving responsibilities; preserve identity, resets, and effect cleanup.
- Give components cohesive responsibilities and explicit prop contracts. Keep state at the lowest owner coordinating consumers; derive values rather than duplicating state.
- Separate presentation from business logic when that boundary improves testing or reuse.
- Extract hooks for cohesive stateful behavior, not merely to reduce line count.
- Encapsulate features while following the project's established composition patterns.
- Split components only when it improves clarity, ownership, testing, or demonstrated reuse.

Avoid all-purpose components, scattered business logic, excessive wrappers, and trivial fragmentation. Replace prop drilling only when coordination costs justify composition or context.

## Review output

Identify findings by component and code location, with consequence and smallest useful correction. Include current responsibilities or examples only when they clarify the ownership change.
