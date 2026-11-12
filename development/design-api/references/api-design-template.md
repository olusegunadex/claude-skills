# API Design Template

```
# API Design: {name}

## Goal and callers
{who calls it, why, how often}

## Options considered
| Option | Simplicity | Flexibility | Compatibility | Notes |
|---|---|---|---|---|
| A | | | | |
| B | | | | |
**Chosen:** {option and one-line reason}

## Contract
### Request
`{METHOD} /path` or `functionName(params)`
| Field | Type | Required | Rules |
|---|---|---|---|

### Response
{shape, with a success example}

### Errors
| Code | When | Body |
|---|---|---|
{consistent shape: code, message, optional fields}

## Behaviour
- Auth and permissions:
- Pagination / limits:
- Idempotency / retries:
- Caching:

## Compatibility
{versioning; old mobile builds; deprecation plan}

## Examples
{request/response or usage snippets}

## Open questions
- ...
```
