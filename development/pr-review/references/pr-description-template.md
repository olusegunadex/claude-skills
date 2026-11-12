# PR Description Template

```
## Summary
{1-3 sentences: what this changes and why}

## Changes
- {key change, grouped by area}

## Platform
- [ ] Web
- [ ] Mobile (iOS / Android)
- [ ] API / backend
{Mobile: native build required? yes/no}

## How to test
1. {steps}
2. {expected result}

## Screenshots / recordings
{before / after, with viewport or device}

## Risk and rollout
{migrations, feature flags, rollback plan, or "low risk"}

## Related
{ticket link, ADR, design}
```

## Rules
- Describe the change that exists in the diff, not intent that is not implemented.
- Keep it short. Link details instead of pasting them.
- Don't include secrets or customer data.
