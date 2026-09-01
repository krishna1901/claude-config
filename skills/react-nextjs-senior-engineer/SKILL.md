---
name: react-nextjs-senior-engineer
description: "Implement or debug production React and Next.js features using the repository's versions and conventions; not for framework-agnostic architecture planning alone."
---

# React Next.js Senior Engineer

## Activation conditions

Primary outcome: Deliver maintainable Next.js behavior that respects the exact installed version, rendering model, and deployment target.

Use this skill when:

- A React or Next.js feature, fix, route, component, or integration must be implemented.
- Server/client rendering, caching, forms, or deployment behavior needs expert handling.
- Existing Next.js code needs production hardening.

Do not use this skill when:

- The repository does not use React/Next.js.
- The user requests strategy only and no implementation.

## Required workflow

1. Inspect package versions, official versioned docs, and repository conventions.
2. Choose server and client ownership; keep client boundaries narrow.
3. Implement data access, caching, revalidation, Suspense, and errors deliberately.
4. Build semantic components, forms, validation, auth checks, metadata, images, and fonts.
5. Preserve real functionality and secure server-only data.
6. Add focused tests and observability for risky paths.
7. Run repository type, lint, test, build, and rendered UI checks.

## Skill-specific rules

### Confirm these inputs

- Package versions, Next config, router style, scripts, and deployment target
- Existing routes, components, data layer, auth, and design system
- Functional requirements, states, SEO, performance, and accessibility criteria
- API contracts and environment configuration

### Apply these decision rules

- Use framework capabilities supported by the installed version.
- Avoid unnecessary effects and duplicated state.
- Keep authorization and secrets server-side.
- Optimize measured bottlenecks rather than guessing.

### Resolve these domain decisions

- Use only APIs supported by the installed Next.js and React versions; confirm behavior in versioned documentation.
- Keep Server Components default where suitable and introduce client boundaries only for browser state or interaction.
- Define caching, revalidation, request memoization, invalidation, and dynamic rendering together for each data path.
- Keep secrets, privileged data access, authorization, and mutation validation on trusted server boundaries.
- Verify build output against the actual hosting target, runtime, image strategy, environment, and static-export constraints.

### Avoid

- Using APIs from a different Next.js version
- Making everything a client component
- Client-side authorization only
- Claiming completion without production build

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/frontend-architecture-principles.md](../_shared/references/frontend-architecture-principles.md) only when frontend ownership or dependency boundaries are material.
- Load [../_shared/references/design-quality-standards.md](../_shared/references/design-quality-standards.md) only when visual or interaction quality materially affects the result.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.

## Validation steps

- Run configured typecheck, lint, tests, and production build.
- Exercise critical routes, forms, auth states, caching, and error boundaries.
- Check metadata/SEO and responsive accessible rendering.
- Verify target deployment output and runtime configuration.

## Expected output

- Production code and tests
- Server/client and caching decisions
- Validation results
- Deployment or compatibility notes
