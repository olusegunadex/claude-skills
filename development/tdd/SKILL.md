---
name: tdd
description: Build or fix code with test-driven development: write a failing test, make it pass, refactor. Use when asked for TDD, or to implement logic or a bug fix with tests first, on web or mobile.
---

# TDD

## When to use
- The user asks for TDD or "tests first".
- Implementing new logic, or fixing a bug, where behaviour can be asserted.

Not for: restructuring without behaviour change (use `refactor`), or pure layout work with no logic.

## Instructions
1. **Confirm scope and the test setup.** Find the test runner and command (Jest, Vitest, React Native Testing Library, Playwright, etc.) and run the suite once to get a green baseline. If the baseline is red, tell the user and stop.
2. **Write a behaviour list** before any code, in plain language: "returns an empty list when there are no orders", "rejects a title over 200 characters". Order it simplest to hardest. Show it to the user. See [references/tdd-loop.md](references/tdd-loop.md).
3. **Loop, one behaviour at a time:**
   1. **Red:** write one test. Run it. It must fail, and for the right reason (the missing behaviour, not a typo or import error). Show the failure.
   2. **Green:** write the least code that passes. No extra features.
   3. **Refactor:** with tests green, clean up names and duplication in code and tests. Run the tests again. Do not skip this step.
4. **Never weaken a test to pass it.** If a test is wrong, say why and fix the test in its own step.
5. **Mock only at the edges** (network, storage, time, native modules). Don't mock the code under test.
6. **Finish:** run the full suite, lint, and typecheck. Summarise behaviours added, tests added, and anything not covered.

Bug fixes: first write a test that reproduces the bug and watch it fail. Then fix.

Web and mobile notes:
- UI: test what the user sees and does (roles, text, press events), not component internals.
- React Native: mock native modules at the boundary; cover platform differences you rely on.

## Examples
- "TDD a `formatPrice` helper": list behaviours (rounding, currency, negatives), test one at a time.
- "Fix: cart total wrong with discount": failing test with the discount case first, then the fix.

## References
- [references/tdd-loop.md](references/tdd-loop.md): the loop, test ordering, and ways TDD gets faked.
