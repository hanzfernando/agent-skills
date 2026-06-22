---
name: performance
description: Implement, optimize, and review frontend and backend performance. Use when Codex is handling React re-renders, query waterfalls, expensive calculations, caching, pagination, large payloads, database queries, charts, dashboards, or unnecessary work.
---

# Performance

## Principle

Optimize only where measurements, user impact, scale risk, or excessive resource use justify it. Establish a baseline and bottleneck before adding complexity; preserve readability and correctness.

## Frontend checks

- Unnecessary renders, unstable references, and expensive render-time work
- Incorrect hook dependencies or memoization whose cost exceeds its benefit
- Duplicate requests, waterfalls, weak query keys, or unsuitable cache/staleness behavior
- Inefficient large-list, chart, and frequently updating UI rendering
- Overbroad global state or components with unrelated responsibilities
- Bundle, network, and client-side processing costs

## Backend checks

- N+1 queries, missing query-driven indexes, and inefficient filters, sorts, joins, or selections
- Missing pagination, unbounded work, and oversized payloads
- Repeated computation or requests that suit bounded caching
- Blocking work or independent async operations serialized unnecessarily
- Rate-limit, memory, CPU, connection, and cache-invalidation pressure

Prefer server-side filtering and pagination, focused memoization, stable cache keys, and reduced payloads. Avoid memoizing everything, moving large data work to clients, or hiding optimizations behind excessive abstraction.

## Reporting

For each material issue, state the evidence or expected impact, proposed change, tradeoff, and how to measure success. Distinguish measured bottlenecks from plausible risks.
