---
name: typography-art-director
description: "Select and implement professional type systems, scales, hierarchy, loading, and localization behavior; not for general layout design or minor text-style fixes."
---

# Typography Art Director

## Activation conditions

Primary outcome: Make typography carry hierarchy, voice, density, and readability across product contexts and languages.

Use this skill when:

- A product needs a new or repaired type system.
- Brand expression and readability depend on font selection or hierarchy.
- Localization, numerical data, or font loading creates systemic issues.

Do not use this skill when:

- A single known token is applied incorrectly.
- The task is unrelated to text rendering or hierarchy.

## Required workflow

1. Audit current type usage, content hierarchy, and rendering problems.
2. Assign font roles and build resilient fallback stacks with metric compatibility.
3. Define display, heading, body, label, caption, code, and numerical styles.
4. Set responsive scales, line heights, tracking, measure, and weight hierarchy.
5. Specify localization, truncation, wrapping, tabular numerals, and variable-font behavior.
6. Implement loading, subsetting, preload, swap, and layout-shift strategy.
7. Validate on real content, devices, zoom levels, and supported scripts.

## Skill-specific rules

### Confirm these inputs

- Audience, brand voice, content types, and reading contexts
- Existing fonts, licenses, tokens, browser/platform support
- Languages, scripts, numerals, and accessibility needs
- Performance budget and deployment constraints

### Apply these decision rules

- Optimize for reading and task clarity before novelty.
- Use few intentional weights and styles.
- Keep line length and vertical rhythm appropriate to context.
- Avoid faux weights and inaccessible low-contrast type.

### Resolve these domain decisions

- Assign explicit roles to display, heading, body, label, caption, code, and numerical typography.
- Choose fallback fonts by metric compatibility, script coverage, platform availability, and brand tolerance.
- Define line length, leading, tracking, truncation, wrapping, and responsive scale from actual content contexts.
- Specify tabular numerals, decimal alignment, signs, units, dates, and localization for data-heavy interfaces.
- Balance font subsetting, preloading, swap behavior, licensing, and layout stability against visual goals.

### Avoid

- Choosing fonts only by trend
- Too many weights or decorative styles
- Fixed sizes that fail zoom or small screens
- Ignoring fallback metrics and localization

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.

## Validation steps

- Measure font payload and layout shift.
- Test missing font, slow network, long text, localization, and 200%-400% zoom.
- Check heading hierarchy, truncation, numerical alignment, and platform rendering.
- Confirm licensing and self-hosting/CDN constraints.

## Expected output

- Typography rationale and font-role map
- Responsive semantic type tokens
- Font loading and fallback implementation plan
- Validation captures and performance evidence
