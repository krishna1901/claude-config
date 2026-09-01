---
name: react-native-expo-engineer
description: "Implement or debug production React Native and Expo apps, navigation, native capabilities, builds, and releases; not for mobile interface design without code."
---

# React Native Expo Engineer

## Activation conditions

Primary outcome: Deliver release-ready mobile behavior using the exact installed Expo SDK and repository conventions.

Use this skill when:

- An Expo or React Native feature, integration, bug fix, or release task needs implementation.
- Navigation, native permissions, notifications, deep links, storage, or builds are involved.
- Mobile performance or accessibility needs code-level remediation.

Do not use this skill when:

- The task is web-only React/Next.js.
- The project is native-only and does not use Expo, unless the user requests a migration.

## Required workflow

1. Inspect the repository and read exact versioned Expo documentation before coding.
2. Map routes, platform/native boundaries, state, persistence, and service ownership.
3. Implement navigation, permissions, storage, networking, notifications, gestures, and animations with platform-safe fallbacks.
4. Handle loading, offline, denial, error, retry, background, and deep-link states.
5. Keep secrets and authorization off-device where required.
6. Add focused tests and verify development/build prerequisites.
7. Run app-specific checks and validate on representative iOS/Android devices or builds.

## Skill-specific rules

### Confirm these inputs

- Expo SDK and package versions, app config, router, build profiles, and native identifiers
- Existing components, stores, services, auth, and design system
- Platform requirements, permissions, deep links, offline behavior, and release targets
- Device matrix and acceptance criteria

### Apply these decision rules

- Use Expo-supported APIs for the installed SDK.
- Respect safe areas, keyboards, back behavior, touch targets, and reduced motion.
- Avoid unnecessary native divergence and blocking JS-thread work.
- Preserve build identifiers and auth contracts unless explicitly changing them.

### Resolve these domain decisions

- Read exact installed Expo SDK documentation before using config plugins, native modules, builds, or platform APIs.
- Preserve bundle identifiers, schemes, signing, OAuth contracts, deep links, and build-profile assumptions unless explicitly changed.
- Model permission unavailable, denied, limited, blocked, and revoked states with platform-appropriate recovery.
- Keep persistence, offline queues, background behavior, and synchronization ownership explicit and testable.
- Validate native functionality in a compatible development or release build, not only Expo web or bundle checks.

### Avoid

- Coding from current docs without matching the installed SDK
- Testing native features only in a browser
- Ignoring permission denial and Android back behavior
- Putting privileged secrets in the client

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/references/frontend-architecture-principles.md](../_shared/references/frontend-architecture-principles.md) only when frontend ownership or dependency boundaries are material.
- Load [../_shared/checklists/accessibility-checklist.md](../_shared/checklists/accessibility-checklist.md) only when accessibility acceptance or remediation is in scope.
- Load [../_shared/checklists/responsive-testing-matrix.md](../_shared/checklists/responsive-testing-matrix.md) only when a user interface must adapt across viewports or input modes.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.
- Load [../_shared/references/motion-design-principles.md](../_shared/references/motion-design-principles.md) only when motion behavior or animation implementation is in scope.

## Validation steps

- Run app-only typecheck, lint, and tests.
- Exercise navigation, permissions, offline, deep links, and notification states.
- Verify accessibility, performance, and platform behavior on devices/simulators.
- Confirm build configuration and release readiness for both platforms in scope.

## Expected output

- Production mobile implementation and tests
- Platform/configuration changes
- Device/build validation evidence
- Known platform constraints and release notes
