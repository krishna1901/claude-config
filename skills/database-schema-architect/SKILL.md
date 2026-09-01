---
name: database-schema-architect
description: "Design relational schemas, constraints, indexes, migrations, transactions, tenancy, and query patterns; not for general API design or Supabase platform setup alone."
---

# Database Schema Architect

## Activation conditions

Primary outcome: Encode domain invariants and query needs in a durable relational model with safe evolution and access control.

Use this skill when:

- New entities, relationships, constraints, indexes, or migrations are needed.
- A schema has integrity, tenancy, retention, or performance problems.
- Supabase tables require RLS and policy design.

Do not use this skill when:

- The task is UI-only.
- A local query can be fixed without changing data shape or access policy.

## Required workflow

1. Inspect schema, migrations, query plans, policies, and representative data.
2. Model entities, keys, relationships, cardinality, lifecycle, and invariants.
3. Define types, nullability, defaults, constraints, uniqueness, and audit fields.
4. Design indexes from real query patterns and write amplification trade-offs.
5. Specify transaction, concurrency, soft-delete, retention, and multi-tenant behavior.
6. Design safe expand/contract migrations, backfills, compatibility windows, forward-fix or restore recovery, and backups.
7. For Supabase, implement and test RLS plus trusted server authorization boundaries.

## Skill-specific rules

### Confirm these inputs

- Domain entities, invariants, lifecycle, ownership, and tenancy
- Read/write query patterns, scale, concurrency, and latency needs
- Existing schema, migrations, data quality, backups, and generated types
- Authorization, retention, reporting, and audit requirements

### Apply these decision rules

- Use database constraints for durable invariants.
- Prefer clear normalized models, denormalizing only with evidence.
- Keep tenant and ownership rules explicit.
- Own relational modeling and migration correctness; route Supabase Auth, Storage, Realtime, Edge Functions, CLI, and platform deployment to supabase-architecture-expert.
- Never apply unreviewed destructive migrations to production.

### Resolve these domain decisions

- Encode durable domain invariants with types, constraints, keys, and transactions rather than application convention alone.
- Design indexes from observed query shapes, selectivity, ordering, joins, write volume, and maintenance cost.
- Choose transaction and locking behavior from concurrency conflicts, not from single-request happy paths.
- Use expand-and-contract migrations with compatible application phases for risky type, ownership, or shape changes.
- Test RLS with anonymous, owner, non-owner, cross-tenant, privileged, and service contexts using realistic claims.

### Avoid

- Indexes without query evidence
- Application-only integrity checks
- Nullable fields without domain rationale
- RLS policies tested only as an admin/service role

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.
- Load [../_shared/checklists/production-readiness-checklist.md](../_shared/checklists/production-readiness-checklist.md) only when release, migration, deployment, or operational readiness is in scope.

## Validation steps

- Rehearse forward migration and the chosen recovery path on representative non-production data.
- Prohibit destructive down-migrations that could discard writes made after deployment; prefer expand/contract, forward-fix, or verified restore.
- Test constraints, concurrent writes, cross-tenant denial, and deletion/retention behavior.
- Use EXPLAIN/ANALYZE for critical queries.
- Verify generated types, backups, restore, and deployment order.

## Expected output

- Schema and relationship specification
- Constraints, indexes, transactions, and access policies
- Forward migration, backfill, compatibility, and safe recovery plan
- Query, security, and restore validation evidence
