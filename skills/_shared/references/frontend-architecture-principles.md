# Frontend Architecture Principles

## Inspect and map
- Read the installed framework version, routes, build configuration, package scripts, conventions, and representative features before proposing structure.
- Identify server/client boundaries, data ownership, state lifetimes, API clients, error handling, testing seams, and dependency direction.

## Boundaries and ownership
- Organize around product capabilities where possible; keep shared code genuinely cross-cutting.
- Give each state one authoritative owner and derive rather than synchronize duplicate state.
- Keep remote state, URL state, form state, and ephemeral UI state distinct.
- Prevent lower-level modules from importing feature or route layers.

## Rendering and data
- Fetch near the server or feature boundary that owns the data.
- Define cache keys, invalidation, freshness, optimistic behavior, cancellation, and retry policy explicitly.
- Keep client boundaries narrow and intentional; do not move secrets or authorization decisions into the browser.

## Components and change
- Prefer composition and clear props over giant components, prop drilling, or speculative abstraction.
- Reuse existing primitives and conventions before adding libraries or architectural layers.
- Introduce migration seams and incremental steps when changing working architecture.

## Reliability
- Model loading, empty, partial, error, retry, and success states.
- Add error boundaries and observability at meaningful ownership boundaries.
- Test contracts and high-risk user behavior rather than implementation trivia.
- Validate bundle, rendering, navigation, and accessibility impact before completion.
