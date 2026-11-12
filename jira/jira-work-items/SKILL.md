---
name: jira-work-items
description: Create, refine, or review Jira Epics, stories, tasks, and bugs with a shared-board model: Epic parent, short summaries, labels, priority, workflow status, acceptance criteria. Any project.
---

# Jira Work Items

Create work items that are concise on the board, actionable without extra explanation, and organized by Epic.

Source of truth: the author's Codex skill `jira-work-items` (`~/.codex/skills/jira-work-items`). If the two ever differ, follow the Codex skill and update this one. The one deliberate difference: the Codex skill hard-codes the Jase Digital board (project `JSE`); this version asks for board settings so any project can use it.

## When to use
- Drafting Jira work items or converting requirements into tickets.
- Cleaning ticket titles, applying labels and priorities, choosing an Epic or workflow status.
- Defining acceptance criteria.
- Checking whether a Jira item is ready or done.
- Splitting a plan into work items (see "Splitting a plan" below).

## Instructions

### Resolve the board settings first
Before drafting, you need these. Take them from the user's message, an earlier answer in this conversation, or Jira itself (look up the project and its Epics through a connector when one is available). Ask only for what is still unknown, in one short message, and offer likely choices:

| Setting | Ask | Example |
|---|---|---|
| Project key | "Which Jira project key should these go in?" | `JSE` |
| Epic | "Which Epic does this belong to? (existing one, or should I propose a new Epic?)" | `Cherry Budget` |
| Product slug | Derive from the Epic name in kebab-case; confirm if unsure | `cherry-budget` |
| Domain label | "What domain label fits (e.g. mobile-app, web-app, api)?" | `mobile-app` |
| Platform | Only if the work targets one | `android`, `ios`, `web` |
| Workflow statuses | Assume Backlog / To Do / In Progress / In Review / Done; ask if the board differs | |
| Priority scheme | Use the project's own; ask if unknown | |

Never guess a project key or Epic name. If the user answers once, reuse it for the rest of the conversation. If no Epic exists, propose one and confirm before creating it.

### Apply the shared-board model
- Use the resolved Jira project key for all work on the shared board.
- Represent each product or project with an Epic, such as `Cherry Budget`.
- Make every task, story, and bug a child of the correct Epic.
- Do not repeat the Epic or project name in a child item's summary.
- Use the summary for the work itself: `Configure Google Play production release`, not `Cherry Budget: Configure Google Play production release`.
- Search for an existing equivalent item before creating a duplicate.

### Choose the work type
- **Epic**: a product, project, or substantial outcome containing multiple work items.
- **Story**: user-visible behavior or value that can be independently accepted.
- **Task**: technical, operational, administrative, release, research, or configuration work.
- **Bug**: observed behavior that differs from the expected behavior.

Do not force operational work into user-story language. Use a Task when there is no meaningful end-user persona or behavior.

### Write the summary
- Start with a clear verb when practical.
- Describe one outcome, not a collection of unrelated activities.
- Keep it short enough to scan on a Kanban card.
- Omit the Epic name, project prefix, ticket key, status, and priority.
- Avoid vague summaries such as `Fix Android`, `Store work`, or `Investigate issue`.

### Add organization fields
Set these fields when the Jira surface supports them:
1. **Parent/Epic**: always select the product or project Epic.
2. **Labels**:
   - product slug (kebab-case of the Epic name), such as `cherry-budget`
   - domain, such as `mobile-app`
   - platform when applicable: `android`, `ios`, or `web`
   - one useful work-class label only when it improves filtering, such as `release-automation`, `subscriptions`, or `store-release`
3. **Priority**: select it from impact and urgency; do not encode it in the summary.
4. **Assignee**: leave unassigned unless ownership is known or the user asks to assign it.
5. **Links/dependencies**: link blocking, duplicate, or related items rather than duplicating their content.

Use lowercase kebab-case labels. Do not add redundant or speculative labels.

### Use the workflow consistently
- **Backlog**: default for newly created work and anything not ready to be picked up.
- **To Do**: refined, unblocked, and ready to start.
- **In Progress**: actively being worked on.
- **In Review**: awaiting code review, stakeholder approval, store review, or external verification.
- **Done**: acceptance criteria are verified and no required follow-up remains.

Do not mark an externally reviewed item Done merely because it was submitted. Record the submission evidence and keep it In Review until approval or the explicitly agreed completion condition is met.

### Structure the description
Use the Task, User Story, or Bug structure in [references/work-item-structures.md](references/work-item-structures.md). Use only the sections that add information.

- Prefer checklist items for multi-step operational work.
- Keep implementation suggestions out of acceptance criteria unless the implementation itself is a requirement.
- Use a user story only when a real user goal exists, with a specific persona rather than `As a user`. Include unhappy paths and permissions when they materially affect acceptance.
- For bugs, preserve exact error messages and separate confirmed facts from suspected causes.

### Check readiness and completion
A work item is ready for **To Do** when:
- the outcome is unambiguous
- the parent Epic and labels are set
- acceptance criteria are testable
- dependencies and blockers are visible
- required product or technical decisions have been made

A work item is ready for **Done** when:
- every acceptance criterion has been verified
- required review or external approval has completed
- evidence, links, or release identifiers are recorded
- remaining follow-up work is captured separately
- the status accurately reflects the external system of record

### Create or update Jira safely
- Prefer an available Jira connector or API; use a signed-in browser only when no suitable connector exists.
- Before bulk creation, show the proposed hierarchy, summaries, and labels when the request leaves material choices unresolved.
- Preserve existing descriptions and comments unless the user explicitly asks to replace them.
- After mutations, verify the item key, summary, parent, labels, and status from Jira.
- Report created or updated keys with direct links.
- Do not create or change Jira content without a clear request from the user.

### Splitting a plan
When the input is a plan or feature rather than a single item:
1. Slice vertically: each item delivers something that works end to end and can ship alone.
2. Size each to a few days or less; split larger, merge trivial.
3. Keep web, iOS, and Android items separate when they can ship independently; shared API work comes first as a dependency.
4. Apply every rule above to each item (Epic parent, summary without prefix, labels, Backlog status).
5. Print the breakdown using [references/work-item-format.md](references/work-item-format.md) and confirm before creating anything.

### Final quality check
Before handing off, confirm:
- [ ] correct work type
- [ ] concise summary without project prefix
- [ ] correct Epic
- [ ] required labels
- [ ] appropriate priority and status
- [ ] actionable scope or user story
- [ ] testable acceptance criteria
- [ ] dependencies and evidence captured

## Examples
- Task: `Submit closed-test release for review`
- Story: `Review monthly spending by category`
- Bug: `Paywall fails to load Google Play products`
- Not acceptable: `Cherry Budget: Configure Google Play production release` (repeats the Epic name).

## References
- [references/work-item-structures.md](references/work-item-structures.md): Task, User Story, and Bug description structures.
- [references/work-item-format.md](references/work-item-format.md): format for a plan broken into work items.
