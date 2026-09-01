---
name: frontend-architecture-expert
description: "Design frontend boundaries, routing, state ownership, data flow, caching, and dependency direction when structural decisions are required; not for routine component work."
---

# Frontend Architecture Expert

## Activation conditions

Primary outcome: Create clear ownership and dependency boundaries that support change without giant components or premature abstraction.

Use this skill when:

- A frontend is being structured, scaled, or meaningfully refactored.
- State, data, routing, or server/client ownership is unclear.
- Repeated coupling and giant components are blocking delivery.

Do not use this skill when:

- A small feature already fits a stable local pattern.
- The request is backend-only or purely visual.

## Required workflow

1. Inspect representative features, configuration, scripts, and dependency graph.
2. Map rendering, routing, state lifetimes, data flow, errors, and side effects.
3. Assign ownership for remote, URL, form, session, and ephemeral state.
4. Define feature boundaries, dependency direction, server/client seams, and API client contracts.
5. Specify caching, invalidation, optimistic updates, cancellation, forms, and error boundaries.
6. Design testing seams, code splitting, observability, and incremental migration.
7. Validate the architecture on real workflows before broad adoption.

## Skill-specific rules

### Confirm these inputs

- Installed framework versions and build/runtime model
- Route, feature, component, state, and API maps
- Product workflows, team boundaries, deployment, and performance constraints
- Current pain points, tests, and migration tolerance

### Apply these decision rules

- Prefer local ownership and explicit data flow.
- Keep client boundaries and shared layers small.
- Reuse existing conventions unless measured problems justify change.
- Choose simple composition over framework-like internal abstractions.

### Resolve these domain decisions

- Separate remote, URL, session, form, persistent client, and ephemeral component state by lifecycle and owner.
- Enforce dependency direction so shared primitives never import routes or product features.
- Place server and client boundaries around capability and data ownership, not arbitrary file-size thresholds.
- Define cache keys, freshness, invalidation, cancellation, retry, and optimistic reconciliation as one data policy.
- Migrate through reversible seams and representative features before applying a new architecture broadly.

### Avoid

- Folder diagrams without ownership rules
- Global state for convenience
- Generic shared layers that import feature code
- Big-bang rewrites without migration evidence

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/frontend-architecture-principles.md](../_shared/references/frontend-architecture-principles.md) only when frontend ownership or dependency boundaries are material.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.

## Validation steps

- Trace critical data and error paths end to end.
- Prototype the riskiest boundary with repository versions.
- Run type, lint, build, tests, and bundle checks as applicable.
- Verify migration steps preserve behavior and rollback.

## Expected output

- Current-state architecture map
- Target boundaries, responsibilities, and decision record
- Incremental migration plan
- Validation strategy and identified trade-offs
