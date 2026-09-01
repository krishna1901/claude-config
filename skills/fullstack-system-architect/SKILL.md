---
name: fullstack-system-architect
description: "Design complete system architecture, service boundaries, data flows, operations, scaling, and trade-offs for complex products; not for a specialized implementation task alone."
---

# Fullstack System Architect

## Activation conditions

Primary outcome: Produce an implementable architecture with explicit trust boundaries, failure behavior, costs, and incremental decisions.

Use this skill when:

- A new product or major capability spans frontend, backend, data, and operations.
- Scaling, reliability, security, or service boundaries require design.
- A risky architectural change needs options and trade-offs.

Do not use this skill when:

- A small change fits established architecture.
- The user only needs component-level implementation details.

## Required workflow

1. Inspect the existing system and separate confirmed facts from assumptions.
2. Define system context, actors, trust boundaries, and critical workflows.
3. Partition components and data ownership with explicit contracts and dependency direction.
4. Design storage, auth, authorization, caching, queues, notifications, and observability.
5. Model failure modes, consistency, retries, idempotency, degradation, backup, and recovery.
6. Evaluate scale, cost, security, deployment, migration, and operational ownership.
7. Compare viable options and produce staged implementation and validation plans.

## Skill-specific rules

### Confirm these inputs

- Functional and non-functional requirements, audience, scale, and SLOs
- Existing repository, infrastructure, data, integrations, and constraints
- Security, privacy, compliance, budget, team, and delivery horizon
- Failure tolerance, growth assumptions, and migration needs

### Apply these decision rules

- Prefer the simplest architecture that meets measured requirements.
- Keep authorization at trusted boundaries.
- Avoid distributed components without independent operational value.
- Make reversibility and migration explicit.

### Resolve these domain decisions

- Define actors, external systems, trust boundaries, data ownership, critical workflows, and service-level objectives first.
- Choose consistency, availability, latency, and failure behavior explicitly for every state-changing cross-boundary flow.
- Add queues, caches, services, or replicas only when they solve measured isolation, scale, reliability, or ownership needs.
- Model provider outage, partial failure, retries, duplicate delivery, recovery, backup, restore, and degraded operation.
- Compare architecture options by delivery complexity, operability, security, reversibility, recurring cost, and team capability.

### Avoid

- Technology selection before requirements
- Microservices by default
- Ignoring failure and operational ownership
- Client-side enforcement of sensitive rules

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/frontend-architecture-principles.md](../_shared/references/frontend-architecture-principles.md) only when frontend ownership or dependency boundaries are material.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.
- Load [../_shared/checklists/production-readiness-checklist.md](../_shared/checklists/production-readiness-checklist.md) only when release, migration, deployment, or operational readiness is in scope.

## Validation steps

- Walk critical data and failure paths end to end.
- Threat-model privileged and external boundaries.
- Estimate capacity/cost and test the riskiest assumption.
- Review deployment, migration, rollback, backup, and observability readiness.

## Expected output

- Context and component diagrams
- Data flows, contracts, ownership, and trust boundaries
- Architecture decision record with trade-offs
- Phased implementation, validation, operations, and rollback plan
