# Decisions: Plans and payment

<!-- project-lead-Opus5.5-agent, 2026-10-05. History only. Build from specs/features/plans-and-payment.md. "Writing Qn" = question n of the first writing brief. -->

- Pay by DuitNow QR plus receipt; owner verifies by hand. (Writing Q4, Q5, 2026-10-03)
- Plans and prices, two products, no automatic renewal. (Writing Q22, 2026-10-04)
- Writing trial 3 days, 2 fixed sets a day; spelling trial 3 fixed rounds, no sign-up. (Writing Q23, Spelling Q2–Q4, 2026-10-04)
- Up to 2 days of grace after a receipt is sent; pay from day 1. (Writing Q6, Q7, 2026-10-04)
- Refunds under CPA 1999 s.17; started month counts as used; minus 5%; never below RM0; within 30 days (was 14). (Writing Q20, Q22, 2026-10-04)
- Business details given privately; Terms page only; no phone number. (Writing Q21, 2026-10-05)
- The receipt form asks what the parent is paying for. "Possible double payment" only for the same plan paid again; refunded in full when it is a real double payment. (2026-10-05)
- "Problem with this payment" email with reason and note; the receipt form reopens. (2026-10-05)
- Plan end date: the day before the same date; the month's last day if that date doesn't exist. (2026-10-05)
- Cancelling: worked out before confirming; the child goes on until the end of the month used. (2026-10-05)
- Trial or plan ending mid-set: finish the current task, then pause. (2026-10-05)
- Spelling trial rounds mix the lists 30 : 70. Writing trial sets are separate from the paid sets. (2026-10-05)
- Writing trial = 72 hours from sign-up (owner, 2026-10-05), replacing "up to 3 days". Grace time = 48 hours after the trial ends (owner gwl, 2026-10-05).
- Senior engineer fixes (owner gwl, 2026-10-05): a bank transaction number used once ("Receipt already used"); early renewal starts the day after the current plan ends; no overlapping plans offered; each plan keeps its bought price; amounts kept in sen but always shown as RM with 2 decimals; payment codes get a Luhn check digit (7 digits, first #1601319).
