---
name: responsive-interface-engineer
description: "Adapt and validate interfaces across viewports, devices, input modes, zoom, orientation, and constrained height; not for general styling or product strategy."
---

# Responsive Interface Engineer

## Activation conditions

Primary outcome: Make the product adapt coherently to available space, input mode, content, and device conditions.

Use this skill when:

- Layouts or interactions must work across diverse viewport conditions.
- Overflow, wrapping, keyboard, orientation, or intermediate-width issues exist.
- A new interface needs responsive implementation and evidence.

Do not use this skill when:

- The task concerns a fixed-size asset only.
- A single breakpoint token change is fully specified and independently verifiable.

## Required workflow

1. Inspect current layout system and reproduce target conditions.
2. Identify content-driven layout thresholds and interaction changes.
3. Define container, grid, spacing, type, navigation, and component adaptation rules.
4. Implement intrinsic sizing, wrapping, min/max constraints, and overflow deliberately.
5. Provide compact alternatives for complex navigation, tables, charts, and toolbars.
6. Test touch, keyboard, hover absence, short height, zoom, rotation, and long content.
7. Fix systemic rules first and document unavoidable constraints.

## Skill-specific rules

### Confirm these inputs

- Supported device/browser matrix and analytics
- Existing breakpoints, layout primitives, tokens, and components
- Content extremes, localization, tables/charts, and interaction states
- Safe-area, keyboard, orientation, zoom, and accessibility requirements

### Apply these decision rules

- Preserve task priority and reading order at every size.
- Avoid device-specific forks when flexible layout solves the problem.
- Use repository tokens and primitives.
- Keep controls reachable above keyboards and safe areas.

### Resolve these domain decisions

- Prefer intrinsic sizing, wrapping, grid constraints, and container logic before adding another viewport breakpoint.
- Adapt navigation and interaction by available space and input capability, not by guessed device identity.
- Treat short height, software keyboards, safe areas, zoom, text scaling, and orientation as first-class constraints.
- Provide compact but complete alternatives for tables, charts, dense toolbars, and multi-column workflows.
- Preserve action priority, reading order, focus order, and information meaning through every layout transformation.

### Avoid

- Desktop-first shrinking
- Breakpoint proliferation without content rationale
- Hiding essential functionality on small screens
- Testing only width while ignoring height and input mode

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/references/visual-qa-process.md](../_shared/references/visual-qa-process.md) only when rendered parity or regression evidence is required.

## Validation steps

- Run the full shared responsive matrix.
- Check screenshots and interaction at small, intermediate, large, and ultrawide widths.
- Test 200%-400% zoom, text scaling, orientation, and reduced height.
- Verify no clipping, obscured focus, unreachable actions, or unintended horizontal scroll.

## Expected output

- Responsive behavior specification
- Implemented layout and component adaptations
- Viewport/state validation matrix
- Known constraints and regression evidence
