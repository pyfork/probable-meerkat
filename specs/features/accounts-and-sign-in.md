# Brief: Accounts and sign-in

<!-- project-lead-Opus5.5-agent, 2026-10-05. DRAFT for the owner's re-approval. Split out of the writing brief (owner, 2026-10-04: one fact, one place).
     Decisions: specs/decisions/accounts-and-sign-in.md. -->

Words follow `specs/glossary.md`. Rules for every page are in `site-rules.md`.

## Who it's for
The parent who signs up, the child who uses the parent's phone or computer, and Admin.

## What should happen

### Sign-up and sign-in (parents)
- A parent signs up with their email: they type it, get a 6-digit code by email, and type the code in. No password.
- Signing in later (a new phone, or after signing out) works the same way: email, then a 6-digit code.
- The phone stays signed in, so the child just opens the site.
- After signing up, the parent adds one child: the child's first name. The name is used in feedback ("Super work, {name}!") and in emails to the parent.
- Writing Confidence's trial starts with this sign-up. Spelling Confidence's trial needs no sign-up; the parent signs up when they pay (see `plans-and-payment.md`).

### Codes
- A code works once.
- "Send a new code" appears 30 seconds after a code is sent. Up to 5 codes an hour per email.
- At the limit the screen says "Too many codes. Try again in N minutes." with the minutes counting down. Admin can reset the limit for a parent on the Parents tab.
- The screen also says "Check your spam folder".
- A limit on sign-ups from one network stops a script from making hundreds of accounts. A new email only gets the same fixed trial content, so fake emails gain nothing.

### One child per account
- One child per account at launch. Siblings come later.
- Each plan and payment code is saved under the child, not the parent, so siblings can be added later without changing anyone's existing plan.

### The same child on two phones
- The first phone to submit a task or round counts. The other phone shows "This task was finished on another phone" and moves on to the next one.

### Admin sign-in
- Only Admin's email can open the admin page, with an email code (the same 6-digit code as parents). No password.
- Admin stays signed in for 12 hours at most.

## Worked examples
| What happens | Result |
|---|---|
| A parent asks for 5 codes in 20 minutes, then a 6th | "Too many codes. Try again in 40 minutes." counting down |
| Admin clicks "Reset code limit" for that parent | The parent can ask for a new code straight away |
| The child submits task 2 on the tablet, then on the phone | The tablet's answer counts; the phone says the task was finished on another phone |

## Out of scope
Passwords. Signing in with Google or Facebook. A second child (later). Separate logins for children.

## Open questions
None.
