# General Standards (web, mobile, API)

Each entry: rule, primary reason, and when it does not apply.

## Code structure
### Keep functions and components small and single-purpose
**Rule:** One reason to change per function, component, or module. Split when you need "and" to describe it.
**Primary reason:** Small units are easy to test and review.
**Does not apply when:** splitting would scatter a tightly coupled piece of logic that reads better in one place.

### Prefer the simplest design that works
**Rule:** No abstraction, config option, or interface until a second real use exists.
**Primary reason:** Speculative generality costs maintenance and hides real behaviour.
**Does not apply when:** a public API contract or an external dependency forces the seam.

### Name by intent
**Rule:** Names describe what a thing is or does in the domain, not how it is built. Booleans read as questions (`isLoading`, `hasAccess`).
**Does not apply when:** a linter already enforces the naming style (don't duplicate it here).

## TypeScript
### Strict mode, no `any` at boundaries
**Rule:** `strict: true`. Use `unknown` and narrow it. Type external data (API, storage, deep links) at the point it enters the app.
**Primary reason:** Types only help if untrusted data is checked where it arrives.
**Does not apply when:** a short-lived `any` in a test double or a documented third-party typing gap.

### Validate at the boundary
**Rule:** Parse request bodies, query params, storage reads, push payloads, and deep-link params with a schema (e.g. Zod) before using them.
**Primary reason:** The compiler cannot see runtime data.
**Check:** no `as SomeType` cast on external data.

## Errors and states
### Every async screen/endpoint handles loading, empty, error, and success
**Rule:** Build all four states. Errors show a recoverable message and never leak internals.
**Primary reason:** Users meet error and empty states more often than developers expect.

### Fail loudly in code, gently in UI
**Rule:** Do not swallow errors. Log with context, then show a user-safe message.
**Does not apply when:** the failure is expected and handled (e.g. a cancelled request).

## Dependencies
### Add a dependency only with a reason
**Rule:** Before adding a package, check size, maintenance, license, and whether the platform already provides it. Pin or lock versions.
**Primary reason:** Every dependency is a security and upgrade liability.

## Testing
### Test behaviour, not implementation
**Rule:** Cover new logic with tests that assert observable results. A bug fix starts with a failing test.
**Check:** the test fails when the behaviour breaks and passes after refactors.
**Does not apply when:** pure layout with no logic (cover it with a visual check instead).

## Git and delivery
### Small, reviewable changes
**Rule:** One purpose per PR. Include how to verify. Do not mix refactors with behaviour changes.
**Primary reason:** Large mixed changes hide bugs and slow reviews.

## Logging and privacy
### Never log secrets or personal data
**Rule:** No tokens, passwords, full emails, phone numbers, or payment data in logs, analytics events, or crash reports.
