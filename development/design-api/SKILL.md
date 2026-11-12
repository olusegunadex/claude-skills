---
name: design-api
description: Design an API contract (HTTP endpoint, function, component props, payload) with options, questions, and validation before coding. Use when shaping an interface. Changes no code.
---

# Design API

## When to use
- Before building a new endpoint, SDK function, hook, module, or component props.
- A change would alter an existing interface and callers need to be considered.

Not for: implementing it (use `tdd`) or recording the decision (use `adr`).

## Instructions
1. **State the goal and the callers.** Who calls this (web client, mobile app, another service, a teammate), what they need, and how often.
2. **Find the starting point.** Search for existing similar interfaces and conventions (naming, error shape, pagination, auth). Reuse before inventing.
3. **Propose 2-3 options** with a short trade-off table: simplicity, flexibility, client effort, and compatibility. Recommend one. Show the user and let them pick.
4. **Ask the open questions**, one at a time, only those that change the design: required vs optional, limits, errors, auth, idempotency, versioning.
5. **Write the contract** using [references/api-design-template.md](references/api-design-template.md): shape, types, errors, examples.
6. **Check mobile and web needs:**
   - Mobile: old app versions stay in the wild, so changes must be backward compatible or versioned. Payloads should be small, paginated, and tolerant of offline retries (idempotency keys).
   - Web: caching, CORS, and cookie vs token auth.
7. **Validate adversarially.** Try to break it: bad input, a missing field, a huge list, a retried request, an old client, an unauthorised caller. Update the design.
8. **Present the design** and list decisions still open. Do not write code.

## Examples
- "Design the orders list endpoint": cursor pagination, filters, error shape, and a versioning note for old app builds.
- "Props for a `Card` component": options (compound components vs props), recommended, with usage examples.

## References
- [references/api-design-template.md](references/api-design-template.md): design document template.
