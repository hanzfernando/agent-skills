---
name: schema-change
description: Design, implement, migrate, and review persisted data shapes, database constraints, indexes, Prisma models, and data backfills. Use when schema or stored-data changes affect queries, deployment compatibility, or dependent application contracts; not API/frontend-only field changes that leave persistence unchanged.
---

# Schema Change

## Design checks

- Inspect schema, migration history, queries, and existing data; confirm the change matches persistence and lifecycle needs.
- Use clear names, explicit ownership, intentional nullability/defaults, and appropriate normalization.
- Define foreign keys, cardinality, uniqueness, delete behavior, and consistency boundaries.
- Choose enums only for stable values; avoid opaque JSON for structured relational data.
- Design indexes from actual reads, filters, sorts, joins, and uniqueness requirements.
- Preserve room for known variation without making the model prematurely generic.

Challenge both rigid and over-general designs. Compare alternatives when they materially affect correctness, query complexity, migration safety, or maintenance.

## Migration safety

Inspect generated migration SQL, not only model diffs. Assess data quality/volume, locks and deployment duration, backfills/defaults, constraint transitions, renames, destructive or enum changes, large-table indexes, and mixed-version compatibility. Validate affected constraints, backfills, and recovery on representative data in a safe environment.

For risky changes, use an expand-and-contract sequence where applicable:

1. Add the compatible nullable field, table, or parallel shape.
2. Deploy compatible reads/writes; dual-write only when required and define reconciliation.
3. Backfill in bounded, observable batches.
4. Verify data and application reads.
5. Enforce required constraints after compatibility is proven.
6. Remove the old shape in a later release with a recovery plan.

Require recovery for data removed by destructive changes; a backfill alone is insufficient. Distinguish schema rollback from data restoration and account for writes made after deployment.

## Prisma checks

Verify model/relation names, optionality, `onDelete`, `@unique`, `@@unique`, `@@index`, enum stability, generated-client impact, and `select`/`include` query cost. Prefer explicit relations and indexes over accidental behavior.

## Application impact

Trace changes through DTO and request validation, API contracts, authorization, frontend types and defaults, filters/sorts/pagination, integrations, seed/dev data, audit/logging, generated artifacts, and tests. Do not review the schema in isolation.

## Reviews

Lead with data-loss, production-safety, integrity, and compatibility findings. Locate each actionable finding in the schema, migration, or caller and explain the failure and correction. Then cover model quality, query/index implications, and application impact. Provide a staged migration plan when risk warrants it. Label severity only when useful:

- **Critical:** data loss, unsafe deployment, broken production behavior, or security impact.
- **Major:** integrity, relationship, compatibility, or likely scale problem.
- **Minor:** localized naming or maintainability concern.
- **Suggestion:** optional improvement.
