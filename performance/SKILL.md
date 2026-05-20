---
name: performance
description: Implement, optimize, and review frontend and backend performance. Use when Codex is handling React re-renders, query waterfalls, expensive calculations, caching, pagination, large payloads, database queries, charts, dashboards, or unnecessary work.
---

# Performance Skill

Use this skill when implementing, optimizing, or reviewing code for performance, especially React, Next.js, Node.js APIs, dashboards, charts, and frequently updated data.

## Frontend checks

Check for:

- Unnecessary React re-renders
- Unstable object, array, or function references
- Incorrect `useEffect`, `useMemo`, and `useCallback` dependencies
- Expensive calculations inside render
- Overuse of memoization where it reduces readability
- Large components doing too many responsibilities
- Duplicate API requests
- Query waterfalls
- Poor TanStack Query keys or cache strategy
- Inefficient list rendering
- Heavy chart re-renders
- Unnecessary global state usage

## Backend checks

Check for:

- N+1 queries
- Missing pagination
- Inefficient filtering or sorting
- Missing database indexes for common access patterns
- Large response payloads
- Unnecessary joins/includes/selects
- Repeated computation that could be cached
- Rate limit pressure
- Blocking or sequential async work that can be parallelized safely

## Performance style

Do not suggest optimization just because it is possible.

Only recommend optimization when there is likely user impact, scaling risk, excessive resource use, or simpler code.

Use this structure:

1. Main performance risks
2. Evidence or reason
3. Suggested fix
4. Trade-off

## Biases

Prefer:

- Measurable improvements
- Stable references only when they matter
- Server-side filtering/pagination
- Small focused memoization
- Proper cache keys
- Reduced payload size

Avoid:

- Memoizing everything
- Premature optimization
- Hiding logic inside too many abstractions
- Client-side processing of large datasets when the server can do it better
