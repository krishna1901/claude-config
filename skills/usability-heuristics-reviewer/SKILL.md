---
name: usability-heuristics-reviewer
description: "Audit interface usability with evidence, severity, impact, and testable remediation when workflows feel confusing; not for subjective visual taste or implementation."
---

# Usability Heuristics Reviewer

## Activation conditions

Primary outcome: Produce an actionable usability risk assessment rather than a taste-based design critique.

Use this skill when:

- A flow or interface needs structured usability evaluation.
- Teams need severity-ranked issues before redesign or release.
- Observed friction must be connected to principles and remediation.

Do not use this skill when:

- The request asks only for a visual direction or new concept.
- No interface or reliable artifact can be inspected.

## Required workflow

1. Inspect the actual experience across representative states and viewports.
2. Evaluate visibility of status, real-world match, control, consistency, prevention, recognition, flexibility, minimalism, recovery, and help.
3. Capture each issue with location, evidence, affected task/user, and reproducible condition.
4. Assign severity from frequency, impact, persistence, recoverability, and business risk.
5. Recommend the smallest systemic remediation, not just cosmetic patches.
6. Define how each fix will be validated and identify uncertain findings.

## Skill-specific rules

### Confirm these inputs

- Runnable product, screenshots, or prototype
- Target users, tasks, devices, and business-critical journeys
- Known analytics, support issues, and constraints
- Applicable platform conventions and accessibility requirements

### Apply these decision rules

- Make every finding reproducible and evidence-linked.
- Separate usability, accessibility, visual polish, and product-policy issues.
- Use a consistent 0-4 severity scale: 0 no issue, 1 cosmetic, 2 minor friction, 3 major task impairment, 4 task blocker or severe user/business risk.
- Prioritize blockers to task success over preference.
- Acknowledge strengths and patterns worth preserving.

### Resolve these domain decisions

- Score severity from task impact, frequency, persistence, recoverability, affected population, and business risk.
- Capture the exact state, action, expected result, observed result, and evidence for every finding.
- Group repeated symptoms under the smallest shared root cause instead of inflating issue counts.
- Separate usability defects from accessibility failures, product-policy choices, bugs, and optional visual polish.
- Recommend a validation method proportionate to uncertainty and severity for every proposed remediation.

### Avoid

- Vague statements such as make it cleaner
- Severity based on personal annoyance
- Redesigning unrelated areas
- Reporting duplicate symptoms instead of a shared root cause

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.

## Validation steps

- Re-run affected journeys after remediation.
- Check high-severity findings with user evidence when feasible.
- Confirm recommendations do not introduce new accessibility or responsive failures.
- Track status and remaining risk per finding.

## Expected output

- Severity-ranked findings table
- Evidence and business/user impact for each issue
- Scoped remediation recommendations
- Validation plan and unresolved questions
