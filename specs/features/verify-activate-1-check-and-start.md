# Spec: Verify and Activate, part 1 of 3: Check and start

## Problem
The bank doesn't tell us who paid, so Admin matches each payment by hand and starts the child's plan, often on a phone beside the bank app, where one wrong tap could confirm the wrong payment or email the wrong parent.

### Concept checks
1. Does the bank tell us who paid? → No.
2. Who decides which payment a receipt belongs to: the site or Admin? → Admin (AC-16).
3. Is Admin usually at a desk with a big screen? → No. Often a phone, or half a laptop screen (AC-45, AC-48).
4. Admin taps Confirm. Is the parent emailed? → No (AC-13).
5. Admin activates the wrong row and taps Undo after 10 seconds. Has the parent been emailed? → No (AC-31, PT-18).
6. Can Admin undo once the parent has been emailed? → No (AC-33).
7. Admin closes the page during the 30 seconds. Does the activation still happen? → Yes (PT-19).
8. What do we record: the plan price, or the amount Admin saw in the bank? → The amount seen (AC-10).
9. Can one payment start plans for two children? → No. One payment, one plan, one child (`plans-and-payment.md`).
10. A parent paid too little. Does part 1 handle it? → No. Part 3 does.
11. A new receipt arrives while Admin is about to tap. Does the list move? → No (PT-12).

## Goals and non-goals
1. **Goals**
   - Admin can confirm a correct payment in a few taps, on a phone beside the bank app.
   - Every payment is recorded with the amount Admin saw in the bank.
   - Any Confirm or Activate can be undone before the parent is told.
   - The parent gets the activation email with the right dates, even if Admin closes the page.
   - Several verified payments can be activated in one go.
2. **Non-goals**
   - Payments that go wrong: problem emails, re-sent receipts, Payment not found, Close receipt, emails that didn't arrive (part 2).
   - Money that doesn't match the plan: too little, too much, refunds (part 3). Parts 2 and 3 add their lines and buttons to the rows and layouts set out here.
   - The parent's screens: the pay page, the receipt form, "Subscription activated" (`plans-and-payment.md`).
   - The daily to-do email, the Log page, the Parents tab and the Refunds to pay list (their own specs).
   - Test families beyond their label (their own spec).
   - Any automatic check with the bank. Admin always checks by hand (`plans-and-payment.md`, out of scope).
   - More than one Admin login (`admin-page.md`, out of scope).

<!-- ux-designer-Opus5.5-agent, 2026-10-10. DRAFT for the owner. Part 1 of the rules for the Verify and Activate tabs of the approved
     brief specs/features/admin-page.md. Part 2: verify-activate-2-when-something-is-wrong.md. Part 3: verify-activate-3-money-that-doesnt-match.md.
     Shared rules (PT-n): specs/patterns.md. Decisions: specs/decisions/verify-activate.md. -->

Words follow `specs/glossary.md`. The brief: `admin-page.md`. Payment rules: `plans-and-payment.md`. Admin sign-in and the action log: `accounts-and-sign-in.md`. Rules for every page: `site-rules.md`. Words in *italics* are on-screen words from the table at the end.

## Patterns used
Both tabs use: Admin tabs (PT-1 to PT-5), Row becomes a card (PT-6 to PT-11), Lists move only when Admin asks (PT-12 to PT-15), Undo in place (PT-16 to PT-26), Buttons that change something (PT-35 to PT-38), List states (PT-39 to PT-41), Labels on a row (PT-48, PT-49), Times and money (PT-50, PT-51) and the Action log (PT-52).

---

## Verify tab

### The list
- **AC-1** Verify lists every receipt waiting to be checked, one row per payment, newest first by the time its newest receipt was sent. With no rows it shows *Verify empty* (PT-40).

