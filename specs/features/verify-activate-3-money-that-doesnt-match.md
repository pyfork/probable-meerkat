# Spec: Verify and Activate, part 3 of 3: Money that doesn't match

## Problem
Parents type the amount themselves in their bank app, so some pay too little, too much or twice, and if we record only the plan price, our records stop matching the bank and a refund could pay back money that never arrived.

### Concept checks
1. Who types the amount: the parent or the bank? → The parent.
2. What do we record: the plan price, or what reached the bank? → What reached the bank (AC-6).
3. A parent paid too little. Does the plan start? → No. They are asked for the rest (AC-7).
4. A parent paid too much. Does the plan start? → Yes, and the extra is refunded (AC-8, AC-10).
5. Does Admin type the refund amount? → No. The site works it out (AC-15).
6. Can a refund be more than what reached the bank? → No (AC-16).
7. Is there a 5% charge on these refunds? → No (AC-17).
8. Do we try to stop wrong amounts on the parent's side? → No. Ruled out by the owner.

## Goals and non-goals
1. **Goals**
   - Every transfer is recorded with the amount Admin saw in the bank.
   - A parent who paid too little is told the exact amount still to pay, and the top-up joins the same row.
   - A parent who paid too much gets the plan, and the extra back.
   - A double payment, or a parent who wants their money back before the plan starts, is refunded in full.
   - Every refund amount is worked out by the site, never typed, and never more than what arrived.
2. **Non-goals**
   - Stopping wrong amounts on the parent's side (copying the amount, "Amount you paid" on the receipt form, a QR with the price). Ruled out by the owner (`specs/decisions/verify-activate.md`).
   - Paying refunds, and the Refunds to pay list itself (Parents tab spec).
   - Cancelling an active plan and its 5% charge (Parents tab spec, `plans-and-payment.md`).
   - A payment service that checks the bank by itself (`plans-and-payment.md`, a later gold standard).

<!-- ux-designer-Opus5.5-agent, 2026-10-10. DRAFT for the owner. Part 3 of the rules for the Verify and Activate tabs of the approved
     brief specs/features/admin-page.md. Builds on part 1 (verify-activate-1-check-and-start.md) and part 2 (verify-activate-2-when-something-is-wrong.md).
     Shared rules (PT-n): specs/patterns.md. Decisions: specs/decisions/verify-activate.md (OQ-1, owner gwl 2026-10-10). -->

Words follow `specs/glossary.md`. Payment rules: `plans-and-payment.md`. Words in *italics* are on-screen words from the table at the end. "Part 1, AC-n" and "part 2, AC-n" mean rules in those parts.

## Patterns used
The same as parts 1 and 2, plus Dialog (PT-42 to PT-45).

---

## Money so far
- **AC-1** Once any money is recorded on a Verify row (part 1, AC-10), the row shows *Money so far*.

## Wrong amount
- **AC-2** Picking Wrong amount (part 2, AC-2) shows the *Amount box* (RM, up to 2 decimals). The send button stays off until the box holds an amount above RM0.00 that is different from the amount Confirm expects (part 1, AC-11).
- **AC-3** Typing the amount Confirm expects shows *Use Confirm*. Anything that isn't an amount shows *Type an amount*.
- **AC-4** **Less than expected:** the dialog shows *Short*. The email preview gives the amount received, the plan price and the amount still to pay, and asks the parent to pay the rest with the same payment code.
- **AC-5** **More than expected:** the dialog shows *Too much*. The email preview says the extra will be refunded and gives the bank-details link (the same private form a cancellation uses, `plans-and-payment.md`). The send button becomes *Send and confirm*.
- **AC-6** Sending Wrong amount records the typed amount on the row's newest receipt, replacing any amount there before.
- **AC-7** **Less than expected:** the row stays on Verify with its money so far, and the receipt form reopens (part 2, AC-9). The parent's top-up receipt joins the same row (part 2, AC-13), and Confirm then expects what is still to pay (part 1, AC-11).
- **AC-8** **More than expected:** the payment is marked as verified and moves to Activate. The row becomes the *Confirmed with extra line*, with no Undo (the email has gone). The receipt form doesn't reopen.

## Extra money on Activate
- **AC-9** An Activate row whose recorded money is more than the plan price shows the *Extra line*.
- **AC-10** When that activation is final (part 1, AC-33), the extra goes on Refunds to pay. The parent already has the bank-details link from the Wrong amount email.

