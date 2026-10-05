# Brief: Accounts and sign-in

<!-- project-lead-Opus5.5-agent, 2026-10-05. APPROVED by the owner, 2026-10-05. Split out of the writing brief (owner, 2026-10-04: one fact, one place).
     Decisions: specs/decisions/accounts-and-sign-in.md. -->

Words follow `specs/glossary.md`. Rules for every page are in `site-rules.md`.

## Who it's for
The parent who signs up, the child who uses the parent's phone or computer, and Admin.

## What should happen

### Sign-up and sign-in (parents)
- A parent signs up with their email: they type it, get a 6-digit code by email, and type the code in. No password.
- Sign-up and sign-in are one step ("Enter your email"). The screen says the same thing for every email, so nobody can find out whether an email has an account. A new email becomes a new account after its code.
- Signing in later (a new phone, or after signing out) works the same way: email, then a 6-digit code.
- The phone stays signed in for 90 days after the last visit, so the child just opens the site. The parent page has **"Sign out on all devices"** (for a lost phone).
- Signing up needs the Privacy Notice consent tick (see `site-rules.md`).
- After signing up, the parent adds one child: the child's first name. The name is used in feedback ("Super work, {name}!") and in emails to the parent.
- Writing Confidence's trial starts with this sign-up. Spelling Confidence's trial needs no sign-up; the parent signs up when they pay (see `plans-and-payment.md`).

### Codes
- A code works once, for 10 minutes. 5 wrong tries cancel it.
- "Send a new code" appears 30 seconds after a code is sent. Up to 5 codes an hour per email.
- At the limit the screen says "Too many codes. Try again in N minutes." with the minutes counting down. Admin can reset the limit for a parent on the Parents tab.
- The screen also says "Check your spam folder".
- A limit on sign-ups from one network stops a script from making hundreds of accounts. It is generous, because Malaysian mobile networks put many customers behind one internet address; the limit per email is stricter. A new email only gets the same fixed trial content, so fake emails gain nothing.

### Backup email and getting back in
- On the parent page, a parent can add **one backup email** (optional), confirmed with a code sent to it.
- **"Can't get into my email"** on the sign-in screen sends a code to the backup email. The parent then enters a new main email and confirms it with a code.
- The old main email gets a notice ("Your account email is changing. Not you? Cancel here."), and the change takes effect after 24 hours, so a stolen backup email can't take the account.
- **No backup email, or both lost:** the parent writes to the support email. Admin checks they are the payer (payment code, bank transaction number and the child's first name) and moves the account to the new email on the Parents tab. Getting back in is never impossible.
- After a plan is activated, the parent page shows a small "Add a backup email so you never lose access" until one is added.

### One child per account
- One child per account at launch. Siblings come later.
- Each plan and payment code is saved under the child, not the parent, so siblings can be added later without changing anyone's existing plan.

### The same child on two phones
- The first phone to submit a task or round counts. The other phone shows "This task was finished on another phone" and moves on to the next one.

### Admin sign-in
- Only emails on the admin allow-list can open the admin page, with an email code (the same 6-digit code as parents). No password. The allow-list is kept in the database, never in the code or this repository.
- Admin stays signed in for 12 hours at most.
- Every admin sign-in sends an email to Admin ("New sign-in to the admin page at 10:42pm"), so a stranger's sign-in is noticed at once.
- An **admin action log** records who did what and when: confirm, activate, undo, refund, cancel, delete, move an email, reset, and every Teaching settings change. Admin can read it on the admin page; nobody can edit it.

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
