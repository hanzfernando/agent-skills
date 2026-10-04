---
name: ui-design
description: Design, implement, refine, and review visible UI layout, hierarchy, typography, accessibility, responsiveness, forms, navigation, and dashboard readability. Use when screen presentation or interaction needs design decisions; not component ownership refactors or backend changes without UI impact.
---

# UI Design

## Priorities

- Make the primary task/action obvious; inspect the screen and design system first and preserve the requested visual direction.
- Use a consistent spacing rhythm, type scale, component language, and readable line lengths.
- Maintain sufficient contrast, keyboard access, visible focus, semantic structure, labels, and non-color cues.
- Design responsive behavior intentionally rather than merely shrinking desktop layouts.
- Cover empty, loading, error, disabled, success, and long-content states without disruptive layout shifts.
- Default to calm, professional styling; adapt color, depth, and motion to product/user intent while preserving task clarity.

Avoid competing accents, purposeless oversized cards, low-contrast text, unclear button hierarchy, cramped ungrouped data, and animation that harms usability.

## Dashboard checks

- Make the most decision-relevant metric or task dominant; show units and time context.
- Keep chart labels and legends readable and avoid encodings users cannot interpret quickly.
- Group dense data by task and make filters, active state, and reset behavior clear.
- Explain missing data and keep loading or real-time updates spatially stable.

## Review output

Give concrete, implementable changes rather than labels such as “make it modern.” Locate findings by screen/component with user impact and correction. Prioritize task clarity, accessibility, hierarchy/layout, responsive states, then polish. Verify affected layouts/states at representative widths and with keyboard interaction; disclose unavailable visual checks. Include a revised component example only when it communicates the fix better than prose.
