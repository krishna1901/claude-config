---
name: deployment-devops-architect
description: "Design or improve CI/CD, environments, secrets, hosting, releases, migrations, observability, rollback, backups, and scaling; not for application feature coding alone."
---

# Deployment DevOps Architect

## Activation conditions

Primary outcome: Create reproducible, observable releases with controlled risk, recovery, and environment separation.

Use this skill when:

- A system needs hosting, CI/CD, environments, release, or rollback design.
- Migrations, secrets, domains, SSL, scaling, observability, or backups affect deployment.
- Production delivery is manual, fragile, or expensive.

Do not use this skill when:

- The change is purely local and has no deployment effect.
- The user only needs application feature code.

## Required workflow

1. Inspect build, infrastructure, scripts, environments, and provider constraints.
2. Define immutable artifacts, environment promotion, configuration, and secret ownership.
3. Design CI gates, previews, migrations, deployment strategy, health checks, and smoke tests.
4. Specify logs, metrics, traces, alerts, dashboards, and operational ownership.
5. Plan CDN, DNS, SSL, scaling, quotas, cost controls, backups, and restore.
6. Define rollback, roll-forward, incident, and third-party degradation procedures.
7. Exercise deployment and recovery in a production-like environment.

## Skill-specific rules

### Confirm these inputs

- Repository build/runtime versions, services, and deployment target
- Environment topology, secrets, domains, data stores, and migrations
- SLOs, traffic, scaling, budget, compliance, and team ownership
- Current CI/CD, monitoring, backups, incidents, and rollback constraints

### Apply these decision rules

- Keep environments reproducible and secrets out of source/artifacts.
- Separate build-time and runtime configuration.
- Make migrations backward-compatible during rollout.
- Prefer simple managed services when they meet requirements.

### Resolve these domain decisions

- Build immutable artifacts once and promote the same verified artifact through controlled environments.
- Separate build-time configuration, runtime configuration, secrets, and public client settings with clear ownership.
- Sequence application and database changes for compatibility, health checking, smoke testing, and safe recovery.
- Define logs, metrics, traces, alerts, dashboards, on-call ownership, and escalation for critical user journeys.
- Exercise rollback or roll-forward, backup restore, DNS, certificates, CDN behavior, and provider degradation before launch.

### Avoid

- Manual snowflake servers
- Secrets embedded in images or client bundles
- Destructive migrations tied blindly to app deploy
- Rollback plans that have never been exercised

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/production-readiness-checklist.md](../_shared/checklists/production-readiness-checklist.md) only when release, migration, deployment, or operational readiness is in scope.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.

## Validation steps

- Run CI from a clean checkout and verify production artifact.
- Test health checks, smoke tests, migration order, rollback, backup, and restore.
- Verify domain, SSL, CDN, cache, environment, and secret behavior.
- Load/failure test critical scaling and alert paths.

## Expected output

- Deployment architecture and pipeline
- Environment/configuration/secret model
- Release, migration, smoke, rollback, and restore runbook
- Observability and cost controls
