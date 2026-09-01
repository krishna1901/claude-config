---
name: background-jobs-notification-architect
description: "Design or implement scheduled jobs, queues, retries, idempotency, workers, email, push, and delivery recovery; not for synchronous request handling alone."
---

# Background Jobs Notification Architect

## Activation conditions

Primary outcome: Ensure asynchronous work and user communications are durable, observable, consent-aware, and recoverable.

Use this skill when:

- Work must execute later, on a schedule, or outside request latency.
- Push/email notifications need preferences, delivery tracking, or retries.
- Existing jobs suffer duplicates, silent failure, timezone, or provider issues.

Do not use this skill when:

- A fast synchronous operation is simpler and reliable enough.
- The task is UI-only with no delivery or job behavior.

## Required workflow

1. Inspect current job, provider, scheduler, and notification flows.
2. Define job state machine, payload contract, idempotency, deduplication, concurrency, and ordering.
3. Set timeout, retry, jittered backoff, dead-letter, cancellation, and recovery behavior.
4. Model time zones, daylight saving, catch-up, missed runs, and schedule changes.
5. Design channel preferences, consent, templates, localization, provider abstraction, and delivery logs.
6. Add admin inspection/replay controls with authorization and audit.
7. Load-test, failure-inject, monitor, and document operations.

## Skill-specific rules

### Confirm these inputs

- Job triggers, payloads, schedules, deadlines, volume, and SLOs
- Notification channels, templates, preferences, consent, and quiet hours
- Existing queue/provider/runtime constraints and cost limits
- Idempotency keys, ownership, data retention, and operational requirements

### Apply these decision rules

- Assume at-least-once delivery and make handlers idempotent.
- Separate job accepted, executed, provider accepted, provider-reported delivered, failed, and unknown/unconfirmed states; do not imply actual receipt or reading without evidence.
- Honor preferences, quiet hours, and unsubscribe requirements.
- Avoid unbounded retries and payloads containing unnecessary sensitive data.

### Resolve these domain decisions

- Assume at-least-once execution and make every externally visible handler idempotent before adding retries.
- Define retryable, terminal, poison, cancelled, superseded, and dead-letter states with explicit operator actions.
- Separate job completion, provider acceptance, provider-reported delivery, failure, and unknown receipt states.
- Model timezone, daylight-saving, missed schedule, catch-up, preference change, and quiet-hour behavior deterministically.
- Store only required payload data and define retention, redaction, replay authorization, deduplication, and audit controls.

### Avoid

- Exactly-once assumptions
- Retries without idempotency
- Conflating provider acceptance with delivery
- Ignoring timezone and consent behavior

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.
- Load [../_shared/checklists/production-readiness-checklist.md](../_shared/checklists/production-readiness-checklist.md) only when release, migration, deployment, or operational readiness is in scope.

## Validation steps

- Test duplicates, retries, poison jobs, provider outage, timeouts, and partial completion.
- Test DST, time-zone changes, missed schedules, and clock skew.
- Verify notification preferences, localization, links, delivery logs, and opt-out.
- Confirm dashboards, alerts, replay, and dead-letter recovery.

## Expected output

- Job and notification architecture
- State/retry/idempotency contracts
- Preference, template, provider, and admin controls
- Failure-test and operations evidence
