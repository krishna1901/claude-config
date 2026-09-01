---
name: product-design-director
description: "Define product direction, audience, priorities, journeys, and success criteria for new products or major features; not for detailed UI implementation or small fixes."
---

# Product Design Director

## Activation conditions

Primary outcome: Turn product ambiguity into a decision document that aligns product, design, and engineering before implementation.

Use this skill when:

- A product idea lacks clear users, scope, journeys, or success measures.
- A redesign affects multiple screens, capabilities, or teams.
- Engineering needs an authoritative brief before estimating or building.

Do not use this skill when:

- A single token, spacing, or isolated style correction.
- Implementation is fully specified and requires no product decisions.

## Required workflow

1. Inspect the repository and current product before proposing change.
2. Separate facts, assumptions, open questions, and decisions.
3. Define audience segments, jobs to be done, pains, desired outcomes, and product principles.
4. Map journeys, information architecture, feature hierarchy, core states, permissions, and edge cases.
5. Specify design direction through hierarchy, interaction, content, accessibility, responsive, and technical constraints.
6. Prioritize scope into must/should/could/not-now and expose dependencies.
7. Define measurable success, guardrails, analytics events, and acceptance criteria.
8. Produce a brief that engineering and design can implement without inventing product behavior.

## Skill-specific rules

### Confirm these inputs

- Business goal and target audience
- Known evidence, constraints, risks, and deadlines
- Existing repository, product behavior, analytics, and brand assets
- Stakeholder decisions and non-goals

### Apply these decision rules

- Trace every proposed feature to a user need and product goal.
- Make non-goals and trade-offs explicit.
- Preserve working architecture unless evidence justifies change.
- Give the product a distinct identity without redesigning unrelated areas.

### Resolve these domain decisions

- Set the smallest coherent release boundary before expanding feature detail or visual direction.
- Tie every must-have capability to a user job, business outcome, and observable acceptance signal.
- Resolve ownership, permissions, dependencies, and data availability before calling a brief implementation-ready.
- Separate launch requirements from experiments, future options, and ideas that lack supporting evidence.
- Specify how success will be measured without encouraging dark patterns, vanity metrics, or inaccessible behavior.

### Avoid

- Starting with screens before understanding the product goal
- Treating assumptions as research evidence
- Feature lists without hierarchy, states, or success criteria
- Redesigning unrelated surfaces to make the concept feel complete

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.

## Validation steps

- Review the brief against existing routes, data, permissions, and platform constraints.
- Walk at least one happy path and key failure/recovery paths.
- Check that success criteria are measurable and not vanity metrics.
- Resolve or visibly assign every implementation-blocking question.

## Expected output

- Implementation-ready product design brief
- Journey and information-architecture map
- Prioritized requirements, states, constraints, and non-goals
- Measurable outcomes, acceptance criteria, assumptions, and open decisions
