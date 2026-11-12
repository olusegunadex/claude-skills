# Web Standards (TypeScript, React, Next.js)

## Components
### Server by default, client when needed
**Rule:** In Next.js App Router, keep components as Server Components. Add `"use client"` only for state, effects, browser APIs, or event handlers, and push it down to the smallest leaf.
**Primary reason:** Less JavaScript shipped and simpler data fetching.
**Does not apply when:** the project uses a different React framework with its own model.

### Derive, don't duplicate state
**Rule:** Compute values from props or state during render. Use effects only to sync with external systems.
**Primary reason:** Duplicated state drifts out of sync.

### Stable keys and no index keys for dynamic lists
**Rule:** Use a stable id as the key. Index keys are fine only for static lists that never reorder.

## Data and APIs
### One validated shape per endpoint
**Rule:** Define the request and response schema once and share the type. Return a consistent error shape (`code`, `message`, optional `fields`).
**Primary reason:** Callers and tests can rely on it.

### Never trust client-supplied identity or scope
**Rule:** Derive user and tenant/org from the session or server context, not from the request body.

## Performance
### Respect Core Web Vitals
**Rule:** Optimise images (`next/image`, sized, lazy below the fold), avoid layout shift, split large bundles, and measure before micro-optimising.
**Check:** Lighthouse or field data; LCP, INP, and CLS in the "good" range.

## Accessibility
### Meet WCAG 2.2 AA
**Rule:** Semantic HTML first. Every control is keyboard reachable with a visible focus state. Inputs have labels. Colour contrast is at least 4.5:1 for text. Don't convey meaning by colour alone.
**Check:** keyboard-only pass plus an automated check (axe).

## Styling
### Use design tokens and the component library
**Rule:** Use the shared tokens (colour, spacing, type) and existing components (e.g. shadcn/ui) before writing custom styles.
**Does not apply when:** a one-off marketing page with its own art direction.

## Responsive
### Design for 390 px and 1280 px
**Rule:** Layouts work from small phones to desktop. Touch targets are at least 44x44 px.
