# Spec: Sign-in and codes, part 1 of 2: Parents

## Problem
A parent has no password, only an email code, so the code must reach them and work first time on a phone, without letting a stranger in or showing anyone whether an email has an account.

### Concept checks
1. Does a parent have a password? → No.
2. Does the screen show whether an email already has an account? → No (AC-10, AC-30).
3. Is the Privacy Notice tick asked before the code, or after it? → After, and only for a new email (AC-16, AC-17).
4. Can a code be used twice? → No (PT-53).
5. A parent types 5 wrong codes. Does that code still work? → No (PT-58).
6. Does the child have to sign in every day? → No. A phone stays signed in for 90 days after the last visit (AC-24).
7. The sign-in ends while the child has a finished answer waiting on the phone. Is the answer lost? → No (AC-27).
8. Someone has only the parent's backup email. Can they take the account at once? → No. The change waits 24 hours, and the old email can cancel it (AC-36, AC-37).
9. Is getting back in ever impossible? → No. Admin can move the account (AC-41).
10. Does the Spelling trial need an account? → No. The parent signs up when they pay (AC-3).
11. A parent signs up to pay for Spelling. Do the Writing trial's 72 hours start then? → ? (decide: OQ-1)

## Goals and non-goals
1. **Goals**
   - A parent signs up or signs in on a phone with an email and a code, in under a minute.
   - Nobody can learn from these screens whether an email has an account.
   - A code that doesn't come has a clear next step: spam, a new code, or a different email.
   - The child opens the site and carries on, with no sign-in, for 90 days after the last visit.
   - A parent who loses their email gets back in, and a stranger with only the backup email can't take the account quickly.
2. **Non-goals**
   - The parent page's buttons: Sign out, Sign out on all devices, adding or changing the backup email, Delete my account and data (parent page spec, design area 10). This part says only what a device sees when its sign-in ends.
   - Admin's sign-in and the Log (part 2).
   - Admin moving an account to a new email, and Reset code limit (Parents tab spec).
   - The same child on two phones (the child's pages specs).
   - The home page itself, beyond its Sign in link (every page spec).
   - The Privacy Notice's text (a lawyer writes it, `site-rules.md`).
   - A second child, passwords, and Google or Facebook sign-in (`accounts-and-sign-in.md`, out of scope).

<!-- ux-designer-Opus5.5-agent, 2026-10-11. DRAFT for the owner. Part 1 of the rules for the approved brief
     specs/features/accounts-and-sign-in.md. Part 2: sign-in-2-admin.md. Shared rules (PT-n): specs/patterns.md.
     Decisions: specs/decisions/sign-in.md. -->

Words follow `specs/glossary.md`. The brief: `accounts-and-sign-in.md`. Trials and paying: `plans-and-payment.md`. Rules for every page: `site-rules.md`. Words in *italics* are on-screen words from the table at the end.

## Patterns used
Email code (PT-53 to PT-66), Buttons that change something (PT-35 to PT-37), Times and money (PT-50).

---

## Where sign-in starts
- **AC-1** Signed out, the home page shows *Sign in* at the top right.
- **AC-2** "Try 3 days for free" (Writing Confidence) opens *Email title*.
- **AC-3** Paying for Spelling Confidence after its trial, with no account, opens *Email title* first, then the pay page (`plans-and-payment.md`). The Spelling trial itself never asks for an email.
- **AC-4** Opening the child's pages, the parent page or the pay page while signed out opens *Email title*. After signing in, the parent lands on the page they were going to.
- **AC-5** Signed in, the sign-in screens are never shown: their address opens the child's pages.

## Enter your email
- **AC-6** One screen for signing up and signing in, titled *Email title*, with one email box and the *Send code button*. The box brings up the phone's email keyboard, with no autocorrect and no capital first letter.
- **AC-7** Spaces at either end of the email are removed, and capital letters don't matter.
- **AC-8** If what was typed isn't an email (no @, or no dot after it), pressing Send code shows *Not an email* under the box. Nothing is sent.
- **AC-9** A common misspelt email ending (for example gmial.com, gmail.co, yahoo.com.mt, hotmial.com) shows *Did you mean* with the corrected email as a button. Tapping it puts that email in the box. Send code still works with what was typed.
- **AC-10** Send code sends a code (PT-53) and opens the code screen. Every email gets the same screen and the same words, whether it has an account or not.
- **AC-11** An email at its code limit opens the code screen showing Too many codes (PT-61), the same for every email.

## The code screen
- **AC-12** The code screen follows Email code (PT-53 to PT-66) and is titled *Code title*.
- **AC-13** *Use a different email* goes back to Enter your email with the email still in the box. The browser's Back button does the same.
- **AC-14** If Code bounced shows (PT-62), Use a different email is the main button.
- **AC-15** The right code for an email with an account signs the parent in. They land where they were going (AC-4), or on the child's pages.
- **AC-16** The right code for a new email opens the *Welcome title* screen (AC-17). No account exists yet.

## A new account
- **AC-17** The Welcome screen names the email, then asks for the child's first name (*Child's name*), then the consent tick (*Consent*, `site-rules.md`). The Privacy Notice link opens in a new tab, so nothing typed is lost.
- **AC-18** The child's first name takes 1 to 40 characters: letters in any language, spaces, hyphens and apostrophes. Spaces at either end are removed.
- **AC-19** *Create account* always works when pressed. If the name is missing or not allowed, *Name needed* or *Letters only* shows under the box. If the tick is missing, *Tick needed* shows under it. Focus goes to the first thing missing.
- **AC-20** Create account makes the account, adds the child, and signs the parent in. They land where they were going (AC-4); from "Try 3 days for free", on Writing Confidence's start screen, with the trial started (`plans-and-payment.md`).
- **AC-21** Leaving the Welcome screen without pressing Create account makes no account. The next right code for that email opens the Welcome screen again.
- **AC-22** New accounts from one internet address are limited, generously, to a number set on the server (it starts at 30 an hour). At the limit, Create account shows *Too many new accounts*, and what was typed stays. Signing in to an account that already exists is never stopped by this limit.
- **AC-23** If Create account can't reach the server: PT-36. What was typed and ticked stays.

