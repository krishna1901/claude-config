---
name: visual-qa-specialist
description: "Compare rendered interfaces with references across viewports, identify visual discrepancies, fix them, and retest; not for initial visual design or feature architecture."
---

# Visual QA Specialist

## Activation conditions

Primary outcome: Close the gap between intended and rendered interface through evidence-driven visual iteration.

Use this skill when:

- An implementation must match a reference or approved baseline.
- A UI change needs visual regression verification.
- Visible inconsistencies must be isolated and fixed.

Do not use this skill when:

- There is no runnable interface or stable artifact to inspect.
- The task is product strategy without implementation.

## Required workflow

1. Inspect the repository and establish a reproducible capture environment.
2. Capture baseline screenshots for all representative viewports and states.
3. Compare composition, typography, spacing, assets, color, controls, wrapping, overflow, and overlays.
4. Rank discrepancies by impact and shared root cause.
5. Fix tokens, primitives, or layout rules before local offsets.
6. Re-capture affected and neighboring views after each systemic fix.
7. Record evidence, intentional differences, and remaining risk.

## Skill-specific rules

### Confirm these inputs

- Runnable application and startup instructions
- Authoritative references or approved baselines
- Target browsers/devices, viewports, themes, and states
- Tolerance, known rendering variability, and scope boundaries

### Apply these decision rules

- Use stable data, fonts, time, animation, and viewport settings.
- Distinguish antialiasing noise from meaningful differences.
- Keep fixes within requested scope.
- Validate interaction states, not only static default views.

### Resolve these domain decisions

- Stabilize fonts, data, time, animation, viewport, browser scale, and capture timing before comparing images.
- Review canvas and layout structure before typography, components, decoration, and pixel-level differences.
- Distinguish antialiasing and platform rendering noise from repeatable product-facing discrepancies.
- Fix shared tokens or primitives before applying local offsets, then recapture every affected surface.
- Change approved baselines only when the intended design changed and the reason is independently documented.

### Avoid

- Eyeballing a single viewport
- One-off offsets that hide token problems
- Updating baselines to conceal regressions
- Declaring parity from source inspection

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/visual-qa-process.md](../_shared/references/visual-qa-process.md) only when rendered parity or regression evidence is required.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.

## Validation steps

- Run repository checks after code changes.
- Compare at small phone, intermediate, desktop, and any reference-specific sizes.
- Test long content, zoom, focus, loading, error, and overlays.
- Confirm no unrelated baseline regressed.

## Expected output

- Before/after capture set
- Severity-ranked discrepancy log
- Scoped fixes
- Final comparison and remaining intentional differences
