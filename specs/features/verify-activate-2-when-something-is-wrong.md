# Spec: Verify and Activate, part 2 of 3: When something is wrong

## Problem
1. **The problem:** Some payments can't simply be confirmed: the code isn't in the bank, the receipt is unreadable, or it looks like a second payment. With no way to say what's wrong, the parent waits on "still being checked" and never learns why.
2. **Why this spec exists:** To let Admin tell the parent exactly what is wrong, check the email before it goes, and follow every receipt through to an end: confirmed, re-sent, not found or closed.

## Goals and non-goals
1. **Goals**
   - Admin can send a clear problem email in under a minute, and sees exactly what it says before it goes.
   - A re-sent receipt lands on the same row, with its history.
   - No receipt sits unanswered: after 14 days the parent is told without Admin doing anything.
   - An email that didn't reach the parent is seen and can be sent again.
   - A receipt that will never be confirmed can be closed, with a reason, and the parent's page says so in plain words.
2. **Non-goals**
   - Conversations with parents on the admin page. Replies stay in Admin's inbox (`admin-page.md`).
   - Writing the owner's fixed email wording. That is content, kept in the database (`site-rules.md`).
   - The amount box for Wrong amount and what follows from it (part 3).
   - Reminders or WhatsApp messages to parents before the 14 days.
   - The parent's receipt form itself (`plans-and-payment.md`).

<!-- ux-designer-Opus5.5-agent, 2026-10-10. DRAFT for the owner. Part 2 of the rules for the Verify and Activate tabs of the approved
     brief specs/features/admin-page.md. Builds on part 1: verify-activate-1-check-and-start.md. Part 3: verify-activate-3-money-that-doesnt-match.md.
     Shared rules (PT-n): specs/patterns.md. Decisions: specs/decisions/verify-activate.md. -->

Words follow `specs/glossary.md`. The brief: `admin-page.md`. Payment rules: `plans-and-payment.md`. Words in *italics* are on-screen words from the table at the end. "Part 1, AC-n" means a rule in `verify-activate-1-check-and-start.md`.

## Patterns used
The same as part 1, plus Dialog (PT-42 to PT-45), Choice list (PT-46, PT-47) and Email didn't arrive (PT-30 to PT-34).

---

## Problem with this payment
- **AC-1** Each Verify row has a *Problem button*. It opens a dialog (PT-42 to PT-45) titled *Problem title*.
- **AC-2** Admin picks one reason from a choice list (PT-46, PT-47): *Wrong amount*, *Code not found*, *Receipt unclear* or *Possible double payment*. At first none is picked, except on a row labelled Possible double payment, where that reason starts picked.
- **AC-3** Wrong amount also asks for the amount in the bank. That box and what follows from it are in part 3.
- **AC-4** A note box, optional, takes up to 300 characters, with the *Note counter*.
- **AC-5** Over 300 characters, the counter becomes *Too long* in red with a warning icon, and the send button is off. The text is never cut.
- **AC-6** The dialog shows the email the parent will get: the owner's fixed wording for the picked reason, then the note. It updates as Admin picks and types. Before a reason is picked it shows *Pick a reason*.
- **AC-7** The *Send button* names the parent's receipt email. It is off until a reason is picked.
- **AC-8** Sending emails the parent, closes the dialog and adds the *Problem line* to the row. There is no Undo, because an email can't be called back. The email preview is the check.
- **AC-9** Sending also reopens the parent's receipt form, and the row stays on Verify. (Part 3 has the one exception: too much money.)
- **AC-10** Every Problem email sent for a row is listed on it, newest first.
- **AC-11** Closing the dialog without sending sends and records nothing. What was picked and typed stays filled in for that row until the page is reloaded.
- **AC-12** If sending fails, the dialog stays open with *Send failed*. Nothing is recorded, and what was picked and typed is kept.

## A new receipt on the same row
- **AC-13** A receipt sent through a form reopened by a Problem email joins the same row, not a new one. When the list updates (PT-14), the row is at the top with the *New receipt line*, and View receipt opens the newest receipt.
- **AC-14** The row's earlier receipts are listed under *Earlier receipts*, each with its transaction number, when it was sent, its recorded amount (if any) and its own View receipt.
- **AC-15** Receipts on the same row never set Receipt already used or Possible double payment against each other. A parent who re-sends a clearer screenshot of the same payment gets no label.
- **AC-16** A receipt sent after its row was closed starts a new row.

## Payment not found
- **AC-17** When a row reaches Payment not found (14 days, `plans-and-payment.md`), counted from the row's first receipt, it gets the *Payment not found* label, the parent is sent the Payment not found email, and the row shows the *Not found line*.
- **AC-18** The row stays on Verify, and all its buttons still work.