## Staying signed in
- **AC-24** A sign-in lasts 90 days after the last visit on that browser. Every visit starts the 90 days again.
- **AC-25** The child is never stopped in the middle of a task. The sign-in is only checked when a page opens or an answer is sent.
- **AC-26** When a device's sign-in has ended (90 days, Sign out, or Sign out on all devices), the next page opened shows Enter your email with the *Signed out note*. After signing in, the parent is back on the same page.
- **AC-27** Answers waiting on the phone (`site-rules.md`) are kept when the sign-in ends. They are sent once the same account signs in again on that phone, and never to a different account.

## Can't get into my email
- **AC-28** Enter your email has *Can't get into my email* under Send code. It opens a screen titled *Recovery title*, with the *Recovery line*, one email box and Send code.
- **AC-29** The parent types their backup email. Send code opens a code screen (PT-53 to PT-66) for that email.
- **AC-30** Every email gets the same screen and the same words. An email that is a backup for an account gets a code. Any other email gets the *Not a backup email* instead, which explains how to write to support.
- **AC-31** The right code opens a screen titled *New email title*, with one email box. Send code sends a code to the new email, and its code screen follows PT-53 to PT-66.
- **AC-32** If the new email belongs to another account, its right code shows *Email taken*, and the parent can try another email.
- **AC-33** If the new email is the backup email itself, the change goes ahead, and once it takes effect the account has no backup email. The parent page then asks for one (`accounts-and-sign-in.md`).
- **AC-34** The right code for the new email shows the *Change waiting* screen. The parent is not signed in yet.
- **AC-35** The old main email gets the *Change notice*, with a Cancel link. The new email and the backup email get the *Change waiting email*.
- **AC-36** The Cancel link stops the change and opens a page saying *Change cancelled*. No sign-in is needed. The new email and the backup email get the *Cancelled email*. Once the change has taken effect, the link shows *Too late to cancel* instead.
- **AC-37** 24 hours after the right code for the new email, the account's main email changes. The old email gets the *Changed email*, and the new email gets the *You can sign in email*. Devices already signed in stay signed in.
- **AC-38** Until then, signing in with the old main email still works.
- **AC-39** An account has only one waiting change. A new one replaces it, starts the 24 hours again, and sends the Change notice again.
- **AC-40** These codes count towards each email's 5 codes an hour (PT-61).
- **AC-41** The Recovery screen also shows the *No backup line*, with the support email as a link that opens the phone's email app. Admin moves the account on the Parents tab (`accounts-and-sign-in.md`).

## Layout
- **AC-42** Every sign-in screen is one column, at most 440 px wide, in the middle of the page. Below 472 px it fills the width with 16 px at each side. No layout change is needed at any width, because each screen asks for one thing.
- **AC-43** The main button sits straight under the box or tick it belongs to, never fixed to the bottom of the screen, so the phone keyboard can't cover it. At 667 × 375 the screen scrolls, and every box and button can be reached.
- **AC-44** Each screen's title is its first heading. When a screen opens, focus goes to its first box. Enter in a box presses that screen's main button.
- **AC-45** Every sign-in screen has the footer, with the Privacy Notice link (`site-rules.md`).

## Emails
- **AC-46** Every email in this part comes from the site's address with Reply-To support@puascari.com and ends with the footer (`admin-page.md`, `site-rules.md`). Its words are in the table below.

## Action log
- **AC-47** Account emails changing, and changes cancelled, each write one entry in the admin action log, with "parent" as who (PT-52).

---

