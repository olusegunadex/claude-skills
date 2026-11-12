# Triage Template

```
# Triage: {short title}

**Type:** bug | regression | performance | security | data | question | request
**Platform:** web | iOS | Android | API | multiple
**Severity:** Critical | Major | Minor | Trivial
**Reproducibility:** Always | Sometimes | Once | Not reproduced

## Known
- {fact, with source}

## Missing
- {item} (ask: {who})

## Suspected areas (leads, not conclusions)
- `path/or/screen`: {why}

## Recommended next step
{ask for info | investigate | create ticket | close}
```

## Severity scale
| Level | Meaning |
|---|---|
| Critical | Security issue, data loss, app won't open, payments broken, many users |
| Major | Core flow broken for some users, no workaround |
| Minor | Non-core problem or an easy workaround exists |
| Trivial | Cosmetic |

## Reproducibility
Record the exact steps and environment that produced it. "Not reproduced" is a valid result; say what was tried.
