# Security and Privacy (web and mobile)

## Input and output
### Validate on the server, always
**Rule:** Client checks are for UX. The server validates type, length, and range for every input, and sanitises free text before storing or rendering it.
### Encode output; never inject raw HTML
**Rule:** Don't use `dangerouslySetInnerHTML` or WebView `injectedJavaScript` with untrusted data. If HTML is required, sanitise it with a vetted library.
### Use parameterised queries
**Rule:** No string-built SQL. Use the ORM/query builder parameters or prepared statements.

## Authentication and authorisation
### Check authorisation on every request
**Rule:** Verify who the user is and whether they may access this specific record. Use database-level rules (e.g. Postgres row-level security) as a second layer where available.
### Sessions and tokens
**Rule:** Web: httpOnly, secure, SameSite cookies. Mobile: tokens in secure storage with short lifetimes and refresh rotation. Never put tokens in URLs.

## Secrets
### No secrets in client code or the repo
**Rule:** Anything shipped to a browser or app bundle is public. Keep service keys server-side, load from environment, and rotate anything leaked.
**Check:** secret scanning in CI; review for `NEXT_PUBLIC_` and `EXPO_PUBLIC_` values.

## Data
### Collect and keep the minimum
**Rule:** Only gather personal data you use. Encrypt in transit (TLS) and at rest where the platform supports it. Honour delete requests.
### Third-party SDKs
**Rule:** Review what each SDK collects before adding it. Update privacy labels and consent flows to match.

## Web-only
- Set a Content-Security-Policy and other security headers.
- Protect state-changing routes against CSRF.
- Rate-limit public endpoints and add bot protection to forms.

## Mobile-only
- Pin or validate TLS where the risk justifies it.
- Don't leave debug flags, test endpoints, or verbose logging in release builds.
- Request permissions at the moment of use with a clear reason.
