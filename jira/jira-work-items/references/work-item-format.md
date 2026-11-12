# Plan Breakdown Format

Use when a plan or feature is split into several work items. Each item still follows the rules in `SKILL.md` (Epic parent, summary without project prefix, kebab-case labels, Backlog status, Task/Story/Bug structure).

## File layout (`work-items.md`)
```
# Work Items: {feature}

**Epic:** {product or project Epic}
**Platforms:** {web | iOS | Android | API}

## Overview
| ID | Type | Summary | Labels | Size | Depends on |
|---|---|---|---|---|---|
| WI-1 | Task | Add notification token endpoint | cherry-budget, mobile-app | S | none |
| WI-2 | Story | Receive spending reminders | cherry-budget, mobile-app, android | M | WI-1 |

## WI-1: {summary}
**Type:** Task | Story | Bug
**Labels:** ...
**Priority:** ...
{description in the Task / User Story / Bug structure}
**Depends on:** none
```

## Rules
- IDs are symbolic (WI-1). Jira keys replace them after creation.
- Summaries start with a verb and never repeat the Epic name.
- Sizes: XS (under half a day), S (1 day), M (2-3 days), L (about a week; split if possible).
- A dependency means "cannot start or finish before"; link it in Jira instead of copying content.
