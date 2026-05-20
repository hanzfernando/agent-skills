---
name: security
description: Implement, harden, debug, and review security-sensitive code for web apps, APIs, authentication, authorization, cookies, JWTs, validation, secrets, encryption, data exposure, and public-facing features.
---

# Security Skill

Use this skill when implementing or reviewing authentication, authorization, APIs, sensitive data handling, environment variables, encryption, storage, or public-facing features.

## Core checks

Check for:

- Missing authorization checks
- Authenticated user trusting client-provided IDs
- Broken object-level authorization
- Overexposed API responses
- Missing input validation
- Unsafe redirects
- XSS risks
- CSRF risks when using cookies
- Insecure cookie settings
- JWT misuse
- Refresh token storage issues
- Leaked secrets or environment variables
- Sensitive logs
- Weak rate limiting
- Missing auditability for sensitive actions

## Cookie and JWT checks

For cookies, check:

- `httpOnly`
- `secure`
- `sameSite`
- appropriate expiration
- path/domain scope

For JWTs, check:

- short access token lifetime
- refresh token rotation where appropriate
- server-side invalidation strategy
- no sensitive data stored in token payload
- signature verification and algorithm safety

## Encryption checks

For encryption-related code:

- Do not invent custom crypto
- Ensure unique nonces/IVs where required
- Separate encryption and authentication concerns unless using AEAD like AES-GCM
- Never log plaintext secrets
- Be clear where keys are derived, stored, and used

## Security style

Use severity labels:

- Critical: exploitable or data-leaking issue
- Major: likely security weakness
- Minor: hardening improvement
- Suggestion: defense-in-depth

## Biases

Prefer:

- Server-side authorization
- Least privilege
- Explicit validation
- Safe defaults
- Defense in depth
- Clear threat model

Avoid:

- Security through obscurity
- Trusting frontend checks
- Logging sensitive values
- Broad wildcard permissions
- Storing secrets in client-accessible environments
