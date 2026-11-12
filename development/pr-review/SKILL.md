---
name: pr-review
description: Review a GitHub pull request, write PR descriptions, and post review comments with gh. Use when asked to review or describe a PR (web or mobile). For local pre-PR audits use code-review.
---

# PR Review

## When to use
- The user gives a PR number/URL or says "review this PR".
- The user wants a PR description written or updated.
- The user wants review findings posted as comments.

Not for: local pre-PR checks (use `code-review`).

## Instructions

### Reviewing a PR
1. **Validate state.** `gh pr view <n> --json title,body,baseRefName,headRefName,files,author,state`. If there is no PR, say so and stop.
2. **Read the description and linked ticket** to learn the intent and acceptance criteria.
3. **Get the diff.** `gh pr diff <n>`. For large PRs, review file by file, riskiest first (auth, data, payments, native config).
4. **Review** with the checklist in [references/checklist.md](references/checklist.md). Also check: does the PR do one thing, is it a reviewable size, and is there a way to verify it?
5. **Findings** use the severity scale from the `code-review` skill (Blocker, Major, Minor, Nit). Each has file, line, problem, fix. Prefer a few high-confidence findings.
6. **Show the draft to the user before posting.** Posting comments is outward-facing and cannot be cleanly undone. Ask which findings to post.
7. **Post only after a clear yes**, as one review with inline comments where possible (`gh pr review <n> --comment --body-file`, or the API for inline comments). Use `--request-changes` or `--approve` only if the user asks. Write comments as a colleague would: kind, specific, one idea each, with a suggested change when small.
8. Report what was posted and the link.

### Writing a PR description
1. Find the repo's PR template (`.github/pull_request_template.md`); follow it if present. Otherwise use [references/pr-description-template.md](references/pr-description-template.md).
2. Base it on `git log <base>..HEAD` and the diff, not guesswork. Explain why, not just what.
3. Include how it was tested, screenshots or screen recordings for UI (web viewports; iOS and Android for mobile), and migration or release notes.
4. Show the draft. Update the PR with `gh pr edit <n> --body-file` only after the user agrees.

## Examples
- "Review PR 42": fetch, review, show 4 findings, ask what to post.
- "Write the PR description for this branch": read commits and diff, fill the template, show for approval.
- Mobile PR: confirm the description says whether a native build or only an over-the-air update is needed.

## References
- [references/checklist.md](references/checklist.md): PR-level checklist.
- [references/pr-description-template.md](references/pr-description-template.md): default description.
