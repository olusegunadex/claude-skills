# Ticket Templates

Fields for every ticket:
```
Project: {key, asked or looked up}
Type: Epic | Story | Task | Bug
Summary: {verb + one outcome; no Epic/project prefix}
Parent (Epic): {asked or looked up; never guessed}
Labels: {product-slug, domain, platform?, work-class?}
Priority: {from impact and urgency}
Assignee: unassigned (unless known)
Status: Backlog
Links: {blocks / duplicates / relates to}
```

## Task
```markdown
## Outcome
State the result this task must produce.

## Current state
Describe the relevant existing state, error, or gap.

## Scope / checklist
- Concrete action
- Concrete action

## Acceptance criteria
- Observable, testable completion condition
- Required evidence or verification

## Dependencies / notes
List blockers, related work items, deadlines, or authoritative links.
```

## User Story
Use only when a real user goal exists.
```markdown
## User story
As a <specific user>, I want <capability> so that <benefit>.

## Context
Explain the problem and important constraints.

## Acceptance criteria
- Given <starting state>, when <action>, then <observable result>.
- Given <edge case>, when <action>, then <expected handling>.

## Notes
Add dependencies, analytics, design, or policy links when relevant.
```

## Bug
```markdown
## Observed behavior
## Expected behavior
## Steps to reproduce
1.
2.
## Environment
Build, platform (web / iOS / Android), OS or browser version, device, account context.
## Evidence
Exact error text, logs, screenshots or recordings.
## Impact and frequency
## Suspected cause (unconfirmed)
Keep separate from confirmed facts.
## Acceptance criteria
- Regression is fixed and the steps above no longer reproduce it.
- Verified on {platforms}.
```

## Quality bar
- Use only the sections that add information.
- Exact error messages preserved; no secrets or customer personal data.
- Implementation suggestions stay out of acceptance criteria unless the implementation is the requirement.
