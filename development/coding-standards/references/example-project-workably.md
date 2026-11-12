# Example: Project-Specific Rules (Workably)

This shows what a project-level override looks like. Rules here win over the generic web and mobile files when working in that repo. Copy the shape for other projects; do not treat these as universal.

Source: that project's `CLAUDE.md`.

## API routes
### Build redirects with `getAppOrigin`
**Rule:** Use `getAppOrigin(request)` from `@/lib/auth-urls` for any redirect or absolute URL in an API route.
**Primary reason:** Behind the proxy, `request.url` resolves to `localhost`, which breaks production redirects.
**Applies when:** the route redirects or returns an absolute URL.
**Does not apply when:** the route returns JSON only.
Avoid: `new URL(request.url).origin`.

### Route group by caller
**Rule:** Put routes under `api/admin/` (org-admin protected), `api/public/` (unauthenticated), or `api/auth/` and `api/orgs/` by purpose.
**Primary reason:** The middleware treats `/api/public/**` as the only public API path.

## Validation
### Validate and sanitize all input with Zod
**Rule:** Define a Zod v4 schema under `src/lib/schemas/` and parse every request body with it. Free-text fields pass through `sanitizeText()` or `sanitizeOptional()`.
**Primary reason:** Public text inputs must be stripped of HTML, `javascript:`, `data:`, and inline handlers server-side.
**Applies when:** the input comes from a user, public or admin.
**Does not apply when:** the value is generated server-side.

### Match the length limits
**Rule:** Server and HTML `maxLength`/`pattern` use the same limits.
| Field | Limit |
|---|---|
| Email | 254 |
| Password | 8-128 |
| Org name | 120 |
| Org slug | 2-60, `^[a-z0-9][a-z0-9-]*[a-z0-9]$` |
| Survey/feedback title | 200 |
| Short text answer | 500 |
| Long text / description | 5000 |
| Author name | 100 |
| Phone | 30 |

## Multi-tenancy
### Get the tenant from headers
**Rule:** In server components use `getTenantFromHeaders()` or `requireTenant()` from `@/lib/tenant-server`. Never trust a tenant id sent by the client.
**Primary reason:** The middleware resolves the organisation from the host and sets trusted headers.
**Applies when:** the code reads or writes org-owned data.

### Do not hard-code domains
**Rule:** Use `NEXT_PUBLIC_ROOT_DOMAIN`, `parseHost()`, and `usesApexDashboard()`. Local dev serves the dashboard from the apex (`localhost:3000/dashboard`).
**Primary reason:** Subdomain cookies do not reliably cross `*.localhost`.

### Public tenant paths stay public
**Rule:** Only `/s/**`, `/feedback`, `/book/**`, and `/api/public/**` skip auth. New public paths need a middleware change and a reviewer.

## Auth
### Redirect after login with the app origin
**Rule:** Post-login redirects go through `getPostLoginRedirect()` and use `getAppOrigin(request)` as the base.

## Components
### Mobile first for dashboard screens
**Rule:** Screens must work at 390x844 and 1280x720. Use the existing patterns: slide-in sidebar via `DashboardShell`, tab switcher with `lg:hidden` for dense editors, fixed overlay panels on mobile.
**Check:** Playwright desktop and mobile projects (`npm run test:e2e`).

## Database
### Migrations are numbered and additive
**Rule:** New schema changes go in `supabase/migrations/NNN_name.sql` in sequence. Do not edit a migration that has shipped.

## Testing
### Test what you add
**Rule:** Add Jest tests for new lib code, schemas, and components. Run `npm test`, `npm run lint`, and `npm run build` before finishing.
