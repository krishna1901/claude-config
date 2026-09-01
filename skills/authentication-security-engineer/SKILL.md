---
name: authentication-security-engineer
description: "Implement or review authentication, authorization, sessions, roles, secrets, webhooks, abuse controls, and secure boundaries; not for general architecture without security scope."
---

# Authentication Security Engineer

## Activation conditions

Primary outcome: Protect sensitive operations through explicit trust boundaries, least privilege, and testable failure behavior.

Use this skill when:

- Auth, sessions, OAuth, permissions, roles, RLS, secrets, or sensitive flows are changing.
- A product needs threat modeling or security hardening.
- Uploads, webhooks, abuse, or privileged operations need controls.

Do not use this skill when:

- The task has no security boundary or sensitive data.
- The user asks for unsupported guarantees or formal certification.

## Required workflow

1. Inspect the full auth and authorization path from UI to data.
2. Threat-model credential, session, authorization, input, browser, provider, and abuse risks.
3. Implement secure session/token settings and OAuth state, nonce, PKCE, redirect controls.
4. Enforce server-side roles, ownership, entitlements, and RLS for every sensitive operation.
5. Harden inputs, outputs, uploads, webhooks, secrets, logs, dependencies, and rate limits.
6. Add negative tests for tampering, replay, expiry, cross-user access, and malformed input.
7. Document residual risk, monitoring, rotation, and incident recovery.

## Skill-specific rules

### Confirm these inputs

- Actors, assets, roles, ownership, threats, and trust boundaries
- Auth providers, session/token model, server endpoints, RLS, and secrets
- Sensitive workflows, uploads, webhooks, logs, and rate limits
- Deployment environments, compliance constraints, and incident history

### Apply these decision rules

- Deny by default and minimize credential scope.
- Never trust client-visible roles or object ownership.
- Avoid secrets and sensitive payloads in source, bundles, URLs, or logs.
- Prefer established primitives over custom cryptography.

### Resolve these domain decisions

- Map credentials, sessions, tokens, claims, roles, ownership, entitlements, and revocation across every trust boundary.
- Validate OAuth redirect allowlists, state, nonce, PKCE, provider claims, account linking, and error recovery.
- Authorize each sensitive operation against trusted current data instead of accepting client-provided role or owner fields.
- Define expiry, rotation, revocation, logout, device loss, replay protection, and concurrent-session behavior.
- Apply abuse controls and logging without exposing secrets, tokens, personal data, or exploitable security detail.

### Avoid

- Client-side authorization only
- Security through hidden UI
- Logging tokens or secrets
- Claiming secure without adversarial tests

### Load references selectively

- Load [../_shared/references/core-operating-rules.md](../_shared/references/core-operating-rules.md) before starting.
- Load [../_shared/checklists/fullstack-security-checklist.md](../_shared/checklists/fullstack-security-checklist.md) only when trusted boundaries, sensitive data, or privileged operations are involved.
- Load [../_shared/checklists/production-readiness-checklist.md](../_shared/checklists/production-readiness-checklist.md) only when release, migration, deployment, or operational readiness is in scope.

## Validation steps

- Run dependency/secret scans available in the repository.
- Test unauthorized, forbidden, expired, replayed, tampered, and cross-tenant cases.
- Verify cookie/token flags, CSRF, redirects, webhook signatures, uploads, and logging redaction.
- Confirm alerting, key rotation, revocation, and rollback paths.

## Expected output

- Threat model and trust-boundary map
- Security implementation or remediation
- Negative test evidence
- Residual risk and operational controls
