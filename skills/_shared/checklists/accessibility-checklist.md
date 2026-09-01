# Accessibility Checklist

Apply the relevant checks; document anything that cannot be verified.

## Structure and semantics
- Use correct headings, landmarks, lists, tables, links, buttons, and native form controls.
- Give every control an accessible name and every meaningful image useful alternative text.
- Keep DOM and reading order aligned with visual order.

## Keyboard and focus
- Reach every interactive element using a keyboard without traps.
- Show a visible focus indicator and logical focus order.
- Move focus deliberately for dialogs, routes, errors, and dynamic disclosures; restore it on close.
- Provide skip navigation when repeated navigation makes it useful.

## Forms and feedback
- Associate labels, descriptions, requirements, and errors programmatically.
- Announce asynchronous status and validation changes without excessive live-region noise.
- Preserve entered data after recoverable errors and focus the first actionable problem.

## Visual and responsive access
- Verify text and non-text contrast, target sizes, reflow at 400% zoom, text resizing, and responsive orientation.
- Never encode status only through color, position, sound, or animation.
- Support reduced motion and avoid flashing or vestibular triggers.

## Complex UI and data
- Give dialogs, tabs, menus, comboboxes, grids, and charts appropriate semantics and keyboard behavior.
- Provide accessible names, summaries, values, and tabular or textual alternatives for visualizations.
- Test touch exploration and screen-reader announcements on supported mobile platforms when relevant.

## Validation evidence
- Run the repository's automated accessibility checks.
- Manually test keyboard-only navigation, focus, zoom/reflow, and at least one relevant screen reader when feasible.
- Report tool, browser/device, scope, failures, fixes, and remaining risks.
