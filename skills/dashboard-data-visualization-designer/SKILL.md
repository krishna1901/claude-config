---
name: dashboard-data-visualization-designer
description: "Design decision-oriented dashboards, KPIs, tables, charts, filters, and numerical states for data products; not for generic page styling or data analysis alone."
---

# Dashboard Data Visualization Designer

## Activation conditions

Primary outcome: Turn metrics into an interface that supports specific decisions without overstating the evidence.

Use this skill when:

- A dashboard, scorecard, reporting surface, or analytical table needs design.
- KPI hierarchy and interactions must support monitoring or diagnosis.
- Existing visualizations are misleading, inaccessible, or unresponsive.

Do not use this skill when:

- A chart is purely decorative.
- The request is statistical analysis with no dashboard experience.

## Required workflow

1. Inspect metric definitions, data limitations, and current reporting behavior.
2. Prioritize KPIs by decision value and define context, target, and comparison.
3. Choose tables/charts by analytical task and encode quantities honestly.
4. Design filters, sorting, cross-filtering, drill-down, annotations, and saved states.
5. Specify loading, stale, partial, missing, zero, error, and permission states.
6. Create responsive and accessible alternatives with consistent number/date formatting.
7. Validate interpretation with representative users and realistic data extremes.

## Skill-specific rules

### Confirm these inputs

- Users, decisions, actions, cadence, and definitions
- Data grain, freshness, quality, uncertainty, and permissions
- Comparison periods, targets, segments, and drill-down paths
- Existing components, chart libraries, viewports, and export needs

### Apply these decision rules

- Never imply precision the data does not support.
- Keep scales, units, periods, and denominators visible.
- Use color redundantly and consistently.
- Make the next action or diagnostic path clear.

### Resolve these domain decisions

- Include a metric only when it informs a defined decision, comparison, diagnosis, or action.
- Keep units, denominators, time ranges, freshness, targets, and comparison bases visible at interpretation points.
- Represent missing, delayed, partial, estimated, and suppressed values without implying zero or false precision.
- Design filter, drill-down, annotation, export, and shared-state behavior before selecting decorative chart treatments.
- Provide textual or tabular alternatives and redundant encodings for every decision-critical visualization.

### Avoid

- Choosing charts for visual novelty
- Truncated axes or inconsistent units
- KPI cards without context or action
- Hiding data-quality limitations

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.

## Validation steps

- Check calculations and labels against source definitions.
- Test sparse, dense, negative, outlier, stale, and partial data.
- Verify keyboard access, screen-reader summaries, contrast, and tabular alternatives.
- Test filters, URL/share state, export, and responsive fallbacks.

## Expected output

- Dashboard information hierarchy
- Chart/table/filter interaction specifications
- State and formatting rules
- Accessibility and data-interpretation validation evidence
