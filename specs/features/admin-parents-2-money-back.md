# Spec: Admin: Parents, part 2 of 3: Money back

## Problem
The law gives a parent the right to cancel and get unused months back within 30 days, so every refund must be worked out the same way, paid to bank details only Admin sees, and never missed or paid twice.

### Concept checks
1. Does Admin type the refund amount? → No. The site works it out (AC-7).
2. Can Admin change the date the parent asked? → Yes, from the activation day to today (AC-4).
3. A parent cancels on the first day of month 3. Does month 3 count as used? → Yes (AC-6, `plans-and-payment.md`).
4. Does cancelling the RM59 plan end Spelling too? → Yes, with one refund (AC-10).
5. Can Cancel plan be undone? → Yes, for 30 seconds. The email waits until then (AC-13).
6. A renewal is activated but hasn't started. Is its refund in full, or minus 5%? → ? (decide: OQ-1)
7. Do the 30 days to pay start when the plan is cancelled? → No. When the bank details arrive (AC-19).
8. Can Admin mark a refund paid without the bank transfer reference? → No (AC-27).
9. Are the bank details kept after the refund is sent? → No. They are deleted (AC-30).
10. The parent is signed in on the child's phone. Does the bank-details form still ask for a code? → Yes, every time, so a child can't fill it in (AC-37).
11. Can a parent change their bank details after sending them? → Yes, until the refund is sent. The pay-by date doesn't move (AC-44).

## Goals and non-goals
1. **Goals**
   - Admin cancels a plan from the family page and sees the refund worked out before confirming.
   - Every refund, from any tab, waits in one list until it is paid, with its pay-by date.
   - Overdue refunds can't be missed.
   - The parent gives bank details once, privately, and they are gone once the refund is sent.
2. **Non-goals**
   - Refunds from Verify and Activate (extra money, Refund instead): they are created there (Verify and Activate part 3) and paid here.
   - Paying refunds from the site. Admin pays from the bank app, by hand.
   - Daily to-do email reminders for refunds (area 6).
   - Cancelling from the parent page. Parents cancel through Report an issue (`plans-and-payment.md`).

<!-- ux-designer-Opus5.5-agent, 2026-10-11. DRAFT for the owner. Part 2 of the rules for the Parents tab of the approved brief
     specs/features/admin-page.md. Part 1: admin-parents-1-find-a-family.md. Part 3: admin-parents-3-delete-and-copy.md.
     Shared rules (PT-n): specs/patterns.md. Decisions: specs/decisions/admin-parents.md. -->

Words follow `specs/glossary.md`. Money rules: `plans-and-payment.md` (Cancelling and refunds). Words in *italics* are on-screen words from the table at the end. "Part 1, AC-n" means a rule in `admin-parents-1-find-a-family.md`; "VA part 3, AC-n" a rule in `verify-activate-3-money-that-doesnt-match.md`; "sign-in part 1, AC-n" a rule in `sign-in-1-parents.md`.

## Patterns used
The same as part 1, plus Choice list (PT-46, PT-47) and Email code (PT-53 to PT-66) on the bank-details form.

---

