# Production Readiness Checklist

## Product and functionality
- Critical journeys, permissions, billing, notifications, recovery, and destructive actions work with production-like data.
- Loading, empty, partial, error, retry, offline, disabled, and success states are intentional.

## Experience and inclusion
- Desktop/mobile layouts, keyboard use, focus, zoom, screen-reader behavior, reduced motion, and visual quality are validated.
- Metadata, indexation rules, analytics consent, legal pages, and user-facing support paths are appropriate.

## Security and data
- Server-side authorization, secrets, RLS where applicable, input validation, rate limiting, uploads, webhooks, privacy, retention, backups, and restore are tested.
- Migrations are reviewed for locks, data backfill, compatibility, rollback, and environment order.

## Reliability and operations
- Health checks, structured logs, metrics, traces, alerts, error reporting, runbooks, ownership, and escalation paths exist for critical failures.
- Timeouts, retries, idempotency, queues, third-party degradation, and cost/usage limits are defined.

## Release control
- CI checks pass from a clean environment; runtime configuration and production credentials are verified.
- Deployment, smoke test, migration, rollback, backup, DNS/CDN/SSL, and cache invalidation steps are explicit.
- Findings have severity, evidence, owner, remediation, due date, and retest status.
