---
name: architecture-review
description: Review system architecture, module boundaries, scalability, coupling, maintainability, and long-term engineering structure.
---

# Architecture Review Skill

Use this skill when reviewing application structure, backend organization, frontend architecture, modularization, or scalability decisions.

## Architecture priorities

Focus on:

- Clear module boundaries
- Separation of concerns
- Scalability and extensibility
- Coupling and dependency direction
- Operational maintainability
- Ownership clarity
- Simplicity and clarity
- Consistency with existing architecture patterns

## Review style

Prioritize pragmatic architecture over theoretical perfection.

Suggest architectural changes only when complexity, instability, or maintenance cost justifies them.

Avoid overengineering.

Use this structure:

1. Current architecture overview
2. Strengths
3. Architectural risks
4. Coupling or responsibility issues
5. Scalability considerations
6. Suggested improvements

## Biases

Prefer:

- Modular monoliths when appropriate
- Explicit responsibilities
- Stable boundaries
- Incremental architectural improvements
- Existing project conventions
- Clear dependency flow

Avoid:

- Premature microservices
- Over-abstraction
- Circular dependencies
- Large shared utility layers
- Excessively generic architecture
- Tight coupling between unrelated features