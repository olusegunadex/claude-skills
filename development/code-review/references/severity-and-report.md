# Severity Scale and Report Template

## Severity
| Level | Meaning | Examples |
|---|---|---|
| Blocker | Must fix before merge: data loss, security hole, crash, broken core flow | Missing auth check, token logged, crash on empty list |
| Major | Likely bug or serious maintainability cost | Unhandled error path, missing test for risky logic, N+1 query |
| Minor | Real but low impact | Confusing name, small duplication |
| Nit | Optional taste; max 2 per review, or omit | Wording of a comment |

## Report template
```
# Code Review: {branch or scope}

**Reviewed:** {what, e.g. 12 files vs main}
**Checks run:** {lint / typecheck / tests: pass or fail; or "not run"}
**Verdict:** {Ready / Ready after minor fixes / Needs changes}

## Findings
### 1. [Blocker] {short title}
**Where:** `path/to/file.ts` -> `functionName`
**Problem:** {what is wrong and the concrete failure}
**Fix:** {specific change}

### 2. [Major] ...

## What looks good
- {1-3 specific things}

## Not reviewed / out of scope
- {areas skipped, unrelated issues noticed}
```

## Rules
- Lead with the verdict and the most severe finding.
- Each finding has a location, a concrete consequence, and a fix.
- Explain in plain language for the reader who must act on it.
- If there are no findings, say so and list what was checked.
