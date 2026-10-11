# Spec: Admin: Parents, part 3 of 3: Delete and copy a family's data

## Problem
The law (PDPA) lets a parent ask for a copy of their data or for it to be deleted, answered within 21 days, while payment records must be kept 7 years, so Admin needs one safe way to delete exactly the right things, and one way to hand over a full copy.

### Concept checks
1. Does a parent's deletion request delete the family by itself? → No. Admin finishes it within 21 days (AC-1, AC-2).
2. Are payment records deleted with the family? → No. They are kept 7 years (AC-14).
3. Can Delete this family be undone? → No. That is why Admin types the parent's email (AC-10).
4. Does the parent get an email once it's done? → Yes (AC-17).
5. The family still has paid months left. Is the plan cancelled with a refund? → Yes, on the date the parent asked (AC-9).
6. A refund is still waiting. Can it still be paid after the family is deleted? → Yes (AC-21).
7. Does the child's phone stay signed in after the family is deleted? → No (AC-18).
8. Can Admin delete a family that asked by email or Report instead of the parent page? → Yes (AC-6).
9. Does Download family data change anything? → No. It only writes a Log entry (AC-31).
10. Does the copy show the child's placement? → ? (decide: OQ-3)
11. Does the site email the copy to the parent? → No. Admin sends it from the inbox (AC-30).

## Goals and non-goals
1. **Goals**
   - Every deletion request is finished within 21 days, and an overdue one can't be missed.
   - Deleting removes the account and the child's work, keeps the payment records, and tells the parent.
   - A slip can't delete the wrong family.
   - Admin can make a full copy of a family's data in one file.
2. **Non-goals**
   - The parent's "Delete my account and data" button and its email code (area 10, the parent page).
   - A parent taking back a deletion request (area 10).
   - Clearing test families in one go (area 6).
   - Daily to-do email reminders for due dates (area 6).
   - Correcting data: the email is part 1's Move to a new email, the child's name part 1's Change name.

<!-- ux-designer-Opus5.5-agent, 2026-10-11. DRAFT for the owner. Part 3 of the rules for the Parents tab of the approved brief
     specs/features/admin-page.md. Part 1: admin-parents-1-find-a-family.md. Part 2: admin-parents-2-money-back.md.
     Shared rules (PT-n): specs/patterns.md. Decisions: specs/decisions/admin-parents.md. -->

Words follow `specs/glossary.md`. Keeping and deleting data: `site-rules.md`. Words in *italics* are on-screen words from the table at the end. "Part 1, AC-n" and "part 2, AC-n" mean rules in those parts; "sign-in part 1, AC-n" a rule in `sign-in-1-parents.md`.

## Patterns used
The same as part 1.

---

## Deletion requested
- **AC-1** Deletion requested, under Refunds to pay (part 1, AC-1), lists every family whose parent asked to delete their account and data, and that isn't deleted yet.
- **AC-2** Each request shows the account email, the child's first name, when it was asked, and the *Due* date, 21 days after the request (`site-rules.md`).
- **AC-3** The day after the due date, the row carries *Overdue* (PT-48). A test family's row carries the Test family label.
- **AC-4** Order: overdue first, then by due date, soonest first.
- **AC-5** Each request has *Open family*, which opens the family page (part 1, AC-12). There, the *Request line* shows under the account email. With no requests, the list shows *No requests* (PT-40).

## Delete this family
- **AC-6** *Delete this family* is the last button on every family page (part 1, AC-55), whether or not the parent asked on the parent page, because some ask by email or Report an issue.
- **AC-7** It is off, with *Payment waiting*, while the family has a receipt on Verify or a payment on Activate. Admin finishes it there first (confirm and activate, Close receipt, or Refund instead).
- **AC-8** It opens a dialog titled *Delete title*. The dialog lists what is deleted (*Deleted list*) and what is kept and why (*Kept list*).
- **AC-9** A family with an active or not-yet-started plan: the dialog also shows the Cancel plan figures for each (part 2, AC-4 to AC-11, AC-17), with Date asked set to the request date, or today when there is no request. Deleting cancels each plan that way. Each refund above RM0 goes on Refunds to pay, and the parent gets the Plan cancelled email (part 2, AC-14), with its bank-details link, just before the Account deleted email.
- **AC-10** Last comes Typed confirmation of the account email (PT-27 to PT-29). The button reads *Delete button*.
- **AC-11** The family has an approved review: the dialog shows *Review note*, because reviews Admin posted by hand must be taken down by hand.
- **AC-12** Pressing it shows *Deleting…* (PT-35). There is no Undo.
- **AC-13** Deleted: the account (account email, backup email, sign-ins), the child's first name, every answer, mark and feedback, spelling boxes, placement, reports, and reviews with their videos.
- **AC-14** Kept: receipts and their pictures, payments, plans, refunds, payment codes, and the name, email and WhatsApp number on each receipt, for 7 years (`site-rules.md`). Counts with no names stay for Numbers.
- **AC-15** Log entries stay. They keep the payment code, and the email shows as Deleted family (`sign-in-2-admin.md`, AC-25).
- **AC-16** When it is done, the dialog closes and the page shows *Deleted page*, with *Back to Parents*. The request leaves Deletion requested.
- **AC-17** The parent gets the *Account deleted* email at once, to the account email. It is sent before the email address is deleted.
- **AC-18** Every device signed in to the family is signed out. Answers still waiting on a phone are never sent anywhere (sign-in part 1, AC-27).
- **AC-19** If deleting stops part-way (for example, the internet drops), the dialog shows *Delete failed* and the button works again. Pressing it deletes what is left. Nothing already deleted comes back.
- **AC-20** After deleting, searching the payment code finds a *Deleted family result*, with its payments only. Searching the email or the child's name finds nothing.
- **AC-21** A refund still on Refunds to pay stays there, and its bank-details link keeps working (part 2, AC-33 to AC-47). The refund keeps the email it was sent to.
- **AC-22** The email can sign up again later, as a new account with nothing from before.

