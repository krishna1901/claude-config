---
name: production-readiness-reviewer
description: "Run a read-only final release gate across product, security, data, accessibility, performance, operations, and deployment evidence; not for early design or automatic remediation."
---

# Production Readiness Reviewer

## Activation conditions

Primary outcome: Provide an evidence-based go/no-go decision with findings classified as BLOCKER, CRITICAL, HIGH, MEDIUM, LOW, or POLISH.

Use this skill when:

- A product or major release is approaching production.
- Stakeholders need a final cross-functional release gate.
- Operational, security, data, or experience readiness is uncertain.

Do not use this skill when:

- The feature is still in early concept/design.
- The request expects automatic approval without running checks.

## Required workflow

1. Inspect repository and production-like environment; inventory release changes and dependencies.
2. Run critical functional journeys across roles, failure states, billing, notifications, and recovery.
3. Review visual quality, responsiveness, accessibility, privacy, security, performance, and SEO evidence.
4. Verify analytics, logs, error handling, environment variables, migrations, backups, restore, and observability.
5. Exercise deployment, health checks, smoke tests, rollback/roll-forward, domains, SSL, CDN, and cache behavior.
6. Classify every finding by severity, evidence, impact, remediation, owner, and retest.
7. Issue GO, CONDITIONAL GO, or NO-GO with explicit blocking criteria.

## Skill-specific rules

### Confirm these inputs

- Release scope, acceptance criteria, owners, timeline, and rollback threshold
- Repository, CI results, environments, deployment, and runtime configuration
- Critical journeys, roles, data/migrations, billing, notifications, and integrations
- Security, privacy, performance, SEO, analytics, legal, SLO, backup, and monitoring requirements

### Apply these decision rules

- Operate read-only by default; remediation requires a separate user request or explicit authorization.
- BLOCKER means release cannot proceed safely or functionally, and any unresolved BLOCKER requires NO-GO.
- CRITICAL means severe security, data, legal, privacy, or widespread outage risk, and any unresolved CRITICAL requires NO-GO.
- HIGH means major user or business risk; release requires exceptional documented risk acceptance, named owner, deadline, monitoring, and rollback protection.
- MEDIUM, LOW, and POLISH must remain evidence-based and owned.
- Never downgrade a finding to meet a date.

### Resolve these domain decisions

- Require direct evidence for every finding, release disposition, accepted risk, and claimed completed control.
- Treat unresolved BLOCKER or CRITICAL findings as NO-GO without schedule-based exceptions.
- Allow HIGH risk only through explicit exceptional acceptance with owner, deadline, monitoring, and rollback protection.
- Separate release gating from remediation; remain read-only unless the user separately authorizes changes.
- Confirm deployment, migration, backup, restore, billing, notification, legal, monitoring, and rollback ownership before GO.

### Avoid

- Checklist theater without evidence
- Approving because CI is green
- Mixing polish with release blockers
- Ignoring rollback, backups, billing, notifications, or legal requirements

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/production-readiness-checklist.md](../_shared/checklists/production-readiness-checklist.md) only when release, migration, deployment, or operational readiness is in scope.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/references/visual-qa-process.md](../_shared/references/visual-qa-process.md) only when rendered parity or regression evidence is required.

## Validation steps

- Run configured CI and production build from a clean environment.
- Verify critical journeys on representative desktop/mobile platforms.
- Complete applicable security, accessibility, performance, migration, backup/restore, and deployment checks.
- Retest every blocker/critical/high remediation and record evidence.

## Expected output

- Severity-ranked release findings
- GO, CONDITIONAL GO, or NO-GO decision
- Owner/remediation/retest table
- Deployment, rollback, monitoring, and residual-risk summary
