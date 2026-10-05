# Decisions: Accounts and sign-in

<!-- project-lead-Opus5.5-agent, 2026-10-05. History only. Build from specs/features/accounts-and-sign-in.md. -->

- Sign-up and sign-in with a 6-digit email code, no password; a sign-up limit per network. (Writing Q24, 2026-10-04)
- One child per account at launch; siblings later; plans and payment codes saved under the child. (2026-10-05)
- Codes: "Send a new code" after 30 s, up to 5 an hour, a countdown at the limit; Admin can reset it. (2026-10-05)
- Two phones: the first to submit counts. (2026-10-05)
- Admin signs in with an email code only (no authenticator app), 12 hours at most. (2026-10-05)
- Recovery: an optional backup email (one, code-checked) instead of recovery phone numbers (SMS was too much wiring); 24-hour delay with a cancel link to the old email; manual check by Admin as the safety net, so recovery is never impossible. (owner, 2026-10-05)
- Senior engineer fixes (owner gwl, 2026-10-05): codes last 10 minutes and 5 wrong tries cancel them; one "Enter your email" step with the same message for every email; signed in 90 days after the last visit plus "Sign out on all devices"; an email on every admin sign-in; an admin action log; a generous per-network sign-up limit and a stricter per-email one. Admin emails are an allow-list in the database, never in this repository.
