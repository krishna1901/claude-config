---
name: api-contract-designer
description: "Design or review REST, RPC, GraphQL, server-action, and webhook schemas, errors, pagination, compatibility, and contract tests; not for database modeling alone."
---

# API Contract Designer

## Activation conditions

Primary outcome: Create explicit, evolvable boundaries that make correct behavior testable by independent producers and consumers.

Use this skill when:

- A client, service, webhook, or external integration needs a contract.
- An existing API has ambiguity, compatibility, or error-handling problems.
- Server actions or RPC boundaries carry security or evolution risk.

Do not use this skill when:

- The interface is a local private function with no meaningful boundary.
- The task is database modeling without an API consumer.

## Required workflow

1. Inspect current contracts and consumer behavior.
2. Model resources/operations around domain intent and ownership.
3. Define request/response schemas, validation, auth, authorization, and field semantics.
4. Specify errors, status, idempotency, concurrency, pagination, filtering, sorting, and rate limits.
5. Design versioning, deprecation, compatibility, webhook signing, and replay handling.
6. Generate examples and contract tests for success and failure.
7. Review with consumers and plan safe rollout/migration.

## Skill-specific rules

### Confirm these inputs

- Consumer use cases, actors, permissions, and latency needs
- Domain entities, invariants, workflows, and error cases
- Existing API style, schemas, versions, clients, and deployment constraints
- Rate, scale, compatibility, observability, and documentation requirements

### Apply these decision rules

- Use consistent names and error envelopes.
- Make optional, nullable, omitted, and default semantics explicit.
- Do not expose internal persistence shapes accidentally.
- Keep sensitive authorization server-side per operation.

### Resolve these domain decisions

- Model operations around domain intent and consumer workflows rather than exposing persistence tables directly.
- Specify required, optional, nullable, omitted, defaulted, and deprecated fields without ambiguous overlap.
- Define idempotency key scope, retention, concurrency behavior, replay result, and conflict semantics for mutations.
- Use consistent error categories that preserve safe diagnostics without leaking secrets or internal implementation detail.
- Plan additive evolution, consumer rollout, observability, deprecation, and removal before publishing a breaking contract.

### Avoid

- Happy-path-only schemas
- Using HTTP 200 for every outcome
- Breaking consumers without rollout strategy
- Trusting client-provided ownership or role

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.
- Load [../_shared/checklists/production-readiness-checklist.md](../_shared/checklists/production-readiness-checklist.md) only when release, migration, deployment, or operational readiness is in scope.

## Validation steps

- Validate schemas and examples mechanically where tooling exists.
- Test malformed, unauthorized, forbidden, duplicate, stale, paginated, and rate-limited requests.
- Run producer/consumer contract tests.
- Verify backward compatibility and rollout order.

## Expected output

- Contract specification and examples
- Error, auth, pagination, idempotency, and compatibility rules
- Contract test suite or cases
- Versioning and migration plan
