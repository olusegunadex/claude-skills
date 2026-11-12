---
name: investigate
description: Find the root cause of a bug or failing behaviour using evidence, then plan a validated fix. Use for crashes, wrong results, and flaky tests in web or mobile. Not for reviews or new features.
---

# Investigate

## When to use
- Something is broken: wrong output, crash, regression, flaky test, mobile-only bug.
- The user wants the cause found and a fix planned (or made).

Not for: code review, research, or architecture assessment. For a vague report, run `issue-triage` first.

## Instructions
1. **Define the symptom.** Expected vs actual, steps to reproduce, environment (browser, OS, device, app version, build type), and when it started. Ask only for what you cannot find.
2. **Reproduce it.** Run the steps or write a failing test. If you cannot reproduce, say so and list what you need. Never guess at a fix for something you cannot reproduce.
3. **Gather evidence**, in this order: error messages and stack traces, logs/crash reports, recent changes (`git log`, `git bisect`), the code path, then config and environment. Record each observation with where you saw it.
4. **Form hypotheses and test them.** State each hypothesis and the observation that would disprove it. Test cheaply: log, breakpoint, minimal repro. Eliminate; don't collect confirmations.
5. **Name the root cause**, not the symptom. Ask "why" until you reach something you can change. Check that it explains every observation.
6. **Plan the fix.** Smallest change at the cause. List side effects and similar spots that share the cause. Include a regression test (see `tdd`).
7. **Validate.** Apply the fix, run the failing test and the full suite, and re-run the original steps. If it does not resolve the symptom, the cause was wrong; go back to step 4.
8. **Report** using [references/investigation-report.md](references/investigation-report.md).

Mobile-specific checks: Metro/bundler cache, JS vs native crash (Xcode/Logcat logs), debug vs release build differences, OS version, permissions, and offline state.
Web-specific checks: browser/console/network errors, server vs client rendering, caching, and environment variables.

## Examples
- "Orders screen crashes on Android only": get the Logcat trace, reproduce in release build, find the null native value.
- "Test fails 1 in 10 runs": look for shared state, timers, and un-awaited async work.

## References
- [references/investigation-report.md](references/investigation-report.md): report template.
