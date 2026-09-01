---
name: accessibility-specialist
description: "Audit or fix semantics, keyboard use, focus, forms, contrast, screen readers, reduced motion, and accessible charts; not for general visual polish alone."
---

# Accessibility Specialist

## Activation conditions

Primary outcome: Remove barriers in real user journeys and leave verifiable accessibility evidence.

Use this skill when:

- A product needs an accessibility audit, fix, or release check.
- New interactive UI needs semantic and assistive-technology design.
- Reported keyboard, screen-reader, contrast, zoom, or motion issues need remediation.

Do not use this skill when:

- The user asks for legal certification without an authorized audit.
- The issue is purely aesthetic and creates no accessibility impact.

## Required workflow

1. Inspect the implementation and map critical journeys and component primitives.
2. Run available automated scans and treat results as leads, not proof.
3. Manually test semantics, headings, landmarks, keyboard order, focus, dialogs, forms, errors, and dynamic updates.
4. Test contrast, targets, zoom/reflow, text scaling, reduced motion, and orientation.
5. Test representative screen-reader behavior and accessible visualization alternatives.
6. Fix root primitives before repeated local symptoms.
7. Re-test affected journeys and document evidence and residual risk.

## Skill-specific rules

### Confirm these inputs

- Target standards, platforms, browsers, devices, and assistive technologies
- Critical routes, roles, states, and content
- Repository tooling and component system
- Known issues, user reports, and constraints

### Apply these decision rules

- Prefer native semantics before ARIA.
- Preserve visible focus and input after errors.
- Make dynamic state understandable without color or motion alone.
- Do not weaken product functionality to pass a scanner.

### Resolve these domain decisions

- Prefer native elements and platform semantics; add ARIA only to complete a valid interaction pattern.
- Define focus entry, containment, movement, error routing, and restoration for every dynamic overlay or route transition.
- Test announcements for names, roles, values, state changes, validation, loading, and asynchronous completion.
- Provide equivalent access to charts, gestures, drag operations, time limits, and motion-dependent interactions.
- Separate verified failures, tool warnings, untested areas, and legal interpretation in the final evidence.

### Avoid

- Adding ARIA to invalid semantics
- Assuming automated tools prove compliance
- Removing focus outlines
- Reporting inaccessible patterns without a validation path

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.

## Validation steps

- Run automated accessibility checks and repository tests.
- Complete keyboard-only, zoom/reflow, reduced-motion, and screen-reader checks where feasible.
- Verify mobile touch targets and platform accessibility when relevant.
- Record tested combinations, failures, fixes, and unverified areas.

## Expected output

- Severity-ranked accessibility findings
- Scoped code/design remediations
- Automated and manual test evidence
- Residual risks and follow-up plan
