---
name: adr
description: Create or update an Architecture Decision Record capturing context, options, decision, and consequences. Use when a significant technical choice is made. Not for coding standards or feature docs.
---

# ADR

## When to use
- A significant, hard-to-reverse technical decision has been made or needs to be (framework, state library, auth approach, data model, build/release approach).
- The user asks to record why something was chosen, or to update/supersede an earlier decision.

Not for: coding standards (use `coding-standards`), feature docs, or runbooks.

## Instructions
1. **Find the decision.** What is being decided, and is it truly architectural (costly to change, affects several parts)? If not, suggest a note in the PR instead.
2. **Find existing ADRs** (`docs/adr/`, `docs/decisions/`). Reuse the folder and numbering. Check whether this supersedes or relates to an earlier one.
3. **Gather context** from the user and code: the problem, constraints (team, platform, deadlines, cost), and the options actually considered. Do not invent options.
4. **Require evidence** for the chosen option: a requirement, measurement, or constraint. Apply the evidence gate in the `coding-standards` skill's `yagni-and-evidence.md` if available. Mark unproven claims as assumptions.
5. **Write the ADR** using [references/adr-template.md](references/adr-template.md). Number it, set status (Proposed, Accepted, Superseded), and date it.
6. **Be honest about consequences:** good, bad, and what must be revisited. List the trigger that would reopen the decision.
7. **Link both ways.** Link related ADRs. If it supersedes one, update that ADR's status.
8. **Verify:** no placeholders left, each option has pros and cons, the decision is one clear sentence.

## Examples
- "Record why we chose Expo over bare React Native": context (small team, OTA updates), options, decision, consequences (custom native code needs dev builds).
- "We replaced Redux with Zustand": new ADR superseding the old one.

## References
- [references/adr-template.md](references/adr-template.md): template.
