# Core Operating Rules

Load this file for any skill in the professional product-design and engineering pack.

## Work efficiently
- Search before reading. Inspect only files, symbols, routes, schemas, configs, and tests relevant to the request.
- Read targeted sections instead of entire directories or full large files.
- Understand the product goal, current behavior, constraints, and acceptance criteria before modifying anything.
- Preserve working architecture and real functionality unless evidence justifies a change.
- Reuse existing components, utilities, schemas, tokens, services, tests, and conventions.
- Make focused edits. Do not redesign, refactor, rename, or migrate unrelated areas.
- Record important assumptions and trade-offs; do not silently invent missing facts.

## Protect quality
- Maintain accessibility throughout user-facing work.
- Enforce authentication, authorization, ownership, and sensitive validation on trusted server boundaries.
- Test applicable loading, empty, partial, error, disabled, success, permission, recovery, focus, active, and destructive states.
- Measure performance when performance matters; do not substitute intuition for evidence.
- Run the smallest relevant validation first, then expand according to risk or failures.
- Do not claim completion until applicable checks pass or an exact blocker and residual risk are reported.

## Activate skills sparingly
1. Select the most specialised relevant skill as primary.
2. Add one architecture skill only when structural decisions are material.
3. Add one validation skill only when implementation or auditing requires it.
4. Use no more than three skills by default.
5. Do not load a broad skill when a specialised skill fully covers the request.

Recommended combinations:
- UI redesign: `premium-ui-designer` + `design-to-code-engineer` + `visual-qa-specialist`.
- Frontend architecture: `frontend-architecture-expert` + the framework engineer + `testing-quality-engineer`.
- Full-stack feature: `fullstack-system-architect` + `api-contract-designer` + `production-readiness-reviewer` only near release.
- Product motion: `motion-interaction-designer` + `frontend-performance-engineer` + `accessibility-specialist` when all three risks apply.
- Supabase backend: `supabase-architecture-expert` + `database-schema-architect` + `authentication-security-engineer` when platform, schema, and auth boundaries are all material.

## Communicate concisely
- Report only changes made, important decisions, validation results, and unresolved risks.
- Do not repeatedly narrate completed actions.
- Keep final responses concise unless detailed documentation is requested.
- Never sacrifice correctness, accessibility, security, or production quality to reduce tokens.
