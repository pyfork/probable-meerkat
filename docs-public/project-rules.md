# Project rules

<!-- project-lead-Opus5.5-agent, 2026-10-05. Owner decision R1, 2026-10-04. Only the owner changes this file. -->
<!-- kit-keeper-Opus5.5-agent, 2026-10-12: the kit no longer has a default stack, so this file names both parts. -->

What this project is built with, and its rules where they differ from the shared engineering rules. Where the two differ, this file wins. Anything not covered here follows the shared rules.

Agents and the reviewer read this file **from `main`**, never from a PR branch, so a PR can't change the rules it is judged by.

## Front end
- **React + TypeScript, built with Vite, as a single-page app.**
- With it: React Router, TanStack Query, Vitest + Testing Library, and Playwright.
- The built front end is static files, served from a CDN.
- Accepted cost: about 40–80 KB more JavaScript than server-rendered HTML with HTMX.

## Back end
- Go and Chi with PostgreSQL, serving a JSON API to the front end. Stack rules: `docs/rules/stacks/go-chi.md`.
