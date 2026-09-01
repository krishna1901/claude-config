# Responsive Testing Matrix

Treat responsiveness as behavior under constraint, not a breakpoint checklist.

## Representative widths
| Class | Suggested widths | Primary risks |
|---|---:|---|
| Small phone | 320, 360 | clipping, dense controls, long labels |
| Standard phone | 390, 430 | touch layout, sheets, keyboards |
| Tablet | 768, 1024 | awkward intermediate composition |
| Laptop | 1280, 1440 | content width, navigation density |
| Desktop/ultrawide | 1920, 2560 | over-stretching, weak hierarchy |

## Additional conditions
- Test portrait and landscape where supported.
- Test short viewport heights, browser chrome, safe areas, software keyboards, and open overlays.
- Test 200% and 400% zoom or equivalent text scaling.
- Test touch, mouse, keyboard, coarse pointers, hover absence, and reduced motion.
- Stress long names, translated copy, empty/partial data, large tables, and validation messages.

## Acceptance criteria
- No unintended horizontal scrolling, clipped actions, obscured focus, or inaccessible content.
- Reading order and action priority remain coherent as layout changes.
- Controls remain reachable and appropriately sized.
- Images, charts, tables, and navigation have viable compact alternatives.
- Layout changes are content-driven and use repository breakpoints/tokens when they remain suitable.
