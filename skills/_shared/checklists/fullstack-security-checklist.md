# Full-Stack Security Checklist

## Trust boundaries
- Inventory users, services, data classes, entry points, privileged operations, and external providers.
- Keep authentication, authorization, entitlement, and ownership checks server-side for every sensitive operation.
- Deny by default and scope service credentials to the minimum capability.

## Inputs and outputs
- Validate type, shape, length, range, encoding, and ownership at trusted boundaries.
- Use parameterized queries and safe framework escaping; review XSS, injection, SSRF, path traversal, and unsafe deserialization risks.
- Restrict uploads by type, size, storage path, access policy, and scanning needs.

## Sessions and secrets
- Use secure cookie/token settings, rotation, expiry, revocation, CSRF protection, and safe redirect allowlists.
- Store secrets outside source and client bundles; prevent secrets and sensitive payloads from logs.
- Verify OAuth state/nonce/PKCE and webhook signatures with replay protection.

## Data and abuse
- Enforce database constraints and row-level policies where used; test cross-user and cross-tenant denial.
- Apply idempotency, rate limits, quotas, deduplication, and abuse controls to costly or sensitive operations.
- Define retention, deletion, backup, restore, and privacy handling for personal data.

## Release evidence
- Run dependency and secret scans available in the repository.
- Test unauthorized, expired, tampered, replayed, and malformed requests.
- Review environment separation, production credentials, logging redaction, alerts, and incident rollback.
- Record residual risk and owner; never describe unverified security as guaranteed.