### What each row shows
- **AC-2** The payment code first, in the largest text on the row.
- **AC-3** The plan and its amount, the child's first name, the parent's name, the email from the receipt form, and the WhatsApp number or *No WhatsApp*.
- **AC-4** The bank transaction number, and when the receipt was sent (*Sent time*).
- **AC-5** *View receipt*, which opens the receipt viewer (AC-17 to AC-22).
- **AC-6** *Copy* beside the payment code copies its 7 digits without the "#", so Admin can paste them into the browser's Find (Cmd+F or Ctrl+F) on the bank's transactions page. A bank may show the code with or without the "#", and the digits find both. The button then shows *Copied* for 2 seconds, and a screen reader hears *Copied, read out*. If the phone doesn't allow copying, the code is selected so Admin can copy it by hand.

### Labels
- **AC-7** *Receipt already used* shows when the row's bank transaction number is on a receipt in another row.
- **AC-8** *Possible double payment* shows when the same plan for the same child is already active or waiting in another row (`plans-and-payment.md`).
- **AC-9** *Test family* shows on rows from a test family.

### Recording the money
- **AC-10** Each receipt on a row holds at most one recorded amount: what Admin saw in the bank for that transfer. The plan price is never recorded as received by itself.
- **AC-11** The amount Confirm expects is the plan price minus the amounts recorded on the row's earlier receipts. (Earlier receipts arrive in part 2, top-ups in part 3. Until then it is the plan price.)
- **AC-12** Each row has a *Confirm button* that names the payment code and that amount. A tap on the wrong row is easy to spot, a screen reader knows which payment it is, and pressing it means "I saw this amount in the bank".
- **AC-13** Confirm records that amount on the row's newest receipt, replacing any amount there before. It marks the payment as verified and moves it to Activate. Nothing is sent to the parent.
- **AC-14** After Confirm, the row becomes the *Confirmed line*, with Undo for 10 seconds.
- **AC-15** Undo puts the row back as it was: not verified, with the amounts it had before.
- **AC-16** Confirm works on every row, whatever its labels. Admin decides after checking the bank.

### Receipt viewer
- **AC-17** View receipt opens the picture in a dialog (PT-42 to PT-45) titled *Receipt title*. The payment code and the transaction number show above the picture, so Admin can compare without closing it.
- **AC-18** At first the picture fits the viewer. On a touch screen, pinching zooms it. On a computer, *Full size* shows it at its real size, and the picture may then scroll sideways inside the viewer. *Named exception:* shrinking a receipt makes its numbers unreadable, so it scrolls instead.
- **AC-19** A PDF receipt opens in a new browser tab.
- **AC-20** Each time a receipt opens, the page asks for a fresh private link (`site-rules.md`), so a page left open for hours still opens receipts.
- **AC-21** While the picture loads, the viewer shows *Receipt loading*. If it can't load, it shows *Receipt failed* with Try again.
- **AC-22** A file the browser can't show gets *Receipt can't show* with Download.

---

## Activate tab

### The list
- **AC-23** Activate lists every verified payment that isn't activated yet, one row per payment, newest verified first. With no rows it shows *Activate empty* (PT-40).

### What each row shows
- **AC-24** The payment code first, in the largest text. Then the plan and its amount, the child's first name and the parent's name.
- **AC-25** *Activation email line*, with the email from the receipt form.
- **AC-26** When it was verified (*Verified time*).
- **AC-27** *Plan dates* for activating today (plan dates: `plans-and-payment.md`). If the Malaysia-time day changes while the page is open, they change to match.
- **AC-28** If the plan is an early renewal (`plans-and-payment.md`), the row is labelled *Renewal* and its plan dates follow the renewal rule.
- **AC-29** *Test family* and *Possible double payment* still show.

### Activate one payment
- **AC-30** Each row has an *Activate button* that names its payment code.
- **AC-31** After Activate, the row becomes the *Activating line*, with Undo for 30 seconds and the email held.
- **AC-32** During those 30 seconds nothing changes for the parent or the child. The plan is still waiting.
- **AC-33** When the 30 seconds are over, the activation is final: the plan starts, the parent gets the activation email (`plans-and-payment.md`), and the line becomes the *Activated line*.
- **AC-34** The start date is the Malaysia-time day on which Admin pressed Activate (or the renewal date), even if the 30 seconds end after midnight.

