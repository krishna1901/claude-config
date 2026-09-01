# Design Quality Standards

Use this reference when design judgment or implementation fidelity materially affects the result.

## Product identity
- Derive a recognizable visual language from the product, audience, content, and brand assets.
- Prefer a small number of strong compositional ideas over decorative variety.
- Avoid generic dashboard templates, arbitrary gradients, excessive glass effects, card-per-section layouts, and ornamental clutter.

## Hierarchy and composition
- Establish one clear primary action or reading path per view.
- Use type, spacing, alignment, contrast, and density intentionally; do not rely on color alone.
- Keep related content together and separate unrelated content with meaningful rhythm.
- Preserve scanability for long, localized, dynamic, and user-generated content.

## System discipline
- Reuse repository tokens and components before adding new ones.
- Express new values as semantic tokens when they recur or carry meaning.
- Define component anatomy, variants, interactive states, and content limits before proliferating components.
- Maintain coherent behavior across light/dark themes and supported platforms.

## State completeness
- Design default, loading, empty, partial, error, disabled, success, hover, focus, active, selected, and destructive states where applicable.
- Keep recovery actions close to the failure and preserve user input whenever safe.
- Distinguish unavailable, pending, and failed states instead of collapsing them into generic disabled UI.

## Implementation and validation
- Inspect the rendered interface, not only source code.
- Check representative desktop and mobile sizes, long content, zoom, keyboard use, and reduced motion.
- Verify contrast, focus visibility, target size, overflow, wrapping, and stable layout during loading.
- Record intentional deviations from references and the product reason for each.
