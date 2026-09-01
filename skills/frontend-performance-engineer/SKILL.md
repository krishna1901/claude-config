---
name: frontend-performance-engineer
description: "Measure and improve Core Web Vitals, rendering, bundles, hydration, networks, images, fonts, and runtime responsiveness; not for unmeasured style optimization."
---

# Frontend Performance Engineer

## Activation conditions

Primary outcome: Improve web user-perceived and runtime performance through reproducible measurement and prioritized root-cause fixes.

Use this skill when:

- Core Web Vitals, startup, route transition, input, scroll, or memory performance is poor.
- A release needs a performance budget and evidence.
- Bundle, hydration, images, fonts, caching, or third parties need investigation.

Do not use this skill when:

- No measurable performance objective exists.
- The proposed change is a speculative micro-optimization with negligible user impact.

## Required workflow

1. Define representative scenarios, metrics, budgets, and a reproducible baseline.
2. Profile network, main thread, rendering, memory, bundle, hydration, images, fonts, and third parties.
3. Attribute bottlenecks to specific code, assets, or architecture.
4. Prioritize by user impact, reach, confidence, and implementation risk.
5. Implement the smallest durable fixes while preserving behavior.
6. Re-measure under identical conditions and check regressions.
7. Document before/after evidence, variance, and remaining bottlenecks.

## Skill-specific rules

### Confirm these inputs

- Target devices, networks, browsers, routes, and user journeys
- Current analytics/RUM, lab traces, budgets, and regressions
- Repository build, bundle, rendering, data, image, font, and third-party setup
- Functional constraints and acceptable trade-offs

### Apply these decision rules

- Measure on representative lower-end devices and realistic networks.
- Optimize critical-path work before low-impact bytes.
- Protect accessibility and visual quality.
- Use budgets and regression checks for sustained gains.

### Resolve these domain decisions

- Use field data for user impact and controlled lab traces for diagnosis; do not treat either source as sufficient alone.
- Set route and journey budgets for loading, interaction, layout stability, memory, JavaScript, images, and fonts.
- Prioritize critical-path and main-thread bottlenecks by reach and measured delay before low-impact bundle cleanup.
- Control device, network, cache, data, and sample count when comparing before-and-after results.
- Add regression protection for durable gains and document trade-offs that shift cost between metrics or user groups.

### Avoid

- Reporting Lighthouse alone as production truth
- Optimizing without a baseline
- Removing functionality or accessibility to improve a score
- Caching data without freshness or invalidation rules

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/frontend-architecture-principles.md](../_shared/references/frontend-architecture-principles.md) only when frontend ownership or dependency boundaries are material.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.

## Validation steps

- Collect multiple baseline and post-change samples.
- Run production builds and route-level traces.
- Check Core Web Vitals, interaction latency, memory, and bundle deltas.
- Verify functionality, accessibility, and visual behavior after optimizations.

## Expected output

- Performance baseline and budget
- Prioritized bottleneck analysis
- Scoped optimizations
- Before/after evidence and residual risks
