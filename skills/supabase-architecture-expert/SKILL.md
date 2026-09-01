---
name: supabase-architecture-expert
description: "Implement or design Supabase Auth, Postgres, Storage, Realtime, Edge Functions, RLS, migrations, and types; not for database work unrelated to Supabase."
---

# Supabase Architecture Expert

## Activation conditions

Primary outcome: Use Supabase capabilities with explicit trust boundaries, reproducible migrations, and least-privilege access.

Use this skill when:

- Supabase Auth, Database, Storage, Realtime, or Edge Functions are being designed or changed.
- RLS, migrations, generated types, performance, or deployment safety needs review.
- A Supabase-backed feature needs end-to-end implementation.

Do not use this skill when:

- The project does not use Supabase.
- The task is frontend-only and no Supabase behavior changes.

## Required workflow

1. Inspect repository configuration and current Supabase resources before editing.
2. Map actors, tokens, trust boundaries, ownership, and data paths.
3. Design schema, constraints, indexes, migrations, and generated type flow.
4. Implement RLS policies and server authorization; isolate service-role use.
5. Configure Auth, Storage, Realtime, and Edge Functions with explicit failure behavior.
6. Test locally using representative roles and production-like data.
7. Plan deployment order, safe migration recovery, observability, performance, and backup/restore using expand/contract, forward-fix, verified restore, or proven non-destructive rollback.

## Skill-specific rules

### Confirm these inputs

- Supabase project/local config, CLI and client versions
- Schema, migrations, policies, functions, buckets, auth providers, and generated types
- Actors, roles, ownership, tenancy, data flows, and threat model
- Deployment environments, observability, performance, and backup requirements

### Apply these decision rules

- Deny by default and test with real user tokens.
- Treat RLS as the mandatory primary database authorization boundary for every client-accessible table or view.
- Require trusted server and Edge Function paths to authorize independently; isolate service-role keys and never use them to bypass user authorization casually.
- Own Supabase Auth, Storage, Realtime, Edge Functions, CLI workflow, and platform deployment; use database-schema-architect for deep relational modeling and query design.
- Use migrations as the source of truth.

### Resolve these domain decisions

- Treat RLS as the primary database authorization boundary for every client-accessible relation and storage path.
- Use service-role access only in trusted code after independent authorization; never forward it to clients.
- Keep SQL migrations, generated types, local development, and environment promotion reproducible and reviewable.
- Define realtime channel ownership, event volume, reconnection, stale state, and authorization before subscribing broadly.
- Specify Storage paths, ownership, MIME and size limits, signed URL lifecycle, and cleanup before accepting uploads.

### Avoid

- Disabling RLS for convenience
- Exposing service-role credentials
- Dashboard-only changes without migrations
- Testing policies only through privileged clients

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.
- Load [../_shared/checklists/production-readiness-checklist.md](../_shared/checklists/production-readiness-checklist.md) only when release, migration, deployment, or operational readiness is in scope.

## Validation steps

- Run Supabase-specific lint/tests and migration checks.
- Test anonymous, authenticated, owner, non-owner, admin, and cross-tenant access.
- Verify storage paths, signed URLs, realtime subscriptions, and function auth/error behavior.
- Rehearse generated types, query plans, deployment order, and the chosen safe recovery path on non-production data; prohibit destructive down-migrations that could discard post-deploy writes.

## Expected output

- Production Supabase implementation
- Schema/RLS/storage/function decisions
- Role-based test evidence
- Migration, deployment, safe recovery, and operations notes
