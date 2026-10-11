# Decisions: Sign-in and codes

<!-- ux-designer-Opus5.5-agent, 2026-10-11. History only. Build from specs/features/sign-in-1-parents.md,
     sign-in-2-admin.md and specs/patterns.md (Email code, PT-53 to PT-66). -->

- Split into two parts by who signs in: part 1 Parents, part 2 Admin. The code itself is a shared pattern (Email code), because the parent page and the refund bank-details form use it too.
- Problems open with concept checks (owner, 2026-10-11). Checks 11 (part 1) and 9 (part 2) had no answer in the brief and became OQ-1 and OQ-2.
- Choices where the brief was loose (told the owner, 2026-10-11):
  - The Privacy Notice tick and the child's first name come **after** the code, on a Welcome screen. Before the code, every email must see the same screen (brief), so the site can't yet know the email is new.
  - No account exists until Create account is pressed. Leaving the Welcome screen keeps nothing.
  - Only the newest code works. The code is at the start of the email's subject, so it can be read from the phone's notification. The code email never holds a sign-in link.
  - Common misspelt email endings get "Did you mean …?", because a mistyped email is the usual reason a code never comes.
  - The per-network sign-up limit counts new accounts only, at the Create account step, starting at 30 an hour from one internet address (a server setting, not a Teaching setting).
  - The child is never stopped mid-task when a sign-in ends; answers waiting on the phone go to the same account only.
  - Can't get into my email: an email that isn't anyone's backup gets an explaining email instead of a code, so the screen still says the same for every email. The parent isn't signed in until the 24 hours are over; devices already signed in stay signed in. One waiting change per account.
  - Admin sign-in sends codes only to allow-list emails (others get nothing, so a stranger can't fill a parent's inbox). The 12 hours count from the sign-in and aren't made longer by use; a bar warns 10 minutes before. What Admin was typing in a dialog comes back after signing in again.
  - The Log page is part of this area (the brief puts the action log under Admin sign-in). It has search by payment code or email. Entries are kept 7 years like payment records; a deleted family's entries keep the payment code and lose the email.
