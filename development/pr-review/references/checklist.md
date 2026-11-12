# PR Review Checklist

Use together with the code-level checklist in the `code-review` skill.

## The PR itself
- [ ] Title says what changes; description says why.
- [ ] Linked ticket exists and the PR meets its acceptance criteria.
- [ ] One purpose; no unrelated refactors mixed in.
- [ ] Size is reviewable. If it is large, can it be split?
- [ ] CI passes (lint, types, tests, build).
- [ ] How to verify is stated.

## Risk
- [ ] Touches auth, payments, data migrations, or permissions? Review those first.
- [ ] Breaking change to an API, schema, or stored data? Is there a migration and a rollback?
- [ ] Feature flag or staged rollout for risky changes?

## Evidence
- [ ] Tests added or changed for new behaviour.
- [ ] UI changes have screenshots (web: desktop and phone widths; mobile: iOS and Android).
- [ ] Performance-sensitive changes have a measurement.

## Mobile release
- [ ] Native dependency, permission, or config change means a new store build (not over-the-air).
- [ ] Privacy labels and permission strings updated.
- [ ] Minimum OS version and app version considered.

## Comment quality (when posting)
- [ ] Specific: file, line, and consequence.
- [ ] One idea per comment; suggested change when small.
- [ ] Question when unsure, statement when certain.
- [ ] Blockers separated from nits.
