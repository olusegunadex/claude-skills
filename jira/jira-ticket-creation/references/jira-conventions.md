# Jira Conventions (copy of `jira-work-items`)

Source of truth: the `jira-work-items` skill. Keep this file in sync with it. Project key and Epic names are examples, not fixed values.

## Board settings (resolve before drafting)
Take from the user's message, earlier answers, or Jira. Ask only for what is unknown, in one short message with likely choices. Never guess.
| Setting | Example |
|---|---|
| Project key | `JSE` |
| Epic (existing or proposed new) | `Cherry Budget` |
| Product slug (kebab-case of Epic) | `cherry-budget` |
| Domain label | `mobile-app` |
| Platform (if specific) | `android`, `ios`, `web` |
| Workflow statuses (assume the five below unless the board differs) | |
| Priority scheme (the project's own) | |

## Shared-board model
- One shared Jira project (the resolved key) holds the board.
- One Epic per product or project (e.g. `Cherry Budget`); propose a new Epic and confirm before creating one.
- Every task, story, and bug is a child of the correct Epic.
- Do not repeat the Epic or project name in a child summary.
- Search for an existing equivalent item before creating a duplicate.

## Work types
- **Epic**: a product, project, or substantial outcome containing multiple items.
- **Story**: user-visible behavior or value that can be independently accepted.
- **Task**: technical, operational, administrative, release, research, or configuration work.
- **Bug**: observed behavior that differs from expected behavior.

Don't force operational work into user-story language.

## Summary
- Starts with a verb when practical; one outcome; short enough for a Kanban card.
- Omit Epic name, project prefix, key, status, and priority.
- Avoid vague summaries (`Fix Android`, `Store work`, `Investigate issue`).

## Fields
1. Parent/Epic: always set.
2. Labels (lowercase kebab-case): product slug; domain (e.g. `mobile-app`); platform if applicable (`android`, `ios`, `web`); optionally one work-class label (`release-automation`, `subscriptions`, `store-release`). No redundant or speculative labels.
3. Priority from impact and urgency; never in the summary.
4. Assignee: unassigned unless ownership is known or requested.
5. Links: blocking, duplicate, or related items; don't copy their content.

## Workflow
- **Backlog**: default for new work and anything not ready.
- **To Do**: refined, unblocked, ready to start.
- **In Progress**: actively worked on.
- **In Review**: awaiting code review, stakeholder approval, store review, or external verification.
- **Done**: acceptance criteria verified, no required follow-up remains.

Submitted for external review is not Done: record the evidence and keep it In Review until approval or the agreed completion condition.

## Ready for To Do
- Outcome unambiguous; Epic and labels set; acceptance criteria testable; dependencies visible; required decisions made.

## Ready for Done
- Every acceptance criterion verified; required review/approval complete; evidence, links, or release identifiers recorded; follow-up captured separately; status matches the external system of record.

## Final quality check
- [ ] correct work type
- [ ] concise summary without project prefix
- [ ] correct Epic
- [ ] required labels
- [ ] appropriate priority and status
- [ ] actionable scope or user story
- [ ] testable acceptance criteria
- [ ] dependencies and evidence captured
