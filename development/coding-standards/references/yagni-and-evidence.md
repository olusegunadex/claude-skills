# YAGNI and Evidence Gate

Adapted from the ideas in testdouble/han (`yagni-rule.md`, `evidence-rule.md`). Use it before writing any new standard.

## Gate 1: Evidence test
A standard is justified only with at least one of:
1. A user-described need ("I keep having to remind people about X").
2. A recurring code-review finding or bug the rule would have prevented (cite at least two).
3. An existing production path that would break without the convention.
4. A regulation or compliance rule the project actually falls under.
5. A documented incident, fired alert, customer report, or measured metric.

Also required: the pattern is used in the codebase today, with at least three examples, and inconsistency between them is causing friction.

## Gate 2: Simpler-version test
Prefer the simplest rule that satisfies the same evidence. A one-line rule beats a section. A lint rule beats a document.

## Auto-flagged as "not yet" (YAGNI candidates)
- "We might need this later" or "best practice says we should".
- "At scale" with no measurement.
- A rule for symmetry with another area ("we have one for backend, so frontend needs one").
- A rule about a pattern the project does not use yet.
- Anything a linter or formatter can enforce (naming, indentation, import order, semicolons).

## Evidence quality
- Evidence in our own codebase is the strongest for what we do today.
- A claim from the web or an article needs a second independent source before it can justify a standard. Mark single-source claims as such.
- Evidence from the person asking is valid but note who benefits.
- No evidence: say so, defer the decision, and write a reopen trigger.

## Deferred format
```
### {rule idea}
**Why deferred:** {missing evidence}
**Reopen when:** {concrete trigger, e.g. third instance lands, first incident}
**Source:** {who raised it}
```
Never drop an item silently. The user can always override with a recorded reason.
