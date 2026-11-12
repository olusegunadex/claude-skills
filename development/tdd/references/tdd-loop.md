# The TDD Loop

## Three laws
1. Write no production code until you have a failing test.
2. Write no more of a test than is needed to fail (a compile error counts).
3. Write no more production code than is needed to pass the failing test.

## Naming behaviours (BDD-style)
Name tests for behaviour, not methods: `returns empty list when user has no orders`.
Structure: Given (setup), When (action), Then (result).

## Ordering tests
Start with the simplest case and add complexity:
1. Degenerate case (empty, null, zero)
2. One item / happy path
3. Many items
4. Boundaries (min, max, off-by-one)
5. Error and invalid input
6. Interactions (ordering, retries, concurrency)

## Ways TDD gets faked
| Symptom | Fix |
|---|---|
| Test written after the code | Delete the code, write the test, watch it fail |
| Test passed the first time | It may test nothing. Break the code on purpose and confirm it fails |
| Test fails for the wrong reason | Fix the test setup before writing code |
| Many tests written at once | Go back to one test, one pass |
| Asserting on mocks, not results | Assert on observable output |
| Code goes beyond the test | Remove the extra; add a test first |
| Skipped refactor step | Do it now while tests are green |

## Done when
All listed behaviours have passing tests, the full suite is green, lint and types pass, and the change contains no untested logic.