## Close receipt
For a receipt that will never be confirmed: the parent hasn't paid yet, sent the wrong receipt, or the payment was never found.
- **AC-19** Each Verify row has a *Close receipt button*. It opens a dialog (PT-42 to PT-45) titled *Close title*.
- **AC-28** Admin picks one reason from a choice list (PT-46, PT-47): *Not paid yet*, *Wrong receipt*, *Not found reason* or *Other*. At first none is picked, except on a row labelled Payment not found, where that reason starts picked.
- **AC-29** The dialog says what will happen (*Close explainer*). The *Close confirm button* is off until a reason is picked.
- **AC-31** Closing the dialog without pressing the button does nothing.
- **AC-30** Pressing the button takes the row off Verify: the row becomes the *Closed line*, with Undo for 10 seconds (PT-16 to PT-26). Nothing is emailed to the parent.
- **AC-20** When the 10 seconds are over, the receipt no longer counts as sent, and the parent's page follows "Closed receipt" in `plans-and-payment.md`. An undone Close changes nothing for the family.

## Emails that didn't arrive
- **AC-21** A Problem email or a Payment not found email that didn't arrive shows on its row (PT-30 to PT-34).
- **AC-22** An activation email that didn't arrive puts the payment in a section at the top of the Activate tab, under *Didn't arrive heading*. Each entry shows the payment code, the child's first name, the address, the *Activated date*, Resend (PT-32, PT-33) and Mark sorted. Mark sorted takes the entry away, with Undo for 10 seconds.
- **AC-23** The section shows only when it has entries.

---

## Layout
- **AC-24** Verify, from 1024 px up: the Payment not found label sits with the other labels; Problem lines and earlier receipts sit under the row, across the full width; Problem with this payment and Close receipt go in Actions, after Confirm.
- **AC-25** Verify, below 1024 px: Problem lines, then earlier receipts, come after the transaction line. The buttons go Confirm (filled) · Problem with this payment · (part 3's Refund instead) · Close receipt.
- **AC-26** Keyboard order follows the card order: earlier receipts' View receipt comes after the row's own View receipt; Resend (when shown) comes last.

## Action log
- **AC-27** Problem email sent (with the reason), Close receipt (with the reason), Mark sorted, Resend and every Undo each write one entry (PT-52).

---

## Words on screen
`{code}`, `{email}`, `{date}`, `{time}` and `{n}` as in part 1. `{reason}` is the reason's own words below.

| Name | Words | Example |
|---|---|---|
| Problem button | Problem with this payment | |
| Problem title | Problem with {code} | Problem with #1601319 |
| Wrong amount | Wrong amount | |
| Code not found | Code not found | |
| Receipt unclear | Receipt unclear | |
| Possible double payment | Possible double payment | |
| Note counter | {n} / 300 | 0 / 300 |
| Too long | Too long by {n} | Too long by 12 |
| Pick a reason | Pick a reason to see the email. | |
| Send button | Send to {email} | |
| Problem line | Problem email sent: {reason} · {date}, {time} | Problem email sent: Receipt unclear · 10 Oct, 9:14pm |
| Send failed | Couldn't send. Check your internet and try again. | |
| New receipt line | New receipt · {date}, {time} | New receipt · 11 Oct, 8:02am |
| Earlier receipts | Earlier receipts | |
| Payment not found | Payment not found | |
| Not found line | Payment not found email sent · {date} | Payment not found email sent · 24 Oct |
| Close receipt button | Close receipt | |
| Close title | Close the receipt for {code} | Close the receipt for #1601319 |
| Not paid yet | Not paid yet | |
| Wrong receipt | Wrong receipt | |
| Not found reason | Payment not found | |
| Other | Other | |
| Close explainer | This receipt will stop counting as sent. The parent's page will ask for a new one. Nothing is emailed. | |
| Close confirm button | Close receipt | |
| Closed line | {code} receipt closed · {reason} | #1601319 receipt closed · Wrong receipt |
| Mark sorted button | Mark sorted | |
| Sorted line | {code} marked sorted | |
| Didn't arrive heading | Emails that didn't arrive | |
| Activated date | Activated {date} | Activated 10 Oct |

## Content for testing
| What | Test value |
|---|---|
| One row with everything | the part 1 labels plus Payment not found, 3 Problem lines, 2 earlier receipts and Email didn't arrive |
| Note | exactly 300 characters; 301 characters; pasted text of 1,000 characters |
| Receipt email | a mistyped address that bounces, and an account email that is different |

## Worked examples
| What happens | Result |
|---|---|
| After a Receipt unclear email, the parent sends a clearer screenshot of the same payment | Same row, at the top once the list updates, with the new receipt line; no Receipt already used label |
| A row is still on Verify 14 days after its first receipt | Payment not found label; the parent is emailed; the row stays |
| An activation email bounces | The payment shows under "Emails that didn't arrive" with Resend; the plan stays active (PT-34) |
| Admin types a note, closes the dialog by mistake, then opens it again | The reason and note are still there |
| The parent says they haven't paid yet. Admin taps Close receipt, picks Not paid yet, and doesn't undo | After 10 seconds the receipt stops counting. If the trial is over, the child's tasks pause and the parent's page shows the pay page with "We couldn't match your receipt…" |
| Admin closes a receipt, then taps Undo after 5 seconds | The row is back on Verify as it was; nothing changed for the family |
| That parent pays the next day and sends a new receipt | A new row on Verify (AC-16) |

## Open questions
None. (OQ-2 settled by the owner, 2026-10-11: Close receipt, see `specs/decisions/verify-activate.md`.)
