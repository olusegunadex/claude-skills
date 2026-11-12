# Investigation Report

```
# Investigation: {short title}

## Symptom
Expected: ...
Actual: ...
Environment: {platform, version, device/browser}
Reproduction: {steps, or "not reproduced" and why}

## Evidence
| # | Observation | Source |
|---|---|---|
| 1 | {what was seen} | {log line, file:function, command} |

## Hypotheses
| Hypothesis | Test | Result |
|---|---|---|
| ... | ... | Confirmed / Ruled out |

## Root cause
{one paragraph: what is wrong, where, and why it produces the symptom}

## Fix
- Change: {what and where}
- Regression test: {name}
- Side effects / similar spots: {list}

## Validation
- [ ] Original steps no longer fail
- [ ] New test fails before, passes after
- [ ] Full suite, lint, typecheck green

## Not verified
{anything you could not confirm}
```
