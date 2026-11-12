# Refactoring Moves

## Common moves
| Smell | Move |
|---|---|
| Long function | Extract function |
| Unclear name | Rename |
| Same code in several places | Extract shared helper (after the third repeat) |
| Component does fetching, logic, and layout | Extract hook for logic; split presentational component |
| Deep nesting | Guard clauses / early return |
| Magic values | Named constant |
| Flag arguments | Split into two functions |
| Large props list | Group into an object or compose children |
| Dead code | Delete it |
| Wide type unions with switch spread everywhere | Centralise in one place |

## Safety rules
- Green before, green after, every step.
- One move per step; commit after a green step if the user wants history.
- Never change behaviour and structure in the same step.
- Prefer tool-assisted renames and moves over hand edits.

## Stop when
- The stated goal is met.
- Further changes would need new behaviour or API changes (propose them separately).
- Tests are too thin to protect the next step (add tests first).