## Words on screen
`{email}` is an email, `{name}` the child's first name, `{n}` a number, `{date}` and `{time}` follow PT-50. Email code words are in `specs/patterns.md`.

| Name | Words | Example |
|---|---|---|
| Sign in | Sign in | |
| Email title | Enter your email | |
| Send code button | Send code | |
| Not an email | Type your full email, like name@gmail.com | |
| Did you mean | Did you mean {email}? | Did you mean sharifah.n@gmail.com? |
| Code title | Check your email | |
| Use a different email | Use a different email | |
| Welcome title | Welcome to Learn English | |
| Child's name | Your child's first name | |
| Consent | I am the parent or guardian of this child, and I agree to the Privacy Notice for myself and my child. | |
| Create account | Create account | |
| Name needed | Type your child's first name | |
| Letters only | Use letters only | |
| Tick needed | Please tick to agree | |
| Too many new accounts | Too many new accounts from this internet connection. Try again in {n} minutes, or use mobile data. | |
| Signed out note | You've been signed out. Sign in to carry on. | |
| Can't get into my email | Can't get into my email | |
| Recovery title | Use your backup email | |
| Recovery line | We'll send a code to the backup email you added on the parent page. | |
| No backup line | No backup email, or lost both? Email support@puascari.com with your payment code, the bank transaction number and your child's first name. | |
| New email title | Your new email | |
| Email taken | This email already has an account. Try another email. | |
| Change waiting | Your account email changes to {email} on {date}, {time}. We've told your old email, in case this wasn't you. Sign in with {email} after that. | Your account email changes to aisyah.h@gmail.com on 12 Oct, 9:14pm. … |
| Change cancelled | The email change is cancelled. Your account email stays the same. | |
| Too late to cancel | This change has already happened. Email support@puascari.com for help. | |

### Emails
| Name | Subject | What it says |
|---|---|---|
| Not a backup email | About your Learn English sign-in | This email isn't a backup email for any account. If you can't get into your account, write to support@puascari.com with your payment code, the bank transaction number and your child's first name. |
| Change notice | Your account email is changing | Your account email will change to {new email} on {date}, {time}. Not you? Cancel here (link). |
| Change waiting email | Your account email is changing | The account email will change to {new email} on {date}, {time}. |
| Cancelled email | Email change cancelled | The change to {new email} was cancelled from the old email. |
| Changed email | Your account email has changed | Your account email is now {new email}. Not you? Email support@puascari.com. |
| You can sign in email | You can sign in now | Your account email is now {email}. Sign in with it to carry on. |

## Content for testing
All names and emails are made up.

| What | Test value |
|---|---|
| Long email, no spaces | sharifah.nuraisyahhumaira.syedkhairul@yahoo.com.my |
| Misspelt endings | aiman@gmial.com, aiman@gmail.co, aiman@yahoo.com.mt, aiman@hotmial.com |
| Not emails | aiman, aiman@gmail, @gmail.com |
| Long child's first name | Muhammad Aiman Haziq |
| Names in other scripts | 李明 (Chinese), Nur'Aisyah, Siti-Hajar |
| Not names | Aiman2, 😀 |
| Pasted codes | "482 915", "482-915", " 482915 " |
| Screen sizes | 320 × 568, 667 × 375 (phone turned sideways), 390, 768 and 1280 px wide, large text on |

## Worked examples
| What happens | Result |
|---|---|
| A new parent types aiman@gmial.com | Did you mean aiman@gmail.com? Tapping it fixes the box |
| A new parent enters the right code, then closes the tab on the Welcome screen | No account. The next right code opens the Welcome screen again |
| A parent asks for 5 codes in 20 minutes, then a 6th | Too many codes. Try again in 40 minutes, counting down (PT-61) |
| A phone last visited 1 Jan; the child opens the site on 31 Mar | Still signed in (89 days). The 90 days start again |
| A phone last visited 1 Jan; the child opens the site on 2 Apr | Enter your email, with "You've been signed out" |
| The parent uses Can't get into my email at 9:14pm on 11 Oct | The change takes effect at 9:14pm on 12 Oct. Until then, the old email still signs in and can cancel |
| The real parent taps Cancel in the old email at 3pm on 12 Oct | The change never happens; the new and backup emails are told |
| A stranger types someone else's email on Enter your email | The same screen as for anyone. The owner of that email gets a code they can ignore |

## Open questions
**OQ-1 (concept check 11): a parent who signs up only to pay for Spelling Confidence. When do their 72 hours of Writing Confidence trial start?**
- **Lean:** when the child first opens Writing Confidence. The brief says the trial starts with sign-up, which fits a parent who came for Writing. A Spelling parent who signs up to pay would otherwise lose the Writing trial without seeing it.
- **Other way:** at sign-up, for everyone, exactly as the brief says. Simpler, but a Spelling parent's Writing trial runs out unseen.
