---
name: security
description: Implement, harden, debug, and review security-sensitive web or API behavior involving authentication, authorization, trust-boundary validation, sessions, secrets, cryptography, uploads, outbound requests, or sensitive data exposure. Use for concrete abuse risks or security reviews; public-facing UI alone is not sufficient.
---

# Security

## Principle

Existing conventions do not justify insecure behavior. Follow established patterns for style and structure, but flag insecure conventions even when they're already in place — do not propagate them into new code. Use OWASP ASVS / Top 10 as a baseline lens, not a checklist to satisfy mechanically.

## Core checks

- Define the assets, actors, trust boundaries, entry points, and plausible abuse cases.
- Enforce authentication and object/action-level authorization server-side, including tenant boundaries; never trust client-provided identity or frontend checks.
- Validate and constrain input; encode output and protect against injection, XSS, unsafe redirects, and path abuse.
- Protect cookie flows against CSRF and configure `httpOnly`, `secure`, `sameSite`, expiration, path, and domain deliberately.
- Minimize API responses, permissions, secret exposure, sensitive logs, and client-accessible configuration.
- Apply rate limits, auditability, and secure failure behavior to sensitive actions.
- For user-influenced outbound requests, constrain schemes/destinations and validate resolved addresses at connection time; disable or revalidate redirects. Prevent DNS rebinding and unintended access to internal/private or metadata endpoints.
- For uploads, allowlist formats and verify actual content, not just declared MIME types/extensions. Bound size, generate safe storage names, control access/execution, and scan or re-encode when risk warrants it.

## Credentials and secrets

Hash passwords with a modern adaptive algorithm (argon2id preferred, bcrypt acceptable) using the project's established cost factor, or a safe default if none exists. Never store or log plaintext passwords or secrets. Load secrets from environment/secret managers, not source control. Check changed files for exposure; for leaks, identify revocation/rotation needs and history/artifact exposure, not just deletion.

## Tokens and cryptography

For JWTs, verify signatures, allowed algorithms, issuer, audience, expiry, and applicable not-before claims. Use short-lived access tokens, rotate refresh tokens where appropriate, define revocation/invalidation, and exclude sensitive payload data.

Do not invent cryptography. Use established authenticated encryption such as AES-GCM, unique nonces/IVs as required, managed key storage and rotation, and explicit key derivation and use.

## Headers and dependencies

Apply headers for the serving context: CSP and frame restrictions for documents, deliberate content types for APIs, and HSTS where HTTPS deployment supports it. Check required scripts, embeds, and cookie flows.

For dependency changes, use available audit/scanning tools and assess advisory reachability and fixes; preserve reproducible versions through the project's lockfile policy.

## Review output

Prioritize exploitable findings with code location, attack prerequisites/path, impact, evidence, and remediation. Separate confirmed vulnerabilities from unverified risks. Verify relevant denial cases, including cross-user access and invalid tokens. Use labels when helpful:

- **Critical:** directly exploitable or severe data exposure.
- **Major:** likely weakness with meaningful impact.
- **Minor:** limited hardening gap.
- **Suggestion:** defense in depth.

Prefer least privilege, explicit validation, safe defaults, and layered defenses. Do not rely on obscurity or wildcard permissions.
