---
name: code-review
description: Review local code changes (diff, branch, or files) for bugs, security, tests, and maintainability on web and mobile projects. Use for audits before a PR. Not for posting to GitHub; use pr-review.
---

# Code Review

## When to use
- The user asks to review, audit, or check local changes, a branch, or specific files before opening a PR.
- You finished a change and want a self-review.

Not for: posting comments on a GitHub PR (use `pr-review`), architecture assessments, or writing the fix.

## Instructions
1. **Identify the changes.** Use the user's target. Otherwise review the current diff against the base branch (`git diff <base>...HEAD`) plus uncommitted changes. State what you are reviewing.
2. **Understand intent.** Read the branch name, commit messages, ticket or PR text. If intent is unclear, ask one question.
3. **Run the project's checks if they exist** (lint, typecheck, tests). Report failures first. Do not claim a pass you did not run.
4. **Review in passes**, using [references/checklist.md](references/checklist.md):
   1. Correctness and edge cases
   2. Security and privacy
   3. Tests
   4. Maintainability and simplicity
   5. Platform specifics (web and/or mobile)
5. **Check what the change leaves out**: missing tests, error states, migrations, docs, accessibility.
6. **Filter before reporting.** Drop a finding if it is style a linter would catch, unreachable in practice, or a preference with no consequence. Keep a finding only when you can point to a file/symbol and a concrete failure.
7. **Rank findings** with the severity scale in [references/severity-and-report.md](references/severity-and-report.md) and write the report in that format.
8. **Verify the report**: each finding names a location, says what breaks, and says how to fix it. Remove duplicates. Say what you did not review.

Rules:
- Review the change, not the whole codebase. Mention unrelated problems in one "Out of scope" line.
- Prefer few, high-confidence findings over a long list.
- Never edit code during a review unless the user asks for fixes.
- Flag over-engineering (unused abstractions, speculative options) as a finding.

## Examples
- "Review my changes": diff against base, run lint/tests, report 3 findings ranked by severity.
- "Review `src/payments/`": review those files in full, since there is no diff.
- Mobile change: also check list rendering, permissions, offline behaviour, and secure storage.

## References
- [references/checklist.md](references/checklist.md): what to check, by area.
- [references/severity-and-report.md](references/severity-and-report.md): severity scale and report template.
