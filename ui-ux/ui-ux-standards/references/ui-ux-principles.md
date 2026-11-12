# UI/UX Principles

## Core principles
1. **Clarity over cleverness.** The user always knows where they are, what they can do, and what happened.
2. **Hierarchy.** One primary action per screen; secondary actions look quieter.
3. **Consistency.** Same thing looks and behaves the same everywhere; use tokens and shared components.
4. **Feedback.** Every action shows a response within about 100 ms; long work shows progress.
5. **Forgiveness.** Undo over confirm dialogs; confirm only destructive or irreversible actions.
6. **Restraint.** Fewer elements, fewer colours, fewer fonts.

## Layout and spacing
- Use a spacing scale (e.g. multiples of 4 or 8). Group related items closer than unrelated ones.
- Left-align text. Keep line length about 45-75 characters on web.
- Align to a grid; avoid one-off offsets.

## Typography
- Limit to one or two typefaces and a small type scale.
- Body text at least 16 px on web and at least the platform default on mobile; support system text scaling.
- Use weight and size for hierarchy, not only colour.

## Colour and contrast
- Text contrast at least 4.5:1 (3:1 for large text and UI components).
- Never use colour alone to carry meaning (add an icon or text).
- Provide light and dark themes from semantic tokens (`textPrimary`, `surface`), not raw hex values.

## Targets and input
| Platform | Minimum touch target |
|---|---|
| iOS | 44 x 44 pt |
| Android | 48 x 48 dp |
| Web (touch) | 44 x 44 px |
- Leave space between targets. Place frequent actions within thumb reach on phones.
- Use the right keyboard type and autofill hints; keep labels visible (not placeholder-only).

## States
Every data-driven view defines: loading (skeleton or spinner), empty (explain and offer an action), error (what happened, how to fix, retry), offline, and success.

## Forms
- Ask only what you need. One column. Validate inline after the field is left. Preserve input on error. Explain errors specifically.

## Navigation
- Web: clear primary nav, breadcrumbs for depth, working back button and deep links.
- iOS: tab bar for top-level areas, swipe-back gesture preserved.
- Android: system back works predictably; bottom or rail navigation for top-level destinations.

## Accessibility
- Semantic structure (headings, landmarks / accessibility roles); labels on all controls.
- Visible focus; logical focus order; full keyboard operation on web.
- Support screen readers (VoiceOver, TalkBack), large text, and reduced motion.

## Content
- Plain language; buttons start with a verb; error text says what to do next.
- Avoid jargon, blame, and all caps.
