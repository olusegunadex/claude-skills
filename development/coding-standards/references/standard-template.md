# Standard Template

Copy this for each new rule in `workably-standards.md`.

```
### {Short rule name}
**Rule:** {one sentence, testable}
**Primary reason:** {the one main benefit}
*Secondary:* {optional, clearly lower priority}
**Applies when:** {decision question, e.g. "the route reads or writes tenant data"}
**Does not apply when:** {cases where the simpler alternative is correct}
**Check:** {command, query, or test to confirm, if the rule is judgment-based}

Correct:
{short code example, with a comment matching the primary reason}

Avoid:
{short code example}

Found in: {path} -> {function or symbol}
```

## Writing rules
- One rule per entry. Exceptions go in "Does not apply when", not in a footnote elsewhere.
- Rank reasons. Do not list benefits side by side.
- Code comments must cite the primary reason, not a secondary one.
- Examples use real files by path and symbol, never line numbers.
- If no real example exists yet, label it "Proposed pattern".
