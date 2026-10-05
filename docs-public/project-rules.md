# Project rules

<!-- project-lead-Opus5.5-agent, 2026-10-05. Owner decision R1, 2026-10-04. Only the owner changes this file. -->

Rules for this project that differ from the shared engineering rules. Where the two differ, this file wins. Anything not covered here follows the shared rules.

Agents and the reviewer read this file **from `main`**, never from a PR branch, so a PR can't change the rules it is judged by.

## Front end
- **React + TypeScript, built with Vite, as a single-page app.** This replaces the shared rules' default front end, for this project only.
- With it: React Router, TanStack Query, Vitest + Testing Library, and Playwright.
- The built front end is static files, served from a CDN.
- Accepted cost: about 40–80 KB more JavaScript than the default.

## Back end
- No change from the shared rules: PostgreSQL, Go and Chi, serving a JSON API to the front end.
