---
name: refactor
description: Restructure existing code without changing behaviour, in small named steps behind a green test suite. Use for cleanup or simplification. Not for reviews or adding features.
---

# Refactor

## When to use
- The user asks to clean up, simplify, extract, rename, or restructure code while keeping behaviour the same.

Not for: new behaviour (use `tdd`), bug fixes (use `investigate`), or reviews (use `code-review`).

## Instructions
1. **Bind the target.** Name the files/functions and the goal (e.g. "split this 400-line screen"). Ask if unclear.
2. **Build the safety net.** Run the tests, lint, and typecheck; they must be green. If coverage of the target is thin, add characterization tests that pin current behaviour first. Do not refactor untested logic blind.
3. **Plan the sequence before editing.** List the refactorings in order (see [references/refactoring-moves.md](references/refactoring-moves.md)), smallest and safest first. Show the plan.
4. **Execute one named refactoring at a time.** After each: run tests. If red, undo that step; don't debug forward. Keep behaviour changes out. If you find a bug, note it and keep going.
5. **Keep the public contract.** Exports, props, API shapes, and persisted data formats stay the same unless the user agreed to change them.
6. **Finish:** full tests, lint, typecheck. Summarise what moved, what stayed, any bugs noticed, and anything you chose not to touch.

Rules:
- No mixed commits: refactor commits contain no behaviour change.
- Stop when the goal is met; don't polish adjacent code.
- Mobile/web: re-check bundle entry points, native module imports, and platform-specific files (`.ios.ts`, `.android.ts`) after moves.

## Examples
- "Break up `OrdersScreen.tsx`": extract hooks and presentational components, running tests after each extraction.
- "Rename `getData` across the app": rename with the tool, run typecheck and tests.

## References
- [references/refactoring-moves.md](references/refactoring-moves.md): common moves and when to stop.
