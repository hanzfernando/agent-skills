---
name: api-design-review
description: Review REST API design for consistency, pagination, filtering, validation, rate limiting, caching, error handling, versioning, and scalable response shapes.
---

# API Design Review Skill

Use this skill when reviewing API routes, controllers, services, response contracts, public APIs, or backend endpoint design.

## API design checks

Check for:

- Clear REST semantics
- Consistent route naming
- Consistent response shapes
- Proper status codes
- Request validation
- Error response consistency
- Authentication and authorization boundaries
- Pagination strategy
- Filtering and sorting conventions
- Rate limit placement
- Caching opportunities
- Idempotency for unsafe operations
- Backward compatibility
- Public API documentation needs

## Pagination

Prefer cursor pagination for frequently updated datasets.

Check:

- stable cursor field
- deterministic sorting
- next cursor behavior
- empty result behavior
- maximum limit enforcement
- total count only when necessary

## Response shape

Prefer predictable response contracts:

```json
{
  "data": [],
  "meta": {},
  "error": null
}
```

or the existing project convention.

Avoid mixing unrelated response formats across endpoints.

## Error handling

Check that errors are:

- consistent
- safe to expose
- useful to clients
- not leaking internals
- mapped to correct HTTP status codes

## Review style

Use this structure:

1. Endpoint summary
2. API contract concerns
3. Scalability concerns
4. Security/auth concerns
5. Suggested revised shape or route, if useful

## Biases

Prefer:

- Consistency over personal preference
- Explicit validation
- Cursor pagination for active datasets
- Small response payloads
- Clear public API contracts
- Practical rate limits

Avoid:

- Returning raw database models
- Inconsistent naming
- Overfetching
- Client-driven unlimited queries
- Breaking existing consumers without versioning or migration plan
