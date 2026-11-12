---
name: ui-ux-standards
description: UI/UX design standards for web and mobile apps: layout, typography, colour, states, accessibility, and platform conventions. Use when designing, building, or critiquing screens and components.
---

# UI/UX Standards

## When to use
- Designing or building a screen, flow, or component for web or mobile.
- Critiquing an existing interface or choosing between design options.

For a pass/fail audit of a finished screen, use `ui-ux-checklist`.

## Instructions
1. **Know the user and the job.** Who uses this screen, what they want to do, and on which device. Ask if unclear. Design the primary action first.
2. **Pick the platform conventions.** Web: responsive, keyboard and pointer. iOS: Human Interface Guidelines patterns (tab bar, navigation stack, sheets). Android: Material patterns. Cross-platform apps may share a design but should respect each platform's navigation and back behaviour. See [references/ui-ux-principles.md](references/ui-ux-principles.md).
3. **Use existing tokens and components** before making new ones: colours, spacing scale, type scale, shared components.
4. **Structure the screen:** one clear primary action, a visible hierarchy, related things grouped, and the minimum content needed. Remove before adding.
5. **Design every state:** loading, empty, error, offline, partial, success, and disabled. Write the real copy for each.
6. **Make it accessible by default:** contrast, labels, focus order, touch target size, dynamic text, and reduced motion.
7. **Write clear copy:** plain words, verbs on buttons ("Save changes"), specific errors that say how to recover.
8. **Motion with purpose:** short, interruptible, and never required to understand the screen. Respect the reduced-motion setting.
9. **Check the result** against `ui-ux-checklist` and say what you could not verify (real devices, screen readers).

When critiquing, name the problem, who it affects, and a specific fix. Rank by user impact.

## Examples
- "Design a settings screen": grouped lists, toggles with labels, a destructive action separated and confirmed.
- "This form feels heavy": cut fields, inline validation, one primary button, helpful errors.
- Mobile: bottom-reachable primary action, 44 pt minimum targets, keyboard doesn't cover the input.

## References
- [references/ui-ux-principles.md](references/ui-ux-principles.md): principles, sizes, and platform notes.
