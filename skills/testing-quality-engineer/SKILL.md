---
name: testing-quality-engineer
description: "Design or implement risk-focused unit, integration, contract, end-to-end, accessibility, visual, migration, and smoke tests; not for a final cross-functional release gate."
---

# Testing Quality Engineer

## Activation conditions

Primary outcome: Create fast, trustworthy evidence around critical behavior while keeping the suite maintainable.

Use this skill when:

- A feature or system needs a test strategy or implementation.
- Regressions, flaky tests, slow suites, or coverage gaps threaten delivery.
- A release needs risk-based validation evidence.

Do not use this skill when:

- The only goal is an arbitrary line-coverage target.
- Existing tests already cover the change and only routine execution is needed.

## Required workflow

1. Inspect the system and build a risk inventory by impact and likelihood.
2. Map each risk to the cheapest reliable test level.
3. Design deterministic fixtures, data isolation, clocks, network/provider fakes, and cleanup.
4. Implement high-value unit, integration, contract, E2E, accessibility, visual, migration, and smoke coverage as appropriate.
5. Test negative, boundary, concurrency, permission, and recovery behavior.
6. Remove flake through root-cause fixes, not retries alone.
7. Run the suite in CI-like conditions and document gaps.

## Skill-specific rules

### Confirm these inputs

- Critical user journeys, business rules, risks, and failure history
- Architecture, boundaries, dependencies, environments, and test tooling
- Data, auth roles, browsers/devices, accessibility, and performance constraints
- CI budget, ownership, and release gates

### Apply these decision rules

- Assert user-visible or contract behavior, not implementation trivia.
- Keep tests independent, deterministic, and readable.
- Use few end-to-end tests for critical cross-boundary journeys.
- Treat accessibility and migrations as first-class risks.

### Resolve these domain decisions

- Rank risks by user or business impact, likelihood, detectability, and history before choosing test levels.
- Use the cheapest test that crosses the boundary where the failure can occur; reserve E2E for critical integrations.
- Design deterministic data, clocks, randomness, network behavior, provider doubles, isolation, and cleanup.
- Test authorization, concurrency, retries, migration compatibility, recovery, and accessibility as product behavior.
- Remove flake by fixing shared state, timing, nondeterminism, and environment assumptions instead of increasing retries.

### Avoid

- Snapshotting everything
- Mocking the behavior under test
- Coverage percentage as the strategy
- Retrying flaky tests without diagnosis

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/production-readiness-checklist.md](../_shared/checklists/production-readiness-checklist.md) only when release, migration, deployment, or operational readiness is in scope.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/references/visual-qa-process.md](../_shared/references/visual-qa-process.md) only when rendered parity or regression evidence is required.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.

## Validation steps

- Run new tests repeatedly and in the configured suite.
- Inject representative failures and permissions.
- Check flake, runtime, isolation, and diagnostic output.
- Confirm each release gate maps to a documented risk.

## Expected output

- Risk and test matrix
- Implemented tests and fixtures
- CI/release gate recommendations
- Results, flake status, and residual gaps
