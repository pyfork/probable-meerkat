# Spec: Sign-in and codes, part 2 of 2: Admin

## Problem
Whoever opens the admin page can confirm payments, refund money and delete families, so only Admin may get in, a sign-in must end by itself, and every action must leave a record nobody can change.

### Concept checks
1. Can any parent's email open the admin page? → No. Only emails on the allow-list (AC-2).
2. Does the admin sign-in screen show whether an email is on the allow-list? → No (AC-2).
3. Can the allow-list be changed on a web page? → No. Only by a command on the server (`admin-page.md`).
4. Does an admin sign-in last 90 days, like a parent's? → No. 12 hours at most (AC-6).
5. Does using the admin page make the 12 hours longer? → No. They count from the sign-in (AC-6).
6. Does the site have a password? → No. Only a 6-digit email code.
7. Admin signs in. Is an email sent? → Yes, every time (AC-12).
8. Is Admin's sign-in the same as a parent sign-in on the same browser? → No. They are separate (AC-5).
9. Can anyone change or delete a log entry? → No (AC-22).
10. Admin gets a sign-in email that wasn't them. Can they end that sign-in from the email? → ? (decide: OQ-2)

## Goals and non-goals
1. **Goals**
   - Admin signs in with the same email code as parents, on a phone or a laptop.
   - A stranger's sign-in is noticed at once.
   - An admin sign-in never lasts more than 12 hours, and Admin never loses what they were typing when it ends.
   - Admin can look up who did what, and when, for any payment or family.
2. **Non-goals**
   - More than one Admin login, or roles with different rights (`admin-page.md`, out of scope).
   - Changing the allow-list on a web page. It is a server command, kept in the owner's private notes (`admin-page.md`).
   - A password for the site, or an authenticator app. Every sign-in is a 6-digit email code (`specs/decisions/accounts-and-sign-in.md`).
   - Undoing an action from the Log. Undo stays on the row where the action was done.

<!-- ux-designer-Opus5.5-agent, 2026-10-11. DRAFT for the owner. Part 2 of the rules for the approved brief
     specs/features/accounts-and-sign-in.md. Part 1: sign-in-1-parents.md. Shared rules (PT-n): specs/patterns.md.
     Decisions: specs/decisions/sign-in.md. -->

Words follow `specs/glossary.md`. The brief: `accounts-and-sign-in.md`. The admin page: `admin-page.md`. Words in *italics* are on-screen words from the table at the end. "Part 1, AC-n" means a rule in `sign-in-1-parents.md`.

## Patterns used
Email code (PT-53 to PT-66), Admin tabs (PT-1 to PT-5), Row becomes a card (PT-6 to PT-11), Lists move only when Admin asks (PT-12 to PT-14), Buttons that change something (PT-35 to PT-38), List states (PT-39 to PT-41), Labels on a row (PT-48, PT-49), Times and money (PT-50), Action log (PT-52).

---

## Admin sign-in
- **AC-1** Opening the admin page while signed out shows a screen titled *Admin email title*, laid out like part 1's Enter your email (part 1, AC-6 to AC-8, AC-42 to AC-44). It has no Can't get into my email and no new-account step.
- **AC-2** Every email gets the same code screen and the same words (*Admin code sent*). Only an email on the allow-list is sent a code. Any other email is sent nothing, so a stranger can't use this screen to fill a parent's inbox.
- **AC-3** The admin code email has its own subject (*Admin code subject*), so it can't be mixed up with a parent's code.
- **AC-4** The right code opens the admin page on the tab Admin used last on that device, or on Verify.
- **AC-5** Admin's sign-in and a parent sign-in on the same browser are separate. Signing in or out of one never changes the other.

## How long it lasts
- **AC-6** An admin sign-in ends 12 hours after the right code, however much the page is used.
- **AC-7** From 10 minutes before the end, the *Ends soon bar* shows above the tab bar.
- **AC-8** When it has ended, the next action shows Signed out (PT-38). The action is not done.
- **AC-9** What Admin had typed or picked in an open dialog (for example a Problem email note) is kept on that device. After signing in again, the same dialog opens with it filled in.
- **AC-10** *Sign out*, at the end of the tab bar, ends the sign-in on this device at once and shows the Admin sign-in screen.
- **AC-11** An email taken off the allow-list is signed out on every device at its next action.

## The sign-in email
- **AC-12** Each right admin code sends the *Admin alert* to that email: the time (PT-50), the device and browser (for example "Safari on iPhone"), and the town the internet address points to, when it is known.
- **AC-13** It is sent when the code works, not when the code is asked for.
- **AC-14** It never holds a code or a link that signs anyone in.
- **AC-15** The alert also says what to do if it wasn't Admin (*Not you line*).

