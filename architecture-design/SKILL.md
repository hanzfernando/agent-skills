---
name: architecture-design
description: Design, implement, refactor, and review system architecture, module boundaries, dependency direction, scalability, coupling, maintainability, and long-term engineering structure. Use for backend organization, frontend architecture, modularization, or cross-cutting feature changes.
---

# Architecture Design Skill

Use this skill when implementing or reviewing application structure, backend organization, frontend architecture, modularization, scalability decisions, domain boundaries, or major cross-cutting changes.

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
- Domain modeling and business boundaries
- Evolutionary improvement over large rewrites

## Architectural influences

Apply architectural thinking inspired by:

### Martin Fowler

- Evolutionary architecture
- Incremental refactoring
- Monolith-first thinking
- Reducing accidental complexity
- Practical tradeoff analysis
- Architectural fitness over theoretical purity

### Robert C. Martin

- Dependency direction
- Separation of concerns
- Boundary protection
- High cohesion and low coupling
- Testability
- Clear responsibility ownership

### Sam Newman

- Service boundary design
- Distributed system tradeoffs
- Operational simplicity
- Avoiding premature microservices
- Team ownership considerations
- Failure-aware architecture

### Vaughn Vernon

- Domain-Driven Design principles
- Bounded contexts
- Aggregate consistency boundaries
- Ubiquitous language
- Domain-focused modularization

### Michael Nygard

- Resilience patterns
- Stability under failure
- Operational readiness
- Reliability considerations
- Production-oriented design decisions

Do not blindly follow any individual methodology.

Use their principles as decision-making tools while optimizing for the actual constraints, team size, system complexity, operational requirements, and existing architecture.

## Architecture style

Prioritize pragmatic architecture over theoretical perfection.

Suggest architectural changes only when:

- Complexity is increasing
- Responsibilities are unclear
- Coupling is becoming problematic
- Scalability concerns are emerging
- Maintenance cost is increasing
- Operational risk is growing
- Team velocity is suffering

Prefer incremental improvements over large-scale rewrites whenever possible.

Always evaluate whether the proposed solution is simpler than the problem it solves.

## Review structure

Use this structure when performing architecture reviews:

### 1. Current architecture overview

Describe:

- Existing architecture style
- Module organization
- Dependency flow
- Responsibility distribution
- Important architectural decisions

### 2. Strengths

Identify:

- Well-defined boundaries
- Effective abstractions
- Good dependency direction
- Strong scalability characteristics
- Maintainability advantages

### 3. Architectural risks

Identify:

- Hidden complexity
- Scalability bottlenecks
- Tight coupling
- Fragile dependencies
- Operational risks
- Future maintenance concerns

### 4. Coupling and responsibility issues

Evaluate:

- Cross-module dependencies
- Circular dependency risks
- Shared ownership concerns
- Responsibility leakage
- Boundary violations

### 5. Scalability considerations

Analyze:

- Growth constraints
- Team scalability
- Operational scalability
- Data ownership concerns
- Performance implications
- Future extensibility

### 6. Suggested improvements

Recommend:

- Incremental refactors
- Boundary improvements
- Dependency cleanup
- Responsibility clarification
- Simplifications
- Scalability enhancements

Explain:

- Why the change is valuable
- What problem it solves
- Tradeoffs introduced
- Implementation complexity
- Migration strategy if needed

## Decision framework

When evaluating architecture decisions:

1. Understand current constraints first.
2. Optimize for maintainability before theoretical purity.
3. Prefer explicitness over cleverness.
4. Protect stable business logic from volatile dependencies.
5. Minimize unnecessary coupling.
6. Avoid introducing abstractions without proven need.
7. Consider operational impact alongside code structure.
8. Prefer designs that are easy for future developers to understand.
9. Design for current scale while allowing reasonable growth.
10. Favor reversible decisions whenever possible.

## Biases

Prefer:

- Modular monoliths when appropriate
- Evolutionary architecture
- Explicit responsibilities
- Stable module boundaries
- Domain-oriented design
- High cohesion
- Low coupling
- Incremental refactoring
- Existing project conventions
- Clear dependency flow
- Operational simplicity
- Vertical slice architectures where appropriate
- Facade/contract patterns for cross-module access
- Clear ownership boundaries

Avoid:

- Premature microservices
- Over-abstraction
- Circular dependencies
- Large shared utility layers
- Excessively generic architecture
- Tight coupling between unrelated features
- Shared databases without ownership boundaries
- Unnecessary framework-driven complexity
- Big-bang rewrites
- Architectural purity at the expense of delivery