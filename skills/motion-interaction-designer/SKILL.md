---
name: motion-interaction-designer
description: "Design or implement purposeful product UI animation, transitions, gestures, and micro-interactions with reduced-motion support; not for promotional videos or storyboards."
---

# Motion Interaction Designer

## Activation conditions

Primary outcome: Use motion to clarify product behavior while keeping interactions immediate, accessible, and performant.

Use this skill when:

- State transitions or gestures need clearer causality and continuity.
- A product interaction needs motion specifications or implementation.
- Existing motion feels inconsistent, distracting, or slow.

Do not use this skill when:

- The motion is a promotional video or branded sequence.
- Animation adds no hierarchy, feedback, or spatial meaning.

## Required workflow

1. Inspect current interactions and motion language.
2. Define the communicative purpose and no-motion fallback for each transition.
3. Specify trigger, origin, destination, properties, duration, easing, delay, interruption, and completion state.
4. Design gesture continuity, cancellation, and velocity behavior.
5. Create reduced-motion alternatives that preserve state meaning.
6. Implement with compositor-friendly techniques and existing primitives.
7. Test frame pacing, interruption, focus, and repeated-use speed.

## Skill-specific rules

### Confirm these inputs

- User action, state transition, hierarchy, and desired perception
- Existing motion tokens, components, libraries, and performance constraints
- Input modes, platform expectations, reduced-motion requirements
- Representative device/browser matrix

### Apply these decision rules

- Keep feedback immediate and repeated transitions brief.
- Coordinate motion around attention, not decoration.
- Never block critical action behind animation.
- Preserve focus, reading order, and reduced-motion access.

### Resolve these domain decisions

- Require each animation to communicate state, causality, hierarchy, continuity, spatial relationship, or immediate feedback.
- Specify interruption, reversal, cancellation, repeated activation, and final-state ownership for every interactive transition.
- Keep direct-manipulation motion coupled to input position and velocity without delayed decorative choreography.
- Provide reduced-motion behavior that preserves status and causality without large movement, parallax, or flashing.
- Measure frame pacing and main-thread cost on representative devices before approving layout-heavy animation.

### Avoid

- Animating every element
- Long transitions on frequent actions
- Layout-heavy animation without measurement
- Using promotional choreography inside routine UI

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/motion-design-principles.md](../_shared/references/motion-design-principles.md) only when motion behavior or animation implementation is in scope.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.

## Validation steps

- Test slow/fast input, interruption, cancellation, and rapid repetition.
- Verify reduced-motion behavior.
- Measure frame pacing and main-thread impact on representative devices.
- Check hover absence, keyboard, touch, and screen changes.

## Expected output

- Motion rationale and state-transition map
- Timing/easing/gesture specifications
- Implementation or component motion tokens
- Reduced-motion and performance evidence