## Download family data
- **AC-23** *Download family data* sits in Account (part 1), before Delete this family.
- **AC-24** It makes one PDF file that a parent can read on a phone. The file's name holds the payment code (or the family's number) and the date, never an email or a name (*File name*).
- **AC-25** The file holds the account: account email, backup email, when the account was made, and when the consent was ticked.
- **AC-26** It holds the child's first name and every writing answer: the date, the task as the child saw it, the answer, the stars and the feedback.
- **AC-27** It holds every spelling round: the date, each word, and whether it was right.
- **AC-28** It holds the plans, the payments and the refunds, with only the last 4 digits of any bank account number, and the reports and reviews the parent sent. Receipt pictures are listed, not included.
- **AC-29** The child's placement: ? (decide: OQ-3). Lean: left out, because no level is ever shown to a parent (`writing-confidence.md`), and the lawyer confirms this before launch.
- **AC-30** The site emails nothing. Admin attaches the file to a reply from the inbox, where the conversation is (`admin-page.md`).
- **AC-31** While the file is made, the button shows *Making the file…* (PT-35). Then the browser downloads it. If it fails: PT-36.

---

## Layout
- **AC-32** From 1024 px up, Deletion requested is a table with these columns in order: Account email (with labels) · Child · Asked · Due · Open family.
- **AC-33** Below 1024 px, each request is a card (PT-6 to PT-11) in this order: account email · labels · due date · child · asked · Open family (filled). The due date matters most.
- **AC-34** In the Delete dialog, Deleted and Kept are two short lists, one under the other at every width, so each line can be read in full.

## Action log
- **AC-35** Delete this family (with the payment codes) and Download family data each write one entry (PT-52). A deletion request writes an entry with "parent" as who.

---

## Words on screen
`{email}` is an email, `{name}` the child's first name, `{code}` a payment code, `{date}` follows PT-50.

| Name | Words | Example |
|---|---|---|
| Deletion requested | Deletion requested | |
| Due | Due {date} | Due 1 Nov 2026 |
| Overdue | Overdue since {date} | |
| Open family | Open family | |
| No requests | No deletion requests. | |
| Request line | Asked to delete on {date} · due {date} | |
| Delete this family | Delete this family | |
| Payment waiting | A payment is waiting on Verify or Activate. Finish it there first. | |
| Delete title | Delete {email} | |
| Deleted list | Deleted: the account and its emails · {name}'s name, answers, marks and feedback · spelling progress · reports · reviews and videos | |
| Kept list | Kept for 7 years, by law: receipts, payments, plans, refunds and payment codes · the action log | |
| Review note | This family has an approved review. Take down anything you posted by hand. | |
| Delete button | Delete this family | |
| Deleting… | Deleting… | |
| Delete failed | Couldn't finish deleting. Check your internet and press Delete again to finish. | |
| Deleted page | {email} is deleted. Payment records are kept. | |
| Back to Parents | Back to Parents | |
| Deleted family result | Deleted family · {code} · payment records only | |
| Download family data | Download family data | |
| Making the file… | Making the file… | |
| File name | learn-english-data-{code or number}-{date}.pdf | learn-english-data-1601319-2026-10-11.pdf |

### Emails
| Name | Subject | What it says |
|---|---|---|
| Account deleted | {code} Your account and data are deleted | Your Learn English account and {name}'s work are deleted. We keep payment records for 7 years, as the law requires. (No code when the family never paid: the subject is "Your account and data are deleted".) |

## Content for testing
| What | Test value |
|---|---|
| Families to delete | A trial with no payment; an active RM59 plan; a cancelled plan with a refund waiting for bank details; an approved review with a video; a receipt on Verify |
| Biggest copy | 12 months of writing: about 400 answers with feedback, and 300 spelling rounds |
| List sizes | 0 requests, 1 overdue, 10 requests |
| Screen sizes | 320 × 568, 667 × 375, 390, 768 and 1280 px wide, large text on |

## Worked examples
| What happens | Result |
|---|---|
| A parent asks to delete on 11 Oct 2026 | Deletion requested shows Due 1 Nov 2026; from 2 Nov it is Overdue |
| Admin deletes a trial family with no payment | Everything goes; the parent gets Account deleted; searching the email finds nothing |
| Admin deletes a family whose cancelled plan has RM41.30 waiting for bank details | The refund stays on Refunds to pay and its link still works; searching #1601319 finds the Deleted family result |
| Deleting stops part-way | Delete failed; pressing again finishes it |
| A parent asks for a copy of their data through Report an issue | Admin presses Download family data and replies from the inbox with the file attached |

## Open questions
OQ-2 settled by the owner (gwl 2026-10-11): deleting cancels any plan on the date asked, with the usual refund.

- **OQ-3** Does the copy of a family's data show the child's placement? Lean: no, because no level is ever shown to a parent; the lawyer confirms this before launch. The other way: include it, as data the law may count as the parent's.
