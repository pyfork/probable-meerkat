# Decisions: Admin: Parents

<!-- ux-designer-Opus5.5-agent, 2026-10-11. History only. Build from specs/features/admin-parents-1-find-a-family.md,
     admin-parents-2-money-back.md, admin-parents-3-delete-and-copy.md and specs/patterns.md. -->

- Split into three parts by what Admin is doing: part 1 Find a family (search, the family page, placement, codes, resend, move email), part 2 Money back (Cancel plan, Refunds to pay, the parent's bank-details form), part 3 Delete and copy (Deletion requested, Delete this family, Download family data). All three are launch day.
- Choices where the brief was loose (told the owner, 2026-10-11):
  - The Parents tab opens on the two deadline lists, then the search; it never lists every family. Its tab count is refunds that can be paid now plus deletions requested.
  - Search runs on Enter, not while typing. Emails match anywhere, the child's name from the start, payment codes in full (with or without #) or by their first 6 digits. The family page's web address holds a number, never an email or a name.
  - The family page also lists the emails sent to the family (with Didn't arrive and Resend) and links to the Log. Admin can change the child's first name (the parent's right to correct their data; the email is corrected with Move).
  - Reset code limit clears both the account and backup email's counts; no Undo, since it sends nothing and harms nothing.
  - Move to a new email shows the payment codes, bank transaction numbers and child's name to check, needs a verified payment, changes at once with a 30-second Undo, and keeps signed-in devices signed in. A family with no payment signs up again instead.
  - The refund bank-details form is designed here, because Refunds to pay can't work without it. It asks for a fresh email code every time, even on a signed-in phone. Changing the details doesn't move the pay-by date. Only the last 4 digits are ever shown back to the parent.
  - Pay-by dates count 30 days from when the bank details arrive (as settled 2026-10-05), so Cancel plan shows "30 days after the bank details arrive" instead of a date.
  - Delete this family is on every family page (requests also come by email or Report an issue), and is off while a payment waits on Verify or Activate. A refund still owed survives the deletion as a payment record. Searching a deleted family's payment code finds its payment records only.
  - Download family data is one PDF; the site emails nothing, Admin replies from the inbox with it.
- **OQ-1, cancelling a renewal that hasn't started (owner gwl, 2026-10-11):** refunded in full, with no 5% charge, as for cancelling before activation, because nothing is used yet. Changes the approved `plans-and-payment.md`.
- **OQ-2, deleting a family with paid months left (owner gwl, 2026-10-11):** deleting cancels each plan on the date the parent asked, with the usual refund and the Plan cancelled email. The refund stays on Refunds to pay after the family is gone, as a payment record.
- **OQ-3, placement in a copy of a family's data (owner gwl, 2026-10-11):** left out, because no level is ever shown to a parent. Added to the lawyer's pre-launch checks.
