---
name: design-to-code-engineer
description: "Implement a supplied screenshot, mockup, Figma reference, or approved design as accurate maintainable UI; not for original product direction or visual QA alone."
---

# Design to Code Engineer

## Activation conditions

Primary outcome: Translate visual intent into faithful code while preserving real behavior, maintainability, and repository conventions.

Use this skill when:

- A screenshot, mockup, Figma frame, or reference UI must become code.
- An implementation must be brought into visual parity.
- A design brief specifies a concrete interface to build.

Do not use this skill when:

- The user wants critique only.
- The task would require replacing unrelated architecture or real functionality.

## Required workflow

1. Inspect references at full fidelity and map visible regions, assets, type, spacing, states, and behavior.
2. Inspect repository conventions and identify reusable primitives before coding.
3. Decompose the reference into semantic layout and components without premature abstraction.
4. Implement real content/data behavior and accessible interactions.
5. Match responsive composition, typography, assets, and state behavior.
6. Run the application and compare screenshots at representative viewports.
7. Fix systemic differences first and repeat until acceptance criteria are met.

## Skill-specific rules

### Confirm these inputs

- Authoritative visual references and target viewports
- Repository stack, routes, components, tokens, and installed versions
- Assets, fonts, content, interactions, states, and responsive rules
- Acceptance criteria and allowed deviations

### Apply these decision rules

- Preserve product functionality and semantics.
- Use semantic tokens instead of unexplained one-off values.
- Match the reference while adapting intelligently to unsupported sizes and content.
- Keep changes scoped to the requested surface.

### Resolve these domain decisions

- Rank reference authority when screenshots, design files, written requirements, and existing behavior disagree.
- Infer reusable components from repeated semantics and behavior, not merely repeated visual rectangles.
- Translate fixed mockup coordinates into intrinsic responsive constraints without weakening the approved composition.
- Preserve live data, navigation, accessibility semantics, form behavior, and error handling throughout visual implementation.
- Record intentional deviations with the source conflict, technical constraint, product rationale, and validation evidence.

### Avoid

- Coding from memory instead of inspecting the reference
- Absolute-positioning the whole screen
- Replacing real data with mocks
- Claiming fidelity without rendered comparison

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/references/visual-qa-process.md](../_shared/references/visual-qa-process.md) only when rendered parity or regression evidence is required.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.

## Validation steps

- Run applicable type, lint, build, and tests.
- Capture and compare rendered mobile and desktop screenshots.
- Check long content and loading, empty, error, success, hover, focus, and active states.
- Document intentional differences and technical constraints.

## Expected output

- Production implementation
- Component/token reuse map
- Visual comparison evidence
- Validation results and explicit deviations
