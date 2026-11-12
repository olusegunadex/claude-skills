---
name: test-planning
description: Write an automated or manual test plan for a feature or change, covering gaps, edge cases, and web and mobile specifics (devices, OS, offline). Does not write the tests themselves.
---

# Test Planning

## When to use
- The user wants a test plan, QA checklist, or coverage-gap analysis for a feature or change.
- Before release, to decide what to automate and what a person must check by hand.

Not for: writing the tests (use `tdd`).

## Instructions
1. **Set scope.** Feature, PR, or screen. Read the code and the ticket's acceptance criteria. Ask only if scope is unclear.
2. **Choose the mode:**
   - *Automated:* find coverage gaps and edge cases that tests should pin down.
   - *Manual:* write steps a person can run, in plain language.
   - If unspecified, produce both, automated first.
3. **List behaviours and risks** from the code and criteria: happy paths, error paths, boundaries, permissions, state, and integrations. Rank by risk (money, data, security, core flow first).
4. **Automated plan:** for each behaviour pick the lowest effective level: unit, component, integration/API, then end-to-end. Note what is already covered (search existing tests) and what is missing.
5. **Manual plan:** group into named tests. Each has preconditions, numbered steps, and an expected result a person can verify. See [references/test-plan-template.md](references/test-plan-template.md).
6. **Add the platform matrix** where it applies:
   - Web: browsers, viewport widths, keyboard-only, screen reader, slow network.
   - Mobile: iOS and Android, min and latest OS, small and large screens, offline and flaky network, permissions denied, backgrounding and resume, interruptions (call, notification), dark mode and large text, fresh install and upgrade.
7. **Challenge the plan.** Ask what a hostile or careless user could do, and what would break silently. Add missing cases.
8. **Write the plan** with the template. State what is out of scope.

## Examples
- "Test plan for the checkout flow": automated unit tests for totals, API tests for payment errors, one e2e happy path, manual run on two devices.
- "Manual QA for push notifications": permission granted, denied, app killed, app in background, tap deep link.

## References
- [references/test-plan-template.md](references/test-plan-template.md): plan structure and platform matrix.
