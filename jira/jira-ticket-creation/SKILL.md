---
name: jira-ticket-creation
description: Write one Jira ticket (task, story, or bug) with an Epic parent, short summary, labels, and acceptance criteria, for any project. Asks for project key and Epic if unknown. Use to write a ticket.
---

# Jira Ticket Creation

## When to use
- The user wants a task, story, or bug written for Jira, from a problem, idea, or requirement.
- The user wants to file it in Jira.

To split a large plan into many tickets, use `jira-work-items`. To structure a vague bug report first, use `issue-triage`.

Source of truth for conventions: the author's `jira-work-items` skill (Codex copy at `~/.codex/skills/jira-work-items`, copy in this repo at `jira/jira-work-items`), made configurable for any project. This skill carries a copy of the rules so it works on its own; if they differ, follow the source of truth.

## Instructions
1. **Read [references/jira-conventions.md](references/jira-conventions.md)** for the board model, summary rules, labels, and workflow.
2. **Resolve the board settings** listed there (project key, Epic, product slug, domain, platform). Use what the user already said or what Jira shows; ask only for what is missing, in one short message with likely choices. Never guess a project key or Epic. Reuse answers for later tickets in the conversation.
3. **Pick the type:** Epic, Story, Task, or Bug. Use a Task for operational work with no real user persona.
4. **Gather facts** from the user, code, or triage. For bugs: observed vs expected, steps, environment/build/platform/account, exact error text, impact, frequency. Ask only for what is missing.
5. **Search for an existing equivalent ticket** before creating a new one, if Jira access is available.
6. **Write the ticket** with the matching structure in [references/ticket-template.md](references/ticket-template.md):
   - Summary: starts with a verb, one outcome, scannable, no Epic/project prefix, key, status, or priority.
   - Parent: the product or project Epic.
   - Labels: lowercase kebab-case (product slug, domain, platform, optionally one work-class label).
   - Priority from impact and urgency. Assignee unassigned unless known or requested. Status Backlog.
   - Description in the Task, User Story, or Bug structure; acceptance criteria are testable.
7. **Do not invent facts.** Mark unknowns "Needs info" with who can answer. Keep confirmed facts separate from suspected causes. No secrets or personal data.
8. **Show the draft** and let the user edit it.
9. **Filing in Jira:** only when a Jira connector or API is available and the user clearly asks. Confirm project, type, Epic, and labels if any are unresolved. Afterwards verify the key, summary, parent, labels, and status from Jira, and report the key with a direct link. Otherwise give the text ready to paste.
10. **Run the final quality check** at the end of `references/jira-conventions.md`.

## Examples
- "Ticket for: Android paywall fails to load Google Play products": Bug, summary `Paywall fails to load Google Play products`, Epic = the product, labels `cherry-budget`, `mobile-app`, `android`, with steps, exact error, and impact.
- "Ticket to submit the closed-test release": Task, summary `Submit closed-test release for review`, checklist scope, stays In Review after submission until approval.

## References
- [references/jira-conventions.md](references/jira-conventions.md): board model, summary, labels, workflow, readiness, quality check.
- [references/ticket-template.md](references/ticket-template.md): Task, User Story, and Bug templates.