## Cancel plan
- **AC-1** *Cancel plan* shows on each active plan on the family page, and on an activated plan that hasn't started yet (a renewal).
- **AC-2** A waiting plan has no Cancel plan. Money back before activation is Refund instead, on Verify or Activate (VA part 3, AC-11).
- **AC-3** Cancel plan opens a dialog (PT-42 to PT-45) titled *Cancel title*.
- **AC-4** It first shows *Date asked*: a date box set to today. Admin can pick any day from the plan's activation day to today. Any other day shows *Date range*, and the figures don't change.
- **AC-5** Then it shows the figures, each on its own line: the plan and the price paid, the activation date, the month now in, the full months left, the refund with its working (*Refund working*), the last day the child can go on, and *Pay by line*.
- **AC-6** The figures follow `plans-and-payment.md` (plan months, the formula, rounding, the price the plan was bought at). They change as soon as Date asked changes.
- **AC-7** Nobody types an amount. A refund never adds up to more than the money recorded for that plan (VA part 3, AC-16).
- **AC-8** A refund of RM0 shows *No refund due*, and no Pay by line.
- **AC-9** If the last day the child can go on is already past (Date asked is far back), the line reads *Ends now*.
- **AC-10** For the RM59 plan, the dialog shows *Both products*.
- **AC-11** If the family has a renewal waiting to start after this plan, the dialog shows *Renewal note*. Cancelling this plan leaves the renewal as it is.
- **AC-12** The button reads *Cancel button*, with the account email.
- **AC-13** Pressing it closes the dialog. The plan becomes the *Cancelled line* with Undo for 30 seconds, and the email is held (PT-16 to PT-26).
- **AC-14** When the 30 seconds are over, the plan is cancelled. The parent gets the *Plan cancelled* email with the same figures, and, when a refund is due, the bank-details link (AC-33).
- **AC-15** The child can go on until the last day, then the plan ends. With Ends now, the plan ends at once.
- **AC-16** A refund above RM0 goes on Refunds to pay, waiting for bank details.
- **AC-17** An activated renewal that hasn't started: ? (decide: OQ-1). Lean: full refund with no 5% charge, because nothing is used yet, and the child keeps the current plan.

## Refunds to pay
- **AC-18** Refunds to pay, at the top of the Parents tab (part 1, AC-1), lists every refund not yet sent: from Cancel plan, and from Verify and Activate (VA part 3, AC-10, AC-13).
- **AC-19** A refund's pay-by date is 30 days after its bank details arrive (`plans-and-payment.md`).
- **AC-20** Order: overdue refunds first, then by pay-by date, soonest first, then refunds waiting for bank details, oldest first.
- **AC-21** Each row shows: the payment code, the amount, why (*Refund reasons*), the account email, the parent's name from the receipt, and the bank details or the *Waiting line*.
- **AC-22** Bank details show the bank, the account name and the account number, with *Copy* beside the number.
- **AC-23** A refund that has bank details shows the *Pay by* date. The day after it, the row carries *Overdue* (PT-48: words, a warning icon and red).
- **AC-24** A row waiting for bank details shows *Resend link*. It sends the bank-details link again, choosing the address as PT-32 does, and shows the Resent line (PT-33).
- **AC-25** With no refunds to pay, the list shows *No refunds* (PT-40).
- **AC-26** *Mark refunded* shows on rows with bank details. It opens a dialog titled *Mark title*, showing the amount and the bank details again, so Admin can check them against the bank app.
- **AC-27** The dialog has one box, *Reference box*: 1 to 40 letters, numbers, spaces or dashes. *Mark button* stays off until the box holds a reference.
- **AC-28** Pressing it closes the dialog. The row becomes the *Refunded line* with Undo for 30 seconds, and the email is held (PT-16 to PT-26).
- **AC-29** When the 30 seconds are over, the parent gets the *Refund sent* email with the amount and the reference.
- **AC-30** At the same moment the bank details are deleted for good. Undo before then brings the row back with them.
- **AC-31** The family's Payments (part 1, AC-30) shows each refund's state: *Waiting for bank details*, *To pay by*, or *Refunded*.
- **AC-32** A refund from a test family carries the Test family label.

