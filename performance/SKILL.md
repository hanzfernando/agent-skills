---
name: performance
description: Investigate, optimize, and review frontend or backend latency, throughput, rendering, and resource use. Use for measured or suspected bottlenecks, query waterfalls, costly renders, unbounded work, or caching and pagination decisions driven by workload; not every query, chart, or dashboard change.
---

# Performance

## Principle

Optimize only where measurements, user impact, scale risk, or excessive resource use justify it. Establish a baseline and bottleneck before adding complexity; preserve readability and correctness.

## Measurement workflow

1. Use existing profiling, APM, or query logs, or the lightest suitable tool. Start query inspection with `EXPLAIN`; `EXPLAIN ANALYZE` executes statements, so assess side effects and load before using it.
2. Identify the actual bottleneck before changing code — don't optimize the first slow-looking line.
3. Compare before/after costs under equivalent data, load, and cache conditions, using the metric relevant to user impact. If measurements are unavailable, label estimates and state how to validate them.
4. Treat a change as unjustified if it adds complexity without a measured or clearly reasoned improvement.

## Frontend checks

- Unnecessary renders, unstable references, and expensive render-time work
- Incorrect hook dependencies or memoization whose cost exceeds its benefit
- Duplicate requests, waterfalls, weak query keys, or unsuitable cache/staleness behavior
- Inefficient large-list, chart, and frequently updating UI rendering
- Overbroad global state or components with unrelated responsibilities
- Bundle, network, and client-side processing costs

## Backend checks

- N+1 queries, missing query-driven indexes, and inefficient filters, sorts, joins, or selections
- Missing pagination, unbounded work, and oversized payloads — respect existing defaults; choose enforced maximums from payload/query costs and client contracts
- Repeated computation or requests that suit bounded caching with explicit freshness and invalidation
- Blocking work, serialized independent operations, or unbounded concurrency that overloads dependencies
- Rate-limit, memory, CPU, connection, and cache-invalidation pressure

Prefer server-side filtering and pagination, focused memoization, stable cache keys, and reduced payloads. Avoid memoizing everything, moving large data work to clients, or hiding optimizations behind excessive abstraction.

## Reporting

For each material issue, identify the code/query location, evidence or expected impact, proposed change, tradeoff, and success metric. Distinguish measured bottlenecks from plausible risks.
