# UI/UX Checklist

Mark each: Pass / Fail / Not checked.

## Task and clarity
- [ ] The primary action is obvious and singular.
- [ ] A new user can finish the main task without help.
- [ ] Labels and copy are plain; buttons start with verbs.
- [ ] Destructive actions are separated and confirmed or undoable.

## Layout and visual
- [ ] Consistent spacing, alignment, and type scale.
- [ ] Uses design tokens and shared components.
- [ ] Hierarchy is clear at a glance.
- [ ] No clipped, overlapping, or truncated text.

## States
- [ ] Loading state
- [ ] Empty state with a next action
- [ ] Error state with recovery
- [ ] Offline / slow network (mobile especially)
- [ ] Long text, many items, and zero items
- [ ] Disabled and pressed/hover/focus states

## Forms
- [ ] Visible labels (not placeholder-only); correct keyboard types
- [ ] Inline, specific validation; input kept on error
- [ ] Submit shows progress and prevents double submit

## Accessibility
- [ ] Text contrast at least 4.5:1; UI components at least 3:1
- [ ] Meaning not carried by colour alone
- [ ] Screen reader: roles, labels, order (VoiceOver / TalkBack / NVDA)
- [ ] Web: full keyboard use, visible focus, logical tab order
- [ ] Text scales with system settings without breaking layout
- [ ] Motion respects reduced-motion; no flashing

## Responsive and platform
- [ ] Web: works at 390, 768, 1280 px
- [ ] Mobile: safe areas, notch, keyboard avoidance, rotation if supported
- [ ] Touch targets at least 44 pt (iOS) / 48 dp (Android) / 44 px (web)
- [ ] Follows platform navigation and back behaviour
- [ ] Dark mode looks correct

## Performance feel
- [ ] Feedback within about 100 ms of an action
- [ ] No layout jump on load; images sized
- [ ] Scrolling and animation smooth

## Result
Verdict: Pass / Pass with fixes / Fail. List Blockers, Majors, Minors, and Not checked items.