## Bank-details form (for the parent)
- **AC-33** Every email that tells a parent a refund is coming (Plan cancelled here; Wrong amount with too much and Refund instead in VA part 3) holds a link to that refund's bank-details form.
- **AC-34** The link opens a page titled *Bank title*. Opening the link alone changes nothing.
- **AC-35** The link works until the refund is marked sent. After that, its page shows *Already sent*.
- **AC-36** The page first names the email the link went to (*Code to*) with *Send code*. The code screen follows Email code (PT-53 to PT-66).
- **AC-37** The code is asked for every time, even when the device is signed in, because the parent's phone is often the child's.
- **AC-38** After the right code, the page shows the refund (*Refund summary*) and three boxes: Bank, Account name, Account number.
- **AC-39** Bank is a choice list (PT-46, PT-47) of Malaysian banks that take DuitNow transfers, kept as a setting on the server, then *Other bank*, which opens a box for the bank's name.
- **AC-40** Account name takes 2 to 100 characters, as on the bank account.
- **AC-41** Account number takes 6 to 20 digits. Spaces and dashes are ignored.
- **AC-42** *Send details* always works when pressed. A missing or wrong box shows its message under it (*Bank needed*, *Name needed*, *Number needed*), and focus goes to the first one. What was typed stays.
- **AC-43** Sending shows *Thanks*, with the amount, the last 4 digits of the account number and the pay-by date (AC-19). The refund moves up Admin's list (List changed bar, PT-14).
- **AC-44** Opening the link again (after a new code) shows the details sent, with *Change details*. A change replaces them. The pay-by date doesn't move.
- **AC-45** If sending can't reach the server: PT-36. What was typed stays.
- **AC-46** The bank-details form is laid out like the sign-in screens (sign-in part 1, AC-42 to AC-45): one column, the main button under its boxes, and the footer.
- **AC-47** Only Admin can see bank details (`plans-and-payment.md`). They are never in an email, and only the last 4 digits are ever shown back to the parent.

---

## Layout
- **AC-48** From 1024 px up, Refunds to pay is a table with these columns in order: Payment code (with labels) · Amount and why · Parent · Bank details · Pay by · Actions.
- **AC-49** Below 1024 px, each refund is a card (PT-6 to PT-11) in this order: payment code · labels · amount and why · pay by · bank details · parent · Mark refunded (filled) or Resend link. The amount and the date matter most on a phone.
- **AC-50** In the Cancel plan dialog, each figure is a label then its value on one line from 480 px up, and the value goes under its label below 480 px. The refund line is in the largest text.

## Action log
- **AC-51** Cancel plan (with Date asked and the refund), Mark refunded (with the amount and reference), Resend link and every Undo each write one entry (PT-52). Bank details arriving or changing write an entry with "parent" as who, without the details.

---

## Words on screen
`{code}` is a payment code, `{email}` an email, `{amount}` money (PT-51), `{n}` a number, `{date}` follows PT-50.

| Name | Words | Example |
|---|---|---|
| Cancel plan | Cancel plan | |
| Cancel title | Cancel {product} {code} | Cancel Writing Confidence #1601319 |
| Date asked | Date the parent asked | |
| Date range | Pick a day from {date} to today. | Pick a day from 5 Oct 2026 to today. |
| Month now in | Month now in: {n} of {months} (counts as used) | Month now in: 3 of 12 (counts as used) |
| Full months left | Full months left: {n} | |
| Refund working | Refund: {price} × {left} ÷ {months} − {five} = {amount} | Refund: RM59.00 × 9 ÷ 12 − RM2.95 = RM41.30 |
| No refund due | No refund due | |
| Last day | Child can go on until {date} | Child can go on until 4 Jan 2027 |
| Ends now | Ends now. The last day, {date}, has passed. | |
| Pay by line | Pay by: 30 days after the bank details arrive | |
| Both products | This ends Writing Confidence and Spelling Confidence. | |
| Renewal note | A renewal starts on {date}. Cancel it on its own if the parent asked. | |
| Cancel button | Cancel plan and email {email} | |
| Cancelled line | {code} cancelled · {amount} to refund | #1601319 cancelled · RM41.30 to refund |
| Refunds to pay | Refunds to pay | |
| No refunds | No refunds to pay. | |
| Waiting line | Waiting for bank details · link sent {date} | |
| Resend link | Resend link | |
| Copy | Copy | |
| Pay by | Pay by {date} | Pay by 19 Jan 2027 |
| Overdue | Overdue since {date} | |
| Mark refunded | Mark refunded | |
| Mark title | Mark {code} refunded | |
| Reference box | Bank transfer reference | |
| Mark button | Mark refunded and email {email} | |
| Refunded line | {code} · {amount} refunded · ref {reference} | #1601319 · RM41.30 refunded · ref MB2701190042 |
| Waiting for bank details | Refund {amount} · waiting for bank details | |
| To pay by | Refund {amount} · to pay by {date} | |
| Refunded | Refunded {amount} on {date} · ref {reference} | |
| Bank title | Bank details for your refund | |
| Code to | We'll send a code to {email} to check it's you. | |
| Send code | Send code | |
| Refund summary | Refund of {amount} for {code} | Refund of RM41.30 for #1601319 |
| Bank | Bank | |
| Other bank | Other bank | |
| Account name | Name on the bank account | |
| Account number | Account number | |
| Send details | Send details | |
| Bank needed | Pick your bank | |
| Name needed | Type the name on the account | |
| Number needed | Type 6 to 20 digits | |
| Thanks | Thank you. We'll pay {amount} to the account ending {last 4} by {date}. | Thank you. We'll pay RM41.30 to the account ending 0042 by 19 Jan 2027. |
| Change details | Change details | |
| Already sent | This refund was sent on {date}. | |

