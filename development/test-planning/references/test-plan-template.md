# Test Plan Template

```
# Test Plan: {feature or change}

**Scope:** {in}  **Out of scope:** {out}
**Risk areas:** {ranked list}

## Automated tests
| Behaviour | Level (unit/component/API/e2e) | Exists? | Priority |
|---|---|---|---|
| ... | ... | yes/no | High/Med/Low |

### Gaps and edge cases
- {empty, boundary, invalid, concurrency, permission cases}

## Manual tests
### T1: {name}
**Preconditions:** {account, data, build}
**Steps:**
1. ...
2. ...
**Expected:** {observable result}

## Platform matrix
| Dimension | Values to cover |
|---|---|
| Web browsers | latest Chrome, Safari, Firefox |
| Viewports | 390 px, 768 px, 1280 px |
| iOS | min supported, latest |
| Android | min supported, latest; one low-end device |
| Conditions | offline, slow network, permission denied, background/resume |
| Appearance | light, dark, large text |

## Exit criteria
{what must pass before release}
```

## Guidelines
- Expected results must be observable, not "works correctly".
- Prefer many fast low-level tests and few e2e tests.
- Record the build number and device for every manual run.
