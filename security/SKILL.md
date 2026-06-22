---
name: security
description: Implement, harden, debug, and review security-sensitive code for web apps, APIs, authentication, authorization, cookies, JWTs, validation, secrets, encryption, data exposure, and public-facing features.
---

# Security

## Core checks

- Define the assets, actors, trust boundaries, entry points, and plausible abuse cases.
- Enforce authentication and object/action-level authorization server-side; never trust client-provided identity or frontend checks.
- Validate and constrain input; encode output and protect against injection, XSS, unsafe redirects, and path abuse.
- Protect cookie flows against CSRF and configure `httpOnly`, `secure`, `sameSite`, expiration, path, and domain deliberately.
- Minimize API responses, permissions, secret exposure, sensitive logs, and client-accessible configuration.
- Apply rate limits, auditability, and secure failure behavior to sensitive actions.

## Tokens and cryptography

For JWTs, verify signatures and allowed algorithms, use short-lived access tokens, rotate refresh tokens where appropriate, define revocation/invalidation, and exclude sensitive payload data.

Do not invent cryptography. Use established authenticated encryption such as AES-GCM, unique nonces/IVs as required, managed key storage and rotation, and explicit key derivation and use. Never log plaintext secrets.

## Review output

Prioritize exploitable findings and explain the attack path, impact, evidence, and remediation. Use labels when helpful:

- **Critical:** directly exploitable or severe data exposure.
- **Major:** likely weakness with meaningful impact.
- **Minor:** limited hardening gap.
- **Suggestion:** defense in depth.

Prefer least privilege, explicit validation, safe defaults, and layered defenses. Do not rely on obscurity or wildcard permissions.
