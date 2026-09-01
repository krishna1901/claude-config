---
name: design-system-architect
description: "Create or evolve reusable design tokens, component standards, variants, documentation, and governance; not for polishing one screen or implementing a supplied mockup."
---

# Design System Architect

## Activation conditions

Primary outcome: Create a stable design language and implementation contract that improves consistency without blocking product work.

Use this skill when:

- Repeated values or components diverge across the product.
- A multi-team product needs tokens, primitives, governance, or migration.
- Dark mode, accessibility, or responsive behavior needs systematic treatment.

Do not use this skill when:

- A single local component has no proven reuse.
- The request can be solved by an existing system primitive.

## Required workflow

1. Audit existing tokens, primitives, components, duplicates, and exceptions.
2. Define semantic foundations and separate intent tokens from raw scales.
3. Specify component anatomy, slots, variants, states, content rules, and accessibility contracts.
4. Design theme, density, breakpoint, icon, and motion systems.
5. Map APIs and dependency direction across design and code.
6. Plan documentation, versioning, contribution, deprecation, and governance.
7. Migrate incrementally and validate representative product surfaces.

## Skill-specific rules

### Confirm these inputs

- Repository token/component inventory and usage data
- Brand, accessibility, platform, and theming requirements
- Supported frameworks, styling approach, and version constraints
- Adoption pain points, ownership, and migration capacity

### Apply these decision rules

- Name tokens by meaning rather than appearance.
- Keep component APIs small, composable, and consistent.
- Include focus, disabled, loading, error, and destructive behavior.
- Allow intentional product expression without uncontrolled variants.

### Resolve these domain decisions

- Separate raw scales from semantic intent tokens and component-specific aliases to support controlled theming.
- Promote a pattern into the system only after evidence of reuse, stable anatomy, and consistent behavioral needs.
- Specify slot ownership, content limits, interaction states, accessibility contract, and escape hatches for each component.
- Define contribution, review, versioning, deprecation, migration, and ownership rules before broad adoption.
- Measure adoption and exceptions; remove obsolete duplicates only after consumers migrate and regressions are checked.

### Avoid

- Tokenizing every unique number
- Building components before observing real use cases
- Boolean-prop explosions
- Big-bang replacement of working UI

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/references/motion-design-principles.md](../_shared/references/motion-design-principles.md) only when motion behavior or animation implementation is in scope.

## Validation steps

- Validate token contrast and theme parity.
- Test component behavior across viewports, input modes, and content extremes.
- Check visual regressions on migrated surfaces.
- Measure adoption and remove superseded duplicates safely.

## Expected output

- System foundations and semantic token model
- Component contracts and state matrices
- Governance, documentation, and contribution model
- Incremental migration and validation plan
