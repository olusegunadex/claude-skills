# Code Review Checklist

## Correctness
- [ ] Does the code do what the ticket/PR says, including the unhappy paths?
- [ ] Null/undefined, empty list, zero, very large input, duplicate submit, race conditions?
- [ ] Async code: awaited, errors caught, requests cancelled when no longer needed?
- [ ] Dates/time zones, currency, and locale handled?
- [ ] State updates safe under re-render and concurrent events?

## Security and privacy
- [ ] Input validated on the server; output encoded?
- [ ] Authorisation checked for the specific record, not just "logged in"?
- [ ] No secrets, tokens, or personal data in code, logs, or analytics?
- [ ] New dependency justified, maintained, and licensed?

## Tests
- [ ] New behaviour has tests that would fail if it broke?
- [ ] Bug fix has a regression test?
- [ ] Tests assert behaviour, not implementation details?
- [ ] No flaky timing, shared state, or network calls?

## Maintainability
- [ ] Names reveal intent; functions are small?
- [ ] No dead code, commented-out code, or leftover debug output?
- [ ] No abstraction, option, or flag without a current use? (YAGNI)
- [ ] Duplication that should reuse existing helpers?
- [ ] Comments explain why, not what?

## Web
- [ ] Server vs client components chosen deliberately?
- [ ] Accessible: labels, keyboard, focus, contrast?
- [ ] Loading, empty, error states? Layout works at phone and desktop widths?
- [ ] No layout shift or oversized images/bundles?

## Mobile (React Native / Expo)
- [ ] Long lists virtualised; rows cheap to render?
- [ ] Tested on iOS and Android; safe areas and keyboard handled?
- [ ] Offline/slow network behaviour defined?
- [ ] Tokens in secure storage; no secrets in `EXPO_PUBLIC_` values?
- [ ] Permissions requested at point of use with a reason?
- [ ] Deep-link/push params validated?
- [ ] Accessible: roles, labels, touch targets, dynamic type?
- [ ] Does it need a native build, or can it ship over the air?

## Data and API
- [ ] Schema/migration is backward compatible and reversible?
- [ ] Response shape and error format consistent?
- [ ] Indexes/pagination for new queries?
