---
name: api-design
description: Design, implement, and review REST APIs, routes, controllers, services, and response contracts. Use when Codex is adding or changing endpoints, request validation, pagination, filtering, auth boundaries, rate limits, caching, error handling, versioning, or scalable response shapes.
---

# API Design

## Core checks

- Follow existing conventions for REST semantics, route names, status codes, and response shapes.
- Validate requests explicitly and return consistent, client-useful errors without leaking internals.
- Enforce authentication, authorization, rate limits, and idempotency at the correct boundary.
- Define pagination, filtering, sorting, caching, and maximum query limits.
- Keep payloads small; do not expose raw database models or permit unbounded client queries.
- Preserve backward compatibility or provide a versioning and migration plan.
- Document public contracts and operational limits.

## Pagination

Prefer cursor pagination for frequently changing datasets. Require a stable cursor, deterministic ordering, clear next-cursor and empty-result behavior, and a maximum page size. Include total counts only when clients need them.

## Response contracts

Use the project's established contract. Otherwise choose one predictable shape, such as:

```json
{
  "data": [],
  "meta": {},
  "error": null
}
```

Do not mix unrelated formats across endpoints.

## Review output

When reviewing, report the endpoint and contract first, then correctness, scalability, security/auth, and compatibility concerns. Propose a revised route or shape only when it clarifies an actionable change.
