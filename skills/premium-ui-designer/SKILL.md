---
name: premium-ui-designer
description: "Design or refine premium production interfaces with strong hierarchy, composition, typography, and product identity; not for system architecture or isolated bug fixes."
---

# Premium UI Designer

## Activation conditions

Primary outcome: Translate product purpose and brand character into a coherent interface that feels authored, useful, and buildable.

Use this skill when:

- A new screen, feature, landing page, or product surface needs visual direction.
- An existing interface needs a meaningful hierarchy and quality uplift.
- A design brief must become production-ready UI specifications.

Do not use this skill when:

- One narrow CSS defect has an obvious fix.
- The task is research or architecture without a visual interface deliverable.

## Required workflow

1. Inspect the product and design system before sketching.
2. Define a visual thesis tied to product identity and content.
3. Establish hierarchy, grid, density, type, color roles, surfaces, and interaction language.
4. Design responsive compositions and all relevant component states.
5. Reuse or extend semantic tokens and components with minimal new primitives.
6. Specify behavior for long content, loading, empty, error, success, and destructive actions.
7. Review rendered output and iterate on the highest-impact discrepancies.

## Skill-specific rules

### Confirm these inputs

- Product goal, audience, jobs, and content priority
- Existing components, tokens, brand assets, and supported themes
- Platform, viewport, accessibility, performance, and implementation constraints
- Reference material and explicit non-goals

### Apply these decision rules

- Favor strong composition over decorative effects.
- Use semantic tokens and accessible contrast.
- Keep controls recognizable and content dominant.
- Avoid arbitrary gradients, excessive glassmorphism, rounded-card repetition, and generic AI-dashboard styling.

### Resolve these domain decisions

- State one visual thesis that connects brand character, content hierarchy, audience expectations, and product utility.
- Choose density from task frequency and information needs rather than applying spacious layouts universally.
- Use authentic product content and assets when judging composition, wrapping, emphasis, and responsive behavior.
- Define interactive, empty, loading, failure, success, selected, and destructive states during design, not afterward.
- Introduce new visual primitives only when existing tokens or components cannot express the approved direction cleanly.

### Avoid

- Designing before understanding content
- Decorative clutter that weakens hierarchy
- One-off values where semantic tokens are appropriate
- Replacing real behavior with static mock UI

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/references/visual-qa-process.md](../_shared/references/visual-qa-process.md) only when rendered parity or regression evidence is required.

## Validation steps

- Render representative mobile and desktop views.
- Check state completeness, long content, zoom, focus, and reduced motion.
- Compare against references and product goals, not only component specs.
- Confirm new patterns are reusable without unnecessary abstraction.

## Expected output

- Visual direction and rationale
- Responsive screen/component specifications
- Token and component extension decisions
- Rendered validation evidence and remaining trade-offs
