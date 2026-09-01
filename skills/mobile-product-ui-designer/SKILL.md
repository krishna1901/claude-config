---
name: mobile-product-ui-designer
description: "Design polished mobile product interfaces, navigation, touch behavior, gestures, keyboards, and native states; not for React Native implementation without design work."
---

# Mobile Product UI Designer

## Activation conditions

Primary outcome: Create mobile experiences that feel native, focused, reachable, and robust on iOS and Android.

Use this skill when:

- A React Native or Expo screen, flow, or navigation model needs design.
- Mobile-specific keyboard, gesture, safe-area, sheet, or platform behavior matters.
- A web concept must be adapted thoughtfully to mobile.

Do not use this skill when:

- The interface is web-only.
- A single known mobile style token is incorrect.

## Required workflow

1. Inspect the mobile repository, routes, primitives, and native dependencies.
2. Prioritize thumb-reachable actions and define navigation/back behavior.
3. Design safe-area, keyboard, sheet, modal, gesture, and permission interactions.
4. Specify default, loading, empty, offline, error, success, disabled, and destructive states.
5. Define iOS/Android differences only where platform expectations require them.
6. Protect performance with appropriate list, image, animation, and rendering choices.
7. Validate on representative devices, orientations, text scales, and input scenarios.

## Skill-specific rules

### Confirm these inputs

- User tasks, device/platform targets, and navigation context
- Existing Expo/React Native components, tokens, and platform conventions
- Safe-area, keyboard, gesture, offline, permission, and accessibility needs
- Content extremes and supported OS versions

### Apply these decision rules

- Respect native conventions without erasing product identity.
- Use accessible touch targets and visible feedback.
- Keep critical actions reachable when the keyboard is open.
- Avoid web layouts compressed into a phone shell.

### Resolve these domain decisions

- Use platform-specific behavior only when iOS or Android expectations materially differ for the task.
- Keep primary actions reachable with safe areas, dynamic text, software keyboards, and one-handed use.
- Define stack, tab, modal, sheet, deep-link, gesture, and system-back behavior as one coherent navigation model.
- Provide non-gesture alternatives and preserve user work across interruption, denial, offline states, and app restarts.
- Plan list virtualization, image loading, animation cost, and lower-end device behavior during interface design.

### Avoid

- Ignoring the Android back button
- Gesture-only actions without alternatives
- Fixed layouts that fail dynamic type
- Unnecessary platform divergence

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/references/motion-design-principles.md](../_shared/references/motion-design-principles.md) only when motion behavior or animation implementation is in scope.

## Validation steps

- Test iOS and Android behavior where supported.
- Check small/large phones, orientation, safe areas, keyboard, gestures, and back navigation.
- Validate screen reader, dynamic text, contrast, reduced motion, and touch targets.
- Inspect performance on representative lower-end hardware.

## Expected output

- Mobile screen and flow specifications
- Platform behavior and state matrix
- Token/component reuse decisions
- Device-level validation evidence
