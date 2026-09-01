# Visual QA Process

## Establish the baseline
1. Identify the authoritative reference, supported viewports, themes, and content states.
2. Run the real application with representative data; do not replace functioning behavior with mocks.
3. Capture deterministic screenshots with stable fonts, animations, time, and viewport settings.

## Compare systematically
- Compare global composition before local details: canvas, containers, columns, rhythm, then type and controls.
- Check typography, spacing, alignment, color, borders, radii, shadows, icons, wrapping, overflow, and image treatment.
- Inspect loading, empty, error, disabled, success, hover, focus, active, selected, and overlay states.
- Use overlays or image diffs when references are precise; separate rendering noise from meaningful discrepancies.

## Fix loop
1. Rank discrepancies by visual impact and systemic cause.
2. Fix tokens, shared primitives, or layout rules before one-off offsets.
3. Re-capture every affected viewport and state after each systemic change.
4. Confirm no unrelated screen regressed.

## Completion evidence
- Record viewport, browser/device, route/state, reference, before/after capture, and remaining intentional differences.
- Do not claim parity from code inspection alone.
