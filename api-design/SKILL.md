---
name: api-design
description: Design, implement, and review REST endpoint contracts and HTTP behavior. Use for routes, request validation, response shapes, pagination, filtering, API auth boundaries, rate limits, caching semantics, retry safety, or compatibility; not internal service refactors without contract impact.
---

# API Design

## Core checks

- Inspect affected clients, contract tests, and existing REST conventions before changing routes, status codes, or response shapes.
- Validate requests explicitly and return consistent, client-useful errors without leaking internals.
- Enforce authentication and authorization at the correct boundary; apply rate limits and retry protection where abuse or repeated side effects warrant them.
- For collection endpoints, define pagination, filtering, sorting, and maximum query limits; define caching semantics where relevant.
- Keep payloads small; do not expose raw database models or permit unbounded client queries.
- Preserve backward compatibility or provide a versioning and migration plan.
- Document public contracts and operational limits — use the project's established format (OpenAPI/Swagger) where one exists, and keep it in sync with the implementation.

## Idempotency

For mutations needing retry protection, use the project's mechanism or a client-supplied `Idempotency-Key`. Scope keys by caller/operation, reject mismatched requests, and atomically claim keys before processing concurrent retries. Define replay, in-progress, failure, and expiry behavior. Coordinate records with committed side effects; caching responses alone leaves a duplicate-execution crash window.

## Versioning

Preserve existing versioning. Use a version or migration path for breaking changes; URL paths (`/v1/...`) are a simple option for new public APIs needing versions. Check client compatibility even for additions, especially enum values, stricter validation, and changed defaults.

## Error responses

Use the project's established error shape where one exists. Otherwise, default to a consistent structure distinguishing validation errors (422) from malformed requests (400), auth failures (401/403), and not-found (404), each with a stable machine-readable code plus a human-readable message — never a raw stack trace or internal exception name.

## Pagination

Prefer cursor pagination for frequently changing datasets. Require a stable cursor, deterministic ordering with a unique tie-breaker, clear next-cursor and empty-result behavior, and a maximum page size. Include total counts only when clients need them.

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

Report findings by impact with endpoint, code location, client consequence, and correction. Verify affected success/error contracts and relevant retry or pagination cases. Propose a revised route or shape only when it clarifies the change.
