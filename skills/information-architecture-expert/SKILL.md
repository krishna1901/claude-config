---
name: information-architecture-expert
description: "Structure navigation, routes, taxonomy, labels, search, and content relationships for scalable products; not for visual styling or interaction microdetails."
---

# Information Architecture Expert

## Activation conditions

Primary outcome: Create an information model that matches user mental models while remaining stable as content and capabilities grow.

Use this skill when:

- Navigation, routes, labels, taxonomy, or discoverability need design.
- A product is adding many content types, roles, filters, or admin areas.
- Search and browse behavior lacks a coherent model.

Do not use this skill when:

- Only colors, typography, or component styling are changing.
- A single page has no meaningful relationship to broader content.

## Required workflow

1. Inspect routes, navigation, content models, and observed findability issues.
2. Inventory and group content by user task, entity, lifecycle, and access.
3. Define taxonomy, canonical labels, synonyms, metadata, and governance.
4. Design route hierarchy, primary/secondary navigation, breadcrumbs, and cross-links.
5. Specify search, filters, sorting, facets, defaults, zero-results, and saved states.
6. Test representative findability tasks and growth scenarios.
7. Document URL, redirect, permission, localization, and migration implications.

## Skill-specific rules

### Confirm these inputs

- Audience tasks and vocabulary
- Content inventory, types, metadata, ownership, lifecycle, and volume
- Existing routes, analytics, search logs, permissions, and SEO constraints
- Growth scenarios and localization requirements

### Apply these decision rules

- Prefer user language over internal organization names.
- Keep categories mutually intelligible even when not perfectly exclusive.
- Expose location and scope; avoid mystery-meat navigation.
- Preserve stable URLs and compatibility where feasible.

### Resolve these domain decisions

- Base grouping and labels on user tasks and vocabulary rather than internal teams or implementation modules.
- Define ownership and change governance for taxonomy, metadata, synonyms, redirects, and deprecated labels.
- Preserve stable canonical URLs while allowing navigation and presentation to evolve independently.
- Prevent restricted content from leaking through navigation, counts, search suggestions, or filter metadata.
- Test findability with realistic tasks, ambiguous terms, long labels, localization, and future content growth.

### Avoid

- Mirroring the org chart
- Adding navigation items without hierarchy
- Filters without clear semantics or removable state
- Changing URLs without redirects or analytics consideration

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.

## Validation steps

- Run tree-testing or scenario walkthroughs for key tasks.
- Check orphan pages, duplicate concepts, ambiguous labels, and permission leaks.
- Verify mobile, keyboard, search, and deep-link discoverability.
- Stress the model with future content volume and localization.

## Expected output

- Route and navigation map
- Taxonomy, labels, metadata, and governance rules
- Search/filter/sort behavior specification
- Migration, redirect, and validation plan
