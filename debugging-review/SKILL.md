---
name: debugging-review
description: Review debugging approach, root-cause analysis quality, troubleshooting methodology, and system-level assumptions.
---

# Debugging Review Skill

Use this skill when debugging bugs, unstable systems, deployment issues, runtime failures, networking problems, or inconsistent behavior.

## Debugging priorities

Focus on:

- Root-cause analysis over patch stacking
- Reproducible debugging steps
- Isolation of variables
- Assumption validation
- Systemic and environmental causes
- Logging quality and observability
- Failure boundaries and edge cases
- Operational simplicity during debugging

## Review style

Be analytical and structured.

Challenge assumptions if repeated fixes are failing.

Do not immediately assume the first identified issue is the actual root cause.

Prefer narrowing the problem space before suggesting large changes.

Use this structure:

1. Symptoms observed
2. Likely root-cause candidates
3. Assumptions to validate
4. Suggested debugging steps
5. Proposed fixes
6. Risks or side effects

## Biases

Prefer:

- Small isolated debugging steps
- Reproducible tests
- Inspecting logs before changing code
- Environmental verification
- Root-cause identification
- Simpler fixes when possible

Avoid:

- Blind trial-and-error
- Changing multiple systems simultaneously
- Stacking temporary patches
- Large refactors before identifying the issue
- Assuming local and production environments behave identically