### Activate several at once
- **AC-35** Each row has a tick box named with its payment code. *Tick all*, above the list, ticks every row on screen. Each tick box can be tapped anywhere in a 44 by 44 px area.
- **AC-36** While one or more rows are ticked, the *Ticked bar* is fixed to the bottom of the screen. It is one line high at 320 px wide. The list ends with empty space as tall as the bar, so the last row can be scrolled clear of it.
- **AC-37** Activate {n} turns each ticked row into the *Activating line, several* (no Undo of its own), and the bar becomes the *Activating bar* with one Undo for all of them (PT-20).
- **AC-38** When the 30 seconds are over, each activation is final, and each parent gets their own email.
- **AC-39** If some ticked rows can't be activated (for example, already activated on another device), the others still go ahead. The rows that couldn't stay as they were, with the reason under them, and the bar becomes the *Partial bar*.
- **AC-40** While the bar shows an Undo, the tick boxes are switched off, with the *Ticks off note*. Each row's own buttons still work.
- **AC-41** A row's own Activate button acts on that row only. If the row was ticked, it leaves the ticked count.

### Send back to Verify
- **AC-42** Each row has a *Send back button*. It moves the payment back to Verify, not verified, and removes the amount recorded on its newest receipt so Admin checks it again. The row becomes the *Sent back line*, with Undo for 10 seconds. Nothing is sent to the parent.
- **AC-43** Back on Verify, the row keeps its labels, its receipts and the amounts on its earlier receipts.

---

## Layout
- **AC-44** Verify, from 1024 px up, has these columns in order: Payment code (with Copy and the labels) · Plan and amount · Child · Parent (name, email, WhatsApp) · Receipt (transaction number, sent time, View receipt) · Actions (buttons one under another, Confirm first).
- **AC-45** Verify, below 1024 px, is a card per row (PT-6 to PT-11), in this order: payment code with Copy · labels · plan and amount · child · parent's name, email, WhatsApp · transaction number, sent time, View receipt · Confirm (filled).
- **AC-46** On a narrow screen, what matters most is the payment code, the labels and Confirm. Nothing on a row is hidden behind a menu.
- **AC-47** Activate, from 1024 px up, has these columns in order: tick box · Payment code (with the labels) · Plan and amount · Child · Parent (name, activation email) · Dates (verified, start date, end date) · Actions (Activate, then Send back to Verify, one under another).
- **AC-48** Activate, below 1024 px, is a card per row, in this order: tick box and payment code on the first line · labels · plan and amount · child · parent's name · activation email · verified · start and end dates · Activate (filled) · Send back to Verify.
- **AC-49** Keyboard order within a row follows the card order. Parts 2 and 3 add their buttons and lines in the places they name.

## Action log
- **AC-50** Confirm (with the amount), Activate, Send back to Verify and every Undo each write one entry (PT-52).

---

## Words on screen
`{code}` is the payment code, `{amount}` an amount (PT-51), `{date}` and `{time}` follow PT-50, `{n}` a number of rows, `{s}` the seconds left.

