---
name: architecture-design
description: Design, implement, refactor, and review system structure when module ownership, dependency direction, integration boundaries, deployment topology, or cross-cutting changes require architectural decisions. Use for modularization and evidence-backed scaling decisions; not localized cleanup within established boundaries.
---

# Architecture Design

## Priorities

- Define cohesive modules, explicit responsibilities, ownership, and dependency direction.
- Protect stable business logic from volatile frameworks and integrations.
- Optimize for maintainability, operational simplicity, testability, and current constraints.
- Design for present scale with reasonable growth in product, data, operations, and teams.
- Follow existing architecture unless its costs justify change.
- Prefer reversible, incremental improvements over speculative abstractions or rewrites.

## Decision process

1. Map the current structure, dependency flow, responsibility distribution, constraints, and important existing decisions.
2. Identify concrete pressure: unclear ownership, harmful coupling, scaling limits, operational risk, or rising maintenance cost.
3. Compare the smallest viable options, including leaving the design unchanged.
4. Evaluate code, data, deployment, failure, migration, team-ownership, and compatibility tradeoffs.
5. Recommend the simplest option whose benefit exceeds its implementation and migration cost.

Always ask whether the proposed architecture is simpler than the problem it solves. Avoid premature microservices, circular dependencies, broad shared utility layers, shared data without ownership, framework-driven complexity, and big-bang rewrites. Prefer modular monoliths, vertical slices, bounded contexts, and facades/contracts when they fit the evidence—not by default.

## Backend pattern toolkit

Name a pattern when it clarifies a concrete structural choice. Common options and when they earn their cost:

- **Modular monolith / vertical slices** — simple in-process boundaries for a new system; in an existing system, compare incremental boundary improvements against restructuring.
- **Event-driven / message queue** — when work is naturally async, needs to survive downstream outages, or must fan out to multiple independent consumers.
- **CQRS** — when read and write load, shape, or scaling needs diverge significantly; adds real complexity, so require clear evidence.
- **Service-per-database / bounded-context data ownership** — when two teams or domains are contending over the same tables with conflicting change cadence.

Treat these as options to weigh against "no change," not defaults to reach for.

## Decision records

For architecturally significant changes, capture the decision, context, alternatives considered, and consequences — in the project's existing ADR location/format if one exists, otherwise as a short note alongside the change. This matters most when the choice is hard to reverse.

## Influences

Use these as lenses, not authorities:

- Martin Fowler: evolutionary design, incremental refactoring, and practical tradeoffs.
- Robert C. Martin: dependency direction, cohesion, boundary protection, and testability.
- Sam Newman: service boundaries, distributed-system costs, failure modes, and team ownership.
- Vaughn Vernon: bounded contexts, aggregates, ubiquitous language, and domain-oriented modules.
- Michael Nygard: resilience, stability, and operational readiness.

## Architecture reviews

Structure substantial reviews around:

1. Current architecture and strengths
2. Risks, boundary violations, and ownership/coupling issues
3. Scalability and operational implications
4. Prioritized improvements

Identify affected modules or code locations, evidence, benefit, tradeoffs, and migration path. Verify dependency direction and affected flows after implementation stages. Omit empty sections; distinguish observed problems from future risks.
