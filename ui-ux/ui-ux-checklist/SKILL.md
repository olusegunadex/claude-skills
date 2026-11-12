---
name: ui-ux-checklist
description: Audit a web or mobile screen or flow against a pass/fail UI/UX and accessibility checklist and report issues by severity. Use before release or PR on UI changes.
---

# UI/UX Checklist

## When to use
- A UI change is ready and needs a design and accessibility audit.
- The user asks "does this look right?", "is this accessible?", or for a UX review of a screen.

To design something new, use `ui-ux-standards`.

## Instructions
1. **Identify the target:** screens, flows, and platforms (web viewports, iOS, Android). If the app can be run, run it. For web, use the browser; for mobile, use the simulator or emulator and take screenshots. Don't judge from code alone when you can see it.
2. **Walk the main flow, then edge flows:** empty, error, loading, offline, long text, small screen, large text, dark mode.
3. **Go through [references/checklist.md](references/checklist.md)** section by section. Mark each item Pass, Fail, or Not checked. Do not mark Pass for something you did not test.
4. **Record each failure** with where it is, what is wrong, who it affects, and a fix. Use the severity scale: Blocker (stops a task or excludes users), Major, Minor.
5. **Report** a short summary first (verdict, counts), then failures ranked by severity, then the items you could not check and why (for example, no real device or screen reader).
6. **Do not fix issues** unless asked.

## Examples
- "Check the new login screen on web and iOS": run both, test with keyboard and VoiceOver if possible, report 2 majors and 3 minors.
- "Quick pass on this PR's UI": review screenshots and code, mark limits clearly.

## References
- [references/checklist.md](references/checklist.md): the checklist.
