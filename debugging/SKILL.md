---
name: debugging
description: Investigate and fix observed bugs, runtime or deployment failures, networking problems, and intermittent behavior, or review a root-cause investigation. Use when symptoms require reproduction, evidence gathering, and hypothesis testing; not general validation of working code.
---

# Debugging

## Workflow

1. Record the observed symptom, expected behavior, scope, environment, and timeline.
2. Reproduce the failure with the smallest reliable case; note when reproduction is unavailable.
3. Gather logs, traces, configuration, recent changes, and environmental differences before changing code.
4. Form competing hypotheses and rank them by evidence, likelihood, and diagnostic cost.
5. Test one variable at a time with reversible checks that can falsify each hypothesis.
6. Establish the root cause and affected boundary before a permanent fix. For urgent incidents, use reversible mitigation and distinguish recovery from causal proof.
7. Verify the fix against the reproduction, regressions, edge cases, and relevant environments.

Do not treat the first plausible issue as the root cause. If fixes repeatedly fail, revisit assumptions and systemic causes rather than stacking patches. Avoid blind trial-and-error, simultaneous multi-system changes, and large refactors before isolation.

## Distributed and production-only failures

When a bug spans services or only appears in production: use correlation/request IDs and distributed traces to follow a single request across boundaries rather than reasoning from isolated per-service logs. When local reproduction isn't possible, narrow the gap by comparing config, data shape, load, and dependency versions between environments instead of guessing.

## Flaky and intermittent failures

Keep temporary containment distinct from a verified fix. Look first for race conditions, shared mutable state, timing/ordering assumptions, retry/timeout interactions, and resource exhaustion under load. Capture the failure rate and correlating conditions (load, timing, specific inputs). Compare equivalent workloads before and after; a single passing rerun does not establish a fix.

## Reporting

Separate observations, hypotheses, mitigations, and established causes. Report relevant evidence and code/log locations, diagnostic results, fix, verification, and remaining uncertainty. State what evidence is missing when a cause remains unproven.
