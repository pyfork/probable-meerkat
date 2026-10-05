# Brief: Plans and payment

<!-- project-lead-Opus5.5-agent, 2026-10-05. DRAFT for the owner's re-approval. Split out of the writing and spelling briefs (owner, 2026-10-04: one fact, one place).
     Decisions: specs/decisions/plans-and-payment.md. -->

Words follow `specs/glossary.md`. Rules for every page are in `site-rules.md`. Admin's screens for payments are in `admin-page.md`.

## Who it's for
Parents who try and then pay for Writing Confidence, Spelling Confidence or both, and Admin who checks the payments.

## The problem
Parents pay by DuitNow QR transfer. The bank gives no automatic confirmation, so every payment has to be matched by hand, quickly and without mistakes.

## What should happen

### Plans and prices
| Plan | Price | Length | Includes |
|---|---|---|---|
| Writing Confidence | RM59 | 12 months | Writing Confidence and Spelling Confidence |
| Writing Confidence | RM45 | 6 months | Writing Confidence only |
| Spelling Confidence | RM39 | 12 months | Spelling Confidence only |
| Spelling Confidence | RM29 | 6 months | Spelling Confidence only |
| Spelling Confidence | RM11 | 1 month | Spelling Confidence only |

- No plan renews by itself.
- A parent can pay from day 1 of a trial. Paying early doesn't shorten the trial. The plan starts on the day Admin activates it.

### Free trials
- **Writing Confidence:** up to 3 days, starting at sign-up. The child gets 2 sets a day. The trial sets are fixed: the same 2 sets for every trial user, every day, kept separate from the paid sets so a paying child never redoes them. Feedback is still written for every trial answer.
- **Spelling Confidence:** 3 rounds, 2 in Fun mode and 1 in Exam mode, with no sign-up. The rounds are fixed: the same 24 words for every trial user, every day. They mix word list 1 and word list 2 at 30 : 70 (2 or 3 list 1 words a round). The trial has the full round: help in Fun mode, the bonus round, marking and the debrief with Listen. Nothing is remembered for the child during the trial (no boxes).
- Clearing cookies, a new browser, a new email or a VPN gives nothing new, so there is no reason to cheat a trial.

### Paying
- The pay page shows a short how-to guide: save or scan the DuitNow QR, pick a plan and pay its price to KIP ADVISORS, type your own payment code in the bank's Reference box, then screenshot the receipt.
- Each parent gets their own payment code: # and 6 digits, counting up from #160131. It shows on the pay page with a Copy button. If a bank won't accept the #, the parent types just the digits.
- The parent sends the receipt form: **what they are paying for** (the plan), the screenshot, the transaction number, their name, their email, and a WhatsApp number (optional).
- The email field starts filled with the parent's account email. The form and the "Payment receipt received" screen both name it: "we'll send your subscription activation to {email}". If the parent changes the field, the named email changes with it.
- One payment activates one plan for one child.
- The receipt screenshot alone never verifies a payment, because a screenshot can be edited. Admin checks the bank's list.
- Receipts are private. Only Admin can see them.

### Checking and activating
- Admin verifies each payment by finding its payment code in the bank's transactions list, then activates the plan (see `admin-page.md`).
- When a plan is activated, the parent sees "Subscription activated" with the plan, start date, end date, amount paid and payment code, and gets an email with the same details.
- Wording: standard subscription terms (Subscription activated, payment verified, start date, end date). Avoid "year" and "match".

### While a payment is being checked
- Once a receipt is sent, the child can keep going for up to 2 days after the trial ends.
- If those 2 days pass before activation, the child's tasks pause. The parent sees that the payment is still being checked and the activation will be sent to their email.
- Without a receipt, the child's tasks pause when the trial ends, and the parent sees the pay page.
- Nothing the child did is ever lost.

### Plan dates
- A plan starts on the day it is activated and ends on the day before the same date at the end of its length, at midnight Malaysia time.
- If that date doesn't exist in the end month, the plan ends on that month's last day.
- If a trial or plan ends in the middle of a set or round, the child can finish the task they are on. Then tasks pause.