## Refund instead
- **AC-11** *Refund instead* shows on every Activate row, and on Verify rows that have money recorded. It is the way to give money back for a double payment, for a parent who wants their money back before the plan starts, or for a parent who paid too little and won't top up.
- **AC-12** Refund instead starts no plan. The row becomes the *Refunding line*, with Undo for 30 seconds and the email held (PT-16 to PT-26). Nothing goes on Refunds to pay until the 30 seconds are over.
- **AC-13** When the 30 seconds are over, all the money recorded on the row goes on Refunds to pay, and the parent gets the owner's fixed wording with the amount and the bank-details link.
- **AC-14** On Verify, after Refund instead the receipt no longer counts as sent, as with Close receipt (part 2, AC-20).

## Refund amounts
- **AC-15** Every refund amount here is worked out from the amounts recorded on Verify (what really reached the bank), never from the plan price. Nobody types an amount at refund time.
- **AC-16** Refunds from one row can never add up to more than the money recorded on it.
- **AC-17** These refunds are always in full, with no 5% charge, and their 30 days to pay start when the bank details arrive (both in `plans-and-payment.md`).

---

## Layout
- **AC-18** The money so far sits under the plan and amount: in the same cell from 1024 px up, on the next line of a card below 1024 px. The extra line sits in the same place on Activate.
- **AC-19** Refund instead goes after Problem with this payment on Verify, and after Activate on Activate. It is never filled: Confirm and Activate stay the main buttons. Keyboard order follows.
- **AC-20** On a narrow screen, the money so far is among the things that matter most, with the payment code, the labels and Confirm (part 1, AC-46).

## Action log
- **AC-21** Wrong amount (with the amount), Refund instead (with the amount) and every Undo each write one entry (PT-52).

---

## Words on screen
`{code}`, `{email}` and `{amount}` as in part 1. `{received}` is the money recorded on the row, `{price}` the plan price, `{left}` what is still to pay, `{difference}` the gap between the typed amount and what Confirm expects, `{extra}` the money above the plan price.

| Name | Words | Example |
|---|---|---|
| Money so far | Received {received} of {price} · {left} to go | Received RM3.90 of RM39.00 · RM35.10 to go |
| Amount box | Amount in the bank | |
| Use Confirm | That's the expected amount. Use Confirm instead. | |
| Type an amount | Type the amount in the bank, for example 3.90. | |
| Short | {difference} short | RM35.10 short |
| Too much | {difference} too much. The plan can start, and the extra is refunded. | RM351.00 too much. The plan can start, and the extra is refunded. |
| Send and confirm | Send to {email} and confirm | |
| Confirmed with extra line | {code} confirmed · {extra} extra · now on Activate | #1601319 confirmed · RM351.00 extra · now on Activate |
| Extra line | Received {received} · extra {extra} to refund | Received RM390.00 · extra RM351.00 to refund |
| Refund instead | Refund instead | |
| Refunding line | {code} · {amount} to refund | #1601319 · RM3.90 to refund |

## Content for testing
| What | Test value |
|---|---|
| Biggest amount in the bank | RM5,900.00 (a RM59.00 plan typed as 5900) |
| Smallest amount in the bank | RM0.39 |
| Amount box input | 3.9, 3.90, RM3.90, 3,90, 0, -5, 39.001, an empty box |
| Longest money-so-far line | Received RM3.90 of RM39.00 · RM35.10 to go |

## Worked examples
| What happens | Result |
|---|---|
| The parent picked the RM39.00 plan but paid RM3.90. Admin sends Wrong amount with 3.90 | RM35.10 short. The parent is asked to pay RM35.10 more with the same payment code; the receipt form reopens; the row shows Received RM3.90 of RM39.00 · RM35.10 to go |
| That parent then pays RM35.10 and sends the receipt | Same row, new receipt. The button reads Confirm #1601319 · RM35.10. Confirm makes RM39.00 received, and the payment moves to Activate |
| The parent paid RM3.90 and wants the money back | Refund instead on Verify; after 30 seconds RM3.90 goes on Refunds to pay, and the parent gets the bank-details link |
| The parent picked RM39.00 but paid RM390.00. Admin sends Wrong amount with 390 | RM351.00 too much; Send to … and confirm. The parent is told RM351.00 will be refunded; the payment moves to Activate showing the extra; once activated, RM351.00 goes on Refunds to pay |
| The parent paid RM3.90, then topped up RM39.00 by mistake | Received RM42.90 for RM39.00. The payment moves to Activate with RM3.90 extra, refunded once activated |
| RM59.00 paid twice for the same child the same day | Admin checks with the parent, confirms the second (RM59.00 recorded), then taps Refund instead on Activate: RM59.00 goes on Refunds to pay, and no plan starts |
| Admin typed 3.90 by mistake when the bank shows RM39.00, and sent the email | Admin taps Confirm #1601319 · RM39.00: RM39.00 replaces RM3.90 and the payment moves to Activate. Admin follows up with the parent from the inbox |
