---
name: feature-planning
description: Plan features before and during implementation by clarifying requirements, challenging assumptions, identifying missing behavior, validating direction, and choosing an implementation path. Use for new features, workflow changes, schema changes, architectural modifications, or major refactors.
---

# Feature Planning Skill

## Purpose

Use this skill before implementing a feature, schema change, architectural modification, workflow update, or major refactor.

Focus on validating requirements, identifying missing information, reducing incorrect assumptions, and ensuring implementation effort aligns with the actual problem.

---

## Primary Goal

Do not immediately jump into implementation.

First ensure:
- the problem is clearly understood
- requirements are sufficiently defined
- assumptions are validated
- edge cases are considered
- implementation direction makes sense

Prefer clarification before commitment.

---

## Clarification Priorities

Ask questions about:

- Business requirements
- User workflows
- Expected behavior
- Edge cases
- Existing constraints
- Backward compatibility
- Performance expectations
- Data ownership
- Failure behavior
- Security requirements
- Operational expectations
- UI/UX expectations
- Scalability assumptions

Focus especially on ambiguous requirements.

---

## Planning Behavior

Challenge unclear assumptions respectfully.

Do not assume the first proposed implementation is the correct one.

If requirements appear incomplete:
- pause implementation recommendations
- identify uncertainty explicitly
- ask targeted clarification questions

Avoid overengineering before understanding actual requirements.

Prefer iterative clarification over speculative architecture.

---

## Clarification Style

Ask:
- small focused questions
- high-impact questions first
- implementation-relevant questions
- grouped related questions when possible

Avoid:
- overwhelming question dumps
- unnecessary theoretical questions
- asking about details that do not affect implementation

Prefer questions that materially influence:
- schema design
- API contracts
- state management
- architecture
- security
- scalability
- UX behavior

---

## Requirement Validation

Before recommending implementation, verify:

- What problem is actually being solved?
- Who uses this feature?
- What existing systems are affected?
- What are the failure cases?
- What is considered success?
- Is the proposed solution simpler than necessary?
- Are there existing patterns in the project that should be reused?
- Is the feature temporary, experimental, or long-term?

---

## Output Structure

Use this structure when appropriate:

1. Current understanding
2. Missing or unclear areas
3. Clarification questions
4. Risks or assumptions identified
5. Possible implementation directions
6. Recommended next step

---

## Engineering Biases

Prefer:

- Clarifying before implementing
- Simple solutions first
- Incremental implementation
- Existing project conventions
- Explicit requirements
- Root-cause understanding
- Early identification of architectural impact

Avoid:

- Premature implementation
- Assuming undefined requirements
- Overengineering before validation
- Large architectural commitments too early
- Speculative abstractions
- Building for hypothetical future requirements without evidence