## The Log
- **AC-16** *Log*, at the end of the tab bar before Sign out, opens the Log page at its own address (PT-5). It is not a tab and has no count.
- **AC-17** The Log lists every entry in the admin action log (PT-52), newest first. Each entry shows when (PT-50, with seconds), who (the admin email, or "parent" or "site" for things they did), what, and which payment code or family (the account email). With no entries it shows *Log empty* (PT-40).
- **AC-18** An entry shows the details its action has: the amount, the reason, or a Teaching setting's old and new value.
- **AC-19** An Undo entry names the entry it undid (*Undid line*).
- **AC-20** Admin sign-ins and sign-outs are entries too, with the device and browser.
- **AC-21** The Log shows 50 entries at first. *Show more* adds the next 50 below, and what is on screen stays.
- **AC-22** No entry has a button that changes it. Nobody can edit or delete an entry from any page.
- **AC-23** One search box finds entries by payment code (with or without the #) or by email. *Clear* shows every entry again.
- **AC-24** Entries for a test family carry the Test family label (PT-48).
- **AC-25** Entries are kept 7 years, like payment records (`site-rules.md`). When a family is deleted, its entries keep the payment code, and the email shows as *Deleted family*.
- **AC-26** New entries don't appear by themselves. The List changed bar shows instead (PT-12 to PT-14).

## Layout
- **AC-27** The Log, from 1024 px up, is a table with these columns in order: When · Who · What · Payment code or family · Details.
- **AC-28** Below 1024 px, each entry is a card (PT-6 to PT-11), in this order: what · payment code or family · details · when · who. What happened matters most on a phone.
- **AC-29** The Ends soon bar is one line high at 1024 px and wraps onto more lines below that. It never covers the tab bar.

---

## Words on screen
`{email}` is an email, `{code}` a 6-digit code, `{date}` and `{time}` follow PT-50, `{n}` a number.

| Name | Words | Example |
|---|---|---|
| Admin email title | Admin sign-in | |
| Admin code sent | If this email can open the admin page, we've sent it a 6-digit code. | |
| Ends soon bar | Your sign-in ends at {time}. Finish what you're doing, then sign in again. | Your sign-in ends at 10:42pm. … |
| Sign out | Sign out | |
| Log | Log | |
| Undid line | Undid: {what} at {time} | Undid: Activate #1601319 at 9:14:05pm |
| Show more | Show more | |
| Search | Payment code or email | |
| Clear | Clear | |
| Deleted family | Deleted family | |
| Log empty | Nothing in the log yet. | |

### Emails
| Name | Subject | What it says |
|---|---|---|
| Admin code subject | {code} is your admin sign-in code | Body as the Code email body (`specs/patterns.md`) |
| Admin alert | New sign-in to the admin page at {time} | Signed in {date}, {time} · {device and browser} · near {town}, when known |
| Not you line | (in the Admin alert) | Not you? Someone can read your email inbox, because a code can only be read there. Lock your inbox now (your email provider's own settings), then follow the allow-list steps in your private notes. |

## Content for testing
| What | Test value |
|---|---|
| Long admin email | the owner's allow-list email (kept in the database only, never in the repository) and a made-up 50-character email |
| Longest log entry | Teaching setting "Box return times" changed from "next round, 1, 3, 7, 14 days" to "next round, 2, 5, 10, 30 days" |
| Log sizes | 0 entries, 1 entry, 51 entries (to show Show more), 5,000 entries |
| Device names | Safari on iPhone, Chrome on Android, Chrome on Mac, an unknown browser |
| Screen sizes | 320 × 568, 667 × 375, 390, 768 and 1280 px wide, a 1280 px laptop split in half |

## Worked examples
| What happens | Result |
|---|---|
| Admin signs in at 9:00am | The alert email goes at once. The Ends soon bar shows at 8:50pm; the sign-in ends at 9:00pm |
| Admin is typing a Problem note at 9:01pm and presses Send | Signed out shows; nothing is sent. After signing in, the dialog opens with the note filled in |
| A stranger types a parent's email on Admin sign-in | The same words as for Admin; no email goes anywhere |
| Admin searches the Log for 1601319 | Every entry for #1601319: Confirm, Activate, Undo, and so on |

## Open questions
**OQ-2 (concept check 10): if Admin gets a sign-in email that wasn't them, can they end that sign-in from the email?**
- **Lean: yes.** Add "Not you? End every admin sign-in" to the alert. One tap ends every admin sign-in on every device, and writes a Log entry. Admin then locks their email inbox (the only place a code can be read), signs in again with a new code and, if needed, follows the allow-list steps. Without it, a stranger's sign-in runs for up to 12 hours, and the only stop is a server command.
- **Other way:** keep the alert as it is now. It tells Admin, but only the server command can stop the stranger.
