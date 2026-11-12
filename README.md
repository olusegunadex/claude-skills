# Claude Skills

A set of [Claude skills](https://support.claude.com/en/articles/12512180-using-skills-in-claude) for web and mobile (React Native / Expo) development: coding standards, code and PR review, TDD, bug investigation, UI/UX, and Jira work items.

Each skill is a self-contained folder with a `SKILL.md` and optional `references/`. The category folders (`development/`, `ui-ux/`, `jira/`) are only for organisation.

## Skills

| Skill | Category | Purpose |
|-------|----------|---------|
| [`coding-standards`](development/coding-standards) | development | Web, mobile, and security standards; evidence gate for new rules |
| [`code-review`](development/code-review) | development | Review local changes before a PR |
| [`pr-review`](development/pr-review) | development | Review PRs, write descriptions, post comments with `gh` |
| [`tdd`](development/tdd) | development | Red-green-refactor with an observed failure |
| [`refactor`](development/refactor) | development | Behaviour-preserving restructuring behind green tests |
| [`investigate`](development/investigate) | development | Evidence-based root-cause analysis for bugs |
| [`issue-triage`](development/issue-triage) | development | Structure a vague bug report |
| [`test-planning`](development/test-planning) | development | Automated and manual test plans with a platform matrix |
| [`adr`](development/adr) | development | Architecture decision records |
| [`design-api`](development/design-api) | development | Design an API contract before coding |
| [`ui-ux-standards`](ui-ux/ui-ux-standards) | ui-ux | UI/UX design standards for web and mobile |
| [`ui-ux-checklist`](ui-ux/ui-ux-checklist) | ui-ux | Pass/fail UI/UX and accessibility audit |
| [`jira-work-items`](jira/jira-work-items) | jira | Create and refine Jira work items; split plans into items |
| [`jira-ticket-creation`](jira/jira-ticket-creation) | jira | Write bug, story, and task tickets |

The Jira skills ask for your project key and Epic when they are not known, so any project can use them.

## Install

### Claude (claude.ai and desktop app)
Zip the individual skill folder (e.g. `code-review.zip` containing `code-review/`) and upload it in Claude under **Customize > Skills**.

```bash
cd development && zip -r code-review.zip code-review
```

### Claude Code
Copy or symlink a skill folder into `~/.claude/skills/` (personal) or `.claude/skills/` (per project):

```bash
ln -s "$(pwd)/development/code-review" ~/.claude/skills/code-review
```

## Conventions
- Folder name is kebab-case and matches the `name` in `SKILL.md` exactly.
- The file is named `SKILL.md` (case-sensitive); no `README.md` inside a skill folder.
- `description` is 200 characters or fewer.
- Each skill is self-contained so it can be packaged alone.

## Credits
Several skills (`coding-standards`' evidence gate, `tdd`, `refactor`, `investigate`, `issue-triage`, `test-planning`, `adr`, `design-api`) are inspired by [testdouble/han](https://github.com/testdouble/han) and rewritten to be self-contained and platform-neutral.

`coding-standards/references/example-project-workably.md` shows how a project-specific override looks; project rules win over the generic ones.
