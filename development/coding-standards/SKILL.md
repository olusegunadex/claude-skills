---
name: coding-standards
description: Coding standards for web and mobile (React Native/Expo) apps. Use when writing or reviewing code, or when asked to add or change a standard. New standards need real evidence first.
---

# Coding Standards

## When to use
- Writing or changing code in a web app (TypeScript, React, Next.js) or a mobile app (React Native / Expo), or in the APIs behind them.
- Reviewing code against the team's rules.
- The user asks to add, change, or remove a standard.

Not for: ADRs (use `adr`), feature docs, or runbooks. Not a replacement for linters and formatters.

## Instructions

### Mode A: Applying standards (default)
1. Identify the platform: web, mobile, shared/API, or several.
2. Read [references/general.md](references/general.md) (applies to everything) and [references/security-and-privacy.md](references/security-and-privacy.md).
3. Read the platform file: [references/web.md](references/web.md) and/or [references/mobile-react-native.md](references/mobile-react-native.md). Open only the sections that match the files you are touching.
4. Project rules win. If the repo has `CLAUDE.md`, `AGENTS.md`, or its own standards docs, follow them where they differ. [references/example-project-workably.md](references/example-project-workably.md) shows what project-specific rules look like.
5. Follow each rule's "Does not apply when" line. Do not apply a rule outside its scope.
6. If you must break a rule, say which rule and why, in the reply or PR description.
7. Do not refactor unrelated code to match a rule. Mention it instead.

### Mode B: Adding or changing a standard
1. Run the evidence gate in [references/yagni-and-evidence.md](references/yagni-and-evidence.md).
2. If a linter, formatter, or well-known language convention covers it, recommend tooling instead and ask whether to proceed.
3. If evidence is missing, record the idea as deferred with a reopen trigger. The user may override.
4. If it passes, write it with [references/standard-template.md](references/standard-template.md): one rule per entry, one ranked primary reason, "applies when", "does not apply when", a correct example, and an example to avoid.
5. Point examples at real code by file path and symbol name, never line numbers.
6. Put it in the right file: `general.md`, `web.md`, `mobile-react-native.md`, or `security-and-privacy.md`. Keep entries alphabetical within a section.
7. Re-read the new entry. It must have a "does not apply when" line and no unfilled placeholders.

## Examples
- "Add a screen that lists orders (mobile)": read general, security, and mobile; use `FlatList`, handle loading/empty/error/offline states, and add accessibility labels.
- "Add a form endpoint (web)": read general, security, and web; validate input at the boundary, return a typed error shape, and never trust client-sent ids.
- "Should we require explicit return types everywhere?": a linter covers this, so recommend an ESLint rule instead of a standard.
- "We keep shipping tokens in AsyncStorage": a recurring review finding is accepted evidence, so check `mobile-react-native.md` for the rule and tighten it if needed.

## References
- [references/general.md](references/general.md): rules for all code.
- [references/web.md](references/web.md): web and React/Next.js rules.
- [references/mobile-react-native.md](references/mobile-react-native.md): React Native / Expo rules.
- [references/security-and-privacy.md](references/security-and-privacy.md): security rules for both platforms.
- [references/yagni-and-evidence.md](references/yagni-and-evidence.md): when a standard is justified.
- [references/standard-template.md](references/standard-template.md): format for a new entry.
- [references/example-project-workably.md](references/example-project-workably.md): example of project-specific rules.