### Refund reasons
| From | Words |
|---|---|
| Cancel plan | Cancelled plan |
| Wrong amount, too much (VA part 3) | Paid too much |
| Refund instead (VA part 3) | Refunded instead |

### Emails
| Name | Subject | What it says |
|---|---|---|
| Plan cancelled | {code} Your plan is cancelled | The plan, the date asked, the last day your child can go on, and the refund with its working, or "No refund due". When a refund is due: "Send your bank details here (link). We'll pay within 30 days of receiving them." |
| Refund sent | {code} Your refund is on its way | We've sent {amount} to your bank account. Bank transfer reference: {reference}. |

## Content for testing
| What | Test value |
|---|---|
| Refunds | Every row of the Refunds table in `plans-and-payment.md` |
| Biggest refund | RM5,900.00 (VA part 3's biggest amount, refunded instead) |
| Long account name | NUR AISYAH HUMAIRA BINTI SYED KHAIRUL ANUAR |
| Account numbers | 5140 1234 0042, 514-012-340-042, 12345 (too short), a 21-digit number |
| References | MB2701190042, a 40-character reference, an empty box |
| List sizes | 0 refunds, 1 overdue, 3 waiting for bank details, 30 refunds |
| Screen sizes | 320 × 568, 667 × 375, 390, 768 and 1280 px wide, large text on |

## Worked examples
| What happens | Result |
|---|---|
| RM59 plan activated 5 Oct 2026; the parent asked on 20 Dec; Admin cancels on 22 Dec with Date asked 20 Dec | Month 3 of 12; 9 full months left; RM41.30; the child can go on until 4 Jan 2027. After 30 seconds the email goes with the bank-details link |
| The parent sends bank details on 23 Dec | The refund shows Pay by 22 Jan 2027 and moves up the list |
| Nobody pays by 22 Jan | From 23 Jan the row carries Overdue |
| Admin pays from the bank app and marks it refunded with MB2701190042 | After 30 seconds the parent gets Refund sent; the bank details are deleted |
| RM11 plan cancelled the day after activation | No refund due; nothing goes on Refunds to pay |
| Admin processes a request from 20 Dec only on 6 Jan | Ends now: the last day, 4 Jan, has passed. The plan ends when the Undo is over |
| A RM59 renewal (starts 5 Oct 2027) is cancelled on 1 Oct 2027 | OQ-1. Lean: RM59.00 in full; the current plan runs to 4 Oct 2027 |

## Open questions
- **OQ-1** A renewal that is activated but hasn't started is cancelled. Lean: refund it in full with no 5% charge, as for cancelling before activation, because nothing is used yet. The other way: treat it like any active plan (all months left, minus 5%).
