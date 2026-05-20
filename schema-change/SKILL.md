---
name: schema-change
description: Design, implement, migrate, and review database schema changes, Prisma models, migrations, relationships, indexes, constraints, seed data, and backward compatibility. Use when Codex is adding or changing persisted data shapes or API/frontend contracts tied to schema fields.
---

# Schema Change Skill

## Purpose

Use this skill when implementing or reviewing a feature that touches:
- database schema
- Prisma models
- migrations
- indexes
- constraints
- relationships
- enums
- seed data
- API contracts dependent on database fields
- frontend assumptions tied to schema shape

Focus on safe schema evolution, data integrity, migration safety, and maintainable feature design.

---

## Schema Priorities

Focus on:

- Whether the schema change is actually necessary
- Data integrity and consistency
- Backward compatibility with existing data
- Migration safety
- Relationship design
- Indexing strategy
- Query patterns affected by the change
- API response/request contract changes
- Frontend impact
- Seed/dev data updates
- Rollback or recovery concerns

---

## Schema Design Checks

Check:

- Is the new table/field named clearly?
- Is the relationship direction correct?
- Should this be normalized or embedded/config-based?
- Are nullable fields intentional?
- Are defaults safe?
- Are unique constraints needed?
- Are foreign keys and delete behavior correct?
- Are enums stable enough, or should they be lookup/config tables?
- Will this schema support future variations without becoming too generic?

Avoid approving schema changes just because they work locally.

Challenge the design if the feature may create long-term data-model problems.

---

## Migration Safety

Check:

- Existing production data impact
- Required backfills
- Nullable-to-required transitions
- Default values
- Destructive changes
- Column/table renames
- Enum changes
- Index creation on large tables
- Rollback difficulty
- Whether the migration can run safely in production

For risky changes, suggest staged migrations.

Example staged approach:

1. Add nullable column/table
2. Deploy code that writes both old and new shape if needed
3. Backfill existing data
4. Verify reads
5. Enforce NOT NULL / constraints later
6. Remove old fields only after stability

---

## Prisma Checks

Check:

- Prisma model naming consistency
- Relation names
- `onDelete` behavior
- `@unique`, `@@unique`, `@@index`
- Optional vs required fields
- Enum usage
- Generated client impact
- Query changes needed after migration
- Whether `include` / `select` usage may become inefficient

Prefer explicit relation and index design over relying on accidental query behavior.

---

## API and Application Impact

When schema changes affect features, check:

- DTO/request validation
- API response shape
- Frontend type updates
- Form defaults
- Filtering/sorting changes
- Pagination impact
- Authorization checks
- Audit/logging impact
- Existing integrations
- Tests that need updates

Do not review the schema in isolation if application behavior depends on it.

---

## Critical Thinking

Do not immediately agree with the proposed schema.

Ask:

- Is this the simplest model that preserves correctness?
- Is this schema too rigid?
- Is this schema too generic?
- Will this create migration pain later?
- Will this make common queries harder?
- Is the feature logic being pushed into the database shape too early?
- Are we optimizing for current requirements while leaving reasonable room for extension?

Provide tradeoffs when there are multiple valid designs.

---

## Output Structure

Use this structure:

1. Summary
2. Schema impact
3. Migration risks
4. Data integrity concerns
5. Application/API impact
6. Suggested schema improvements
7. Safer migration plan, if needed
8. Final recommendation

---

## Severity Labels

Use these labels when helpful:

- Critical: data loss, unsafe migration, broken production behavior, security impact
- Major: poor relationship design, missing constraint, likely scalability issue
- Minor: naming, consistency, small maintainability concern
- Suggestion: optional improvement or future-proofing idea

---

## Biases

Prefer:

- Safe incremental migrations
- Explicit constraints
- Clear relationship ownership
- Practical normalization
- Query-driven index design
- Backward-compatible changes
- Simple schema shapes that match real requirements
- Preserving useful comments and migration context

Avoid:

- Destructive migrations without backup/backfill strategy
- Overly generic JSON blobs for structured relational data
- Over-normalizing simple feature data
- Using enums for values likely to change often
- Adding nullable fields without clear meaning
- Removing comments or migration notes instead of updating them
- Schema changes without considering API/frontend impact
- Stacking migration patches without understanding the root issue
