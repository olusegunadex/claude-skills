---
name: issue-triage
description: Turn a vague bug or issue report into a structured triage: classification, known facts, gaps, severity, and next step. Use before investigate or a Jira ticket. Does not find root causes.
---

# Issue Triage

## When to use
- A bug report, support message, or crash note is vague and needs structure.
- You need severity, missing information, and a recommended next step.

Not for: finding the root cause (use `investigate`) or filing the ticket (use `jira-ticket-creation`).

## Instructions
1. **Get the report text.** Use what the user pasted or linked.
2. **Classify:** bug, regression, feature request, question, performance, security, or data issue. Note platform: web, iOS, Android, API.
3. **Extract what is known:** symptoms, steps, environment, frequency, affected users, first seen, recent releases.
4. **List what is missing** and who can supply it: reproduction steps, app/OS/browser versions, device, account, logs, screenshots.
5. **Assess severity and reproducibility** using [references/triage-template.md](references/triage-template.md). Security or data-loss reports are Critical until disproved.
6. **Identify suspected areas** by searching the codebase for the relevant screen, endpoint, or recent changes. These are leads, not conclusions.
7. **Recommend the next step:** ask for more info, investigate, file a ticket, or close as duplicate/not a bug.
8. **Write the report** with the template. Keep it short.

Do not speculate about causes beyond labelled leads.

## Examples
- "App sometimes logs users out": classify as bug (auth), ask for OS/version and frequency, severity Major, next step investigate.
- "Make it faster": classify as performance, ask what is slow and by how much.

## References
- [references/triage-template.md](references/triage-template.md): report template and severity scale.
