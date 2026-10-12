# ADR-001: The front end is a React single-page app

<!-- kit-keeper-Opus5.5-agent, 2026-10-12. Moved here from docs-public/project-rules.md and the owner's
     decision R1 (2026-10-04). Template: the Senior Signal starter kit's ADR template. -->

Status:   Accepted · 2026-10-04
Door:     one-way
Deciders: the owner

## Context
The front end decides how every screen is built, tested and served. It is costly to change once
screens exist. At the time, the kit's default front end was server-rendered HTML with HTMX, with a
Svelte island where justified. The owner chose otherwise for this product.

## Options considered
1. Server-rendered HTML with HTMX, and a Svelte island where justified (the kit's default then)
   + Less JavaScript sent to the browser.  − Not the owner's choice for this product.
2. React + TypeScript single-page app, built with Vite
   + The owner's choice for this product. Static files, served from a CDN.
   − About 40–80 KB more JavaScript. The browser now holds state the server also knows.

## Decision
Option 2: React + TypeScript, built with Vite, as a single-page app, with React Router, TanStack
Query, Vitest + Testing Library, and Playwright. The built front end is static files, served from a
CDN. The back end serves it a JSON API.

## Consequences
+ The app keeps working offline, opens offline if opened before, and sends answers later (owner, 2026-10-04).
+ The front end needs no server of its own.
− About 40–80 KB more JavaScript than server-rendered HTML with HTMX (accepted by the owner).
− State in the browser has to be reconciled with the server: shared engineering rules, section 5.
− Add-ons outside the chosen set must be kept out: a plain check against an allowed list,
  written into the first build slice's plan (owner gwl, 2026-10-06; R2).

## Revisit when
The owner names a trigger, for example the front-end JavaScript passing a size the owner sets.