### Payment problems
- **Possible double payment:** the same plan for the same child paid again while it is active or waiting. Admin checks with the parent first, because a second payment is often a second product or an early renewal. If it really is a double payment, the extra amount is refunded in full, with no 5% charge.
- **Wrong amount, code not found, or receipt unclear:** Admin sends a "Problem with this payment" email with the reason and an optional note. The parent's receipt form opens again. The 2 extra days still count from the first receipt.

### Cancelling and refunds
- Follows the Consumer Protection Act 1999 (s.17). A blanket "no refunds" term is not allowed.
- A parent can cancel at any time, through Report an issue.
- Plan months run from the activation date (month 1 = activation day to the day before the same date next month). A started month counts as used, even on its first day.
- **Refund = plan price × full months left ÷ plan months − 5% of the plan price**, rounded to the nearest sen, never below RM0.
- The child can keep going until the end of the month already used.
- The refund is paid within 30 days of the cancellation.
- Admin's screens for this are in `admin-page.md` (Cancel plan, Refunds to pay).

### Terms of Subscription page
- Linked from the pay page ("By sending your receipt, you agree to the Terms of Subscription"), the Support page and the footer.
- Covers: who we are (Kip Advisors, registration numbers, business address, from the owner's private notes), what the parent gets, the free trials, plans and prices, cancellation and refunds with a month-by-month refund table, using the service, AI-written feedback, the child's work and personal data, reviews, changes, the parent's rights and disputes, and how to contact us (the Report an issue form and the support email; no phone number).
- A Bahasa Malaysia version sits beside the English one.
- A Privacy Notice in Bahasa Malaysia and English (Personal Data Protection Act 2010), with the parent's consent for their child's data.
- A Malaysian lawyer checks the Terms and the Privacy Notice before launch.

## Worked examples

**Plan dates**
| Activated | Plan | Last day |
|---|---|---|
| 5 Oct 2026 | 12 months | 4 Oct 2027 |
| 5 Oct 2026 | 6 months | 4 Apr 2027 |
| 5 Oct 2026 | 1 month | 4 Nov 2026 |
| 1 Jan 2027 | 12 months | 31 Dec 2027 |
| 31 Jan 2027 | 1 month | 28 Feb 2027 |
| 29 Feb 2028 | 12 months | 28 Feb 2029 |

**Refunds**
| Plan | Activated | Cancel asked | Month now in | Full months left | Refund | Child can go on until | Pay by |
|---|---|---|---|---|---|---|---|
| RM59, 12 months | 5 Oct 2026 | 20 Dec 2026 | 3 | 9 | RM59 × 9 ÷ 12 − RM2.95 = **RM41.30** | 4 Jan 2027 | 19 Jan 2027 |
| RM45, 6 months | 5 Oct 2026 | 10 Nov 2026 | 2 | 4 | RM45 × 4 ÷ 6 − RM2.25 = **RM27.75** | 4 Dec 2026 | 10 Dec 2026 |
| RM29, 6 months | 5 Oct 2026 | 5 Oct 2026 | 1 | 5 | RM29 × 5 ÷ 6 − RM1.45 = **RM22.72** | 4 Nov 2026 | 4 Nov 2026 |
| RM39, 12 months | 5 Oct 2026 | 10 Sep 2027 | 12 | 0 | below RM0, so **RM0** ("No refund due") | 4 Oct 2027 | – |
| RM11, 1 month | 5 Oct 2026 | 6 Oct 2026 | 1 | 0 | **RM0** ("No refund due") | 4 Nov 2026 | – |

**Double payments**
| What happened | Label? | Result |
|---|---|---|
| RM45 writing, then RM39 spelling for the same child | No | Two plans, both activated |
| RM59 writing paid twice the same day | "Possible double payment" | Admin checks; the extra RM59 is refunded in full |
| RM59 writing paid again 2 weeks before the end date | "Possible double payment" | Admin checks; usually an early renewal, kept |

**Trial and grace**
| Day | Receipt sent? | The child can… |
|---|---|---|
| Trial days 1–3 | any | do the trial |
| Day 4 | yes (on day 2) | keep going (grace day 1) |
| Day 6 | yes, not yet activated | tasks paused; the parent sees "still being checked" |
| Day 4 | no | tasks paused; the parent sees the pay page |

## Out of scope
Card or online-banking payment (only QR transfer plus receipt for now). Renewal reminders before the end date. A payment service that confirms DuitNow payments by itself (a later gold standard).

## Open questions
None.