| Name | Words | Example |
|---|---|---|
| Verify empty | No receipts to check. | |
| No WhatsApp | WhatsApp: not given | |
| Sent time | Sent {date}, {time} | Sent 10 Oct, 9:14pm |
| View receipt | View receipt | |
| Copy | Copy | |
| Copied | Copied | |
| Copied, read out | Payment code copied | |
| Receipt already used | Receipt already used: also on {code}, {date} | Receipt already used: also on #1601327, 3 Oct |
| Possible double payment | Possible double payment: same plan as {code} | Possible double payment: same plan as #1601319 |
| Test family | Test family | |
| Confirm button | Confirm {code} · {amount} | Confirm #1601319 · RM39.00 |
| Confirmed line | {code} confirmed · now on Activate | #1601319 confirmed · now on Activate |
| Receipt title | Receipt for {code} | Receipt for #1601319 |
| Full size | Full size | |
| Receipt loading | Loading receipt… | |
| Receipt failed | Couldn't open the receipt. | |
| Receipt can't show | This file can't be shown here. | |
| Activate empty | Nothing to activate. | |
| Activation email line | Activation email goes to {email} | |
| Verified time | Verified {date}, {time} | Verified 10 Oct, 9:20pm |
| Plan dates | Start date {date} · End date {date} | Start date 10 Oct 2026 · End date 9 Oct 2027 |
| Renewal | Renewal | |
| Activate button | Activate {code} | Activate #1601319 |
| Activating line | {code} activating · email goes out in {s} s | #1601319 activating · email goes out in 27 s |
| Activated line | {code} activated · email sent | |
| Tick all | Tick all | |
| Ticked bar | {n} ticked · Activate {n} · Clear | 4 ticked · Activate 4 · Clear |
| Activating line, several | {code} activating | |
| Activating bar | {n} activating · emails go out in {s} s · Undo | 4 activating · emails go out in 27 s · Undo |
| Partial bar | {n} activating · {m} couldn't be | 3 activating · 1 couldn't be |
| Ticks off note | You can tick again when this finishes | |
| Send back button | Send back to Verify | |
| Sent back line | {code} sent back to Verify | |

## Content for testing
All names, emails and numbers are made up.

| What | Test value |
|---|---|
| Longest plan and amount | Spelling Confidence · 12 months · RM39.00 |
| Long parent's name | Sharifah Nur Aisyah Humaira binti Syed Mohd Khairul Anuar |
| Long email, no spaces | sharifah.nuraisyahhumaira.syedkhairul@yahoo.com.my |
| Long child's first name | Muhammad Aiman Haziq |
| Long bank transaction number | 20261010MBBEMYKL030OQR12345678 |
| WhatsApp | missing |
| Receipts | a tall phone screenshot (1080 × 2400), a PDF, a file that fails to load, a file the browser can't show |
| One row with every label | Receipt already used, Possible double payment, Test family, Renewal |
| List sizes | 0 rows, 1 row, 40 rows |
| Screen sizes | 320 × 568, 667 × 375 (phone turned sideways), a phone split in half with the bank app, and a 1280 px laptop screen split in half with the bank's web page (640 px each) |

## Worked examples
| What happens | Result |
|---|---|
| Admin taps Confirm #1601319 · RM39.00, then Undo after 4 seconds | Back on Verify, not verified, no amount recorded; nothing sent; the log shows Confirm, then Undo |
| Admin confirms #1601319 and closes the page after 3 seconds | It stays verified with RM39.00 recorded, and is on Activate |
| Admin activates #1601319 (12 months) at 11:59:45pm on 10 Oct 2026 | The email goes out at 12:00:15am on 11 Oct. Start date 10 Oct 2026, end date 9 Oct 2027 |
| Admin ticks 4 rows, taps Activate 4, then Undo after 10 seconds | All 4 are back on Activate, still verified, with no ticks; no emails sent |
| Admin ticks 4 rows; #1601327 was already activated on the laptop | 3 activating; #1601327 shows "Already activated on another device" (PT-37) |
| A RM59 renewal is paid on 20 Sep 2027; the current plan ends 4 Oct 2027 | The Activate row shows Renewal, start date 5 Oct 2027, end date 4 Oct 2028 |
| A new receipt arrives while Admin is about to tap Confirm on a phone | Nothing moves; the list-changed bar appears at the top (PT-14) |

## Open questions
None. (OQ-3 settled by the owner, 2026-10-11: Admin finds the code with the browser's Find, so Copy stays.)
