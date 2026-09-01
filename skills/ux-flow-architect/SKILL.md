---
name: ux-flow-architect
description: "Design detailed user journeys, states, transitions, permissions, forms, and recovery paths for complex features; not for product strategy or visual polish."
---

# UX Flow Architect

## Activation conditions

Primary outcome: Make product behavior complete, coherent, recoverable, and implementable before screens are polished.

Use this skill when:

- A feature spans several steps, states, roles, or entry points.
- Authentication, payment, permissions, AI, or forms introduce failure branches.
- Teams disagree about navigation or recovery behavior.

Do not use this skill when:

- Only a static visual treatment is requested.
- The task is an internal service with no user interaction flow.

## Required workflow

1. Inspect current routes and interaction conventions.
2. Define actors, triggers, preconditions, entry points, and desired terminal states.
3. Map the happy path with user actions, system responses, data changes, and navigation.
4. Add permissions, onboarding, auth, form, subscription, and AI branches as applicable.
5. Model loading, empty, partial, timeout, offline, validation, denial, failure, retry, cancellation, and success.
6. Define back behavior, persistence, resumption, duplicate submission, and cross-device/session handling.
7. Annotate events, ownership boundaries, content needs, accessibility, and acceptance criteria.

## Skill-specific rules

### Confirm these inputs

- User roles, goals, and entry points
- Existing routes, navigation, auth, entitlements, and data rules
- Business rules, platform constraints, and analytics requirements
- Known failure modes and recovery capabilities

### Apply these decision rules

- Keep each step necessary and make status visible.
- Preserve user work across recoverable failures.
- Put authorization decisions on trusted server boundaries.
- Use existing navigation and component patterns unless change is justified.

### Resolve these domain decisions

- Assign every transition an initiating actor, precondition, system response, persisted effect, and terminal state.
- Define resumption after refresh, app restart, expired session, network loss, and cross-device continuation.
- Model authentication, permission, subscription, and payment gates without losing the user's original intent.
- For AI interactions, expose uncertainty, latency, cancellation, correction, and safe fallback behavior.
- Keep navigation, browser or device back behavior, deep links, and duplicate submissions deterministic.

### Avoid

- Drawing only the happy path
- Hiding system status behind indefinite spinners
- Dead ends without recovery or preserved input
- Treating client-side visibility as authorization

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/references/frontend-architecture-principles.md](../_shared/references/frontend-architecture-principles.md) only when frontend ownership or dependency boundaries are material.

## Validation steps

- Walk flows for each role and entry point.
- Test interrupted, expired, denied, duplicate, and partial-completion scenarios.
- Verify every branch has a terminal state or recovery path.
- Check keyboard, focus, mobile back, and deep-link behavior where relevant.

## Expected output

- Annotated flow map or state machine
- Screen/state inventory with transitions and ownership
- Edge-case and recovery matrix
- Acceptance criteria and analytics events
