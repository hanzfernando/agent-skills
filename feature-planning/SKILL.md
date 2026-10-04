---
name: feature-planning
description: Plan features, workflow changes, schema or architectural modifications, and major refactors when requirements, scope, compatibility, or implementation direction need decisions. Use before or during implementation to resolve consequential uncertainty; not routine fixes with clear expected behavior.
---

# Feature Planning

## Goal

Establish enough shared understanding to choose a sound implementation without turning planning into a gate. Investigate available project context first. Ask only when unresolved uncertainty would materially change behavior, scope, data, security, architecture, or user experience; otherwise state reasonable assumptions and proceed.

## Planning workflow

1. Define the problem, users, workflow, desired outcome, and measurable success.
2. Inspect existing behavior, conventions, constraints, affected systems, and ownership.
3. Identify missing requirements, edge and failure cases, compatibility needs, and operational expectations.
4. Test the proposed solution against simpler alternatives and the option of no change.
5. Compare viable directions by complexity, risk, reversibility, migration cost, and future maintenance.
6. Recommend the smallest incremental path that solves the current need and name its assumptions.

Consider, where relevant: API contracts, schema and data ownership, authorization and privacy, performance and scale, state management, UI states and accessibility, observability, rollout/rollback, tests, and integration impact.

## Acceptance criteria

Use existing acceptance criteria or define observable success for the behavior being planned, including material failure cases. Keep small changes brief; a separate spec or approval step is not required. Resolve vague criteria ("works well", "handles errors") through project evidence or focused clarification before committing to dependent behavior.

## Clarification behavior

Ask small, high-impact, implementation-relevant questions, grouped when useful. Do not overwhelm the user with theoretical or low-consequence questions. If a missing answer makes implementation risky, explain the decision it controls. Avoid speculative abstractions and commitments based only on hypothetical future requirements.

## Planning output

Adapt the depth to the change. Capture current understanding, material unknowns or assumptions, affected behavior, options and tradeoffs, risks, acceptance criteria, and a recommended next step. Omit sections that add no decision value.
