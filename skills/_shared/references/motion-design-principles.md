# Motion Design Principles

## Communicative value
- Animate to explain causality, hierarchy, continuity, spatial relationships, feedback, or status.
- Remove motion that only decorates, delays, distracts, or competes with the primary task.

## Timing and choreography
- Choose duration from distance, complexity, and user control rather than a universal preset.
- Use easing that reflects entry, exit, interruption, and direct manipulation.
- Coordinate parent/child and list motion so attention follows the intended order.
- Keep repeated interactions faster than first-time explanatory transitions.

## Interaction and accessibility
- Preserve input continuity during gesture-driven motion and define cancellation/interruption behavior.
- Provide a reduced-motion treatment that preserves meaning without large transforms or parallax.
- Avoid flashing, unexpected autoplay, and motion that blocks reading or action.

## Performance
- Prefer compositor-friendly transforms and opacity for frequent UI motion.
- Measure frame pacing and main-thread cost on representative devices.
- Avoid animating layout-heavy properties across large trees unless measured and justified.

## Context distinction
- Keep product micro-interactions brief, responsive, and subordinate to the task.
- Treat promotional sequences as authored narratives with storyboards, timing maps, asset plans, and explicit playback controls.
