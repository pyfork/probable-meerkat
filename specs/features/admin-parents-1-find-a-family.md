# Spec: Admin: Parents, part 1 of 3: Find a family

## Problem
Parents write to support about one family at a time (a lost email, a code limit, a missing activation email), so Admin must find that family in seconds from whatever the parent gave, and fix it without touching any other family.

### Concept checks
1. Does the Parents tab list every family when it opens? → No. It shows the lists with deadlines, then the search (AC-1).
2. Can Admin find a family from its backup email? → Yes (AC-5).
3. Two children are called Aiman. Does the search show only the first? → No. Every match (AC-7).
4. Does the family's web address hold the parent's email? → No (AC-12).
5. Admin resets a child's placement. Does the child see anything? → No (AC-27).
6. Does Reset placement put the child on the Guided paper? → No. Back to Average (AC-26).
7. Does Reset code limit send the parent an email? → No (AC-31).
8. Does Resend activation email change the plan's dates? → No. Only the email goes again (AC-35).
9. Can Admin move an account without checking the parent is the payer? → No. The dialog shows what to check, and Admin types the current email (AC-39, AC-41).
10. Does Admin's move wait 24 hours, like Can't get into my email? → No. Admin has checked the payer; it changes at once, with Undo (AC-46).
11. Can a family with no payment be moved? → No. The parent signs up again with the new email (AC-38).
12. Can the new email belong to another account? → No (AC-43).

## Goals and non-goals
1. **Goals**
   - Admin finds a family from an email, a payment code or a child's first name, on a phone or a laptop.
   - One page shows everything about a family: the child, plans, payments, emails sent and the account.
   - Admin can fix a placement, a code limit, a lost activation email or a lost email address from that page.
2. **Non-goals**
   - Cancel plan and Refunds to pay (part 2). Deletion requested, Delete this family and Download family data (part 3).
   - Placement history (`design-order.md`, soon after launch). Download payments (area 12).
   - Marking a family as a test family, and clearing test families (area 6).
   - Siblings: one child per account at launch (`accounts-and-sign-in.md`).

<!-- ux-designer-Opus5.5-agent, 2026-10-11. DRAFT for the owner. Part 1 of the rules for the Parents tab of the approved brief
     specs/features/admin-page.md. Part 2: admin-parents-2-money-back.md. Part 3: admin-parents-3-delete-and-copy.md.
     Shared rules (PT-n): specs/patterns.md. Decisions: specs/decisions/admin-parents.md. -->

Words follow `specs/glossary.md`. The brief: `admin-page.md` (Parents). Words in *italics* are on-screen words from the table at the end. "Sign-in part 1, AC-n" means a rule in `sign-in-1-parents.md`.

## Patterns used
Admin tabs (PT-1 to PT-5), Row becomes a card (PT-6 to PT-11), Lists move only when Admin asks (PT-12 to PT-15), Undo in place (PT-16 to PT-26), Typed confirmation (PT-27 to PT-29), Email didn't arrive (PT-30 to PT-34), Buttons that change something (PT-35 to PT-38), List states (PT-39 to PT-41), Dialog (PT-42 to PT-45), Labels on a row (PT-48, PT-49), Times and money (PT-50, PT-51), Action log (PT-52).

---

## The Parents tab
- **AC-1** The tab shows, in order: Refunds to pay (part 2), Deletion requested (part 3), then *Find a family*.
- **AC-2** The tab count (PT-3) is the refunds that can be paid now plus the deletions requested. Refunds still waiting for bank details don't count, because Admin can't pay them yet.

## Search
- **AC-3** Find a family has one search box (*Search box*), a *Search* button and a *Weaker* button.
- **AC-4** The search runs when Admin presses Search or Enter, not while typing.
- **AC-5** It finds a family when the account email or backup email contains the text.
- **AC-6** It also finds a family when a payment code equals the text, with or without the #, or when the text is the code's first 6 digits.
- **AC-7** It also finds every child whose first name starts with the text.
- **AC-8** Capital letters, and spaces at either end, don't matter. Fewer than 2 characters shows *Type more* and searches nothing.
- **AC-9** Results show 50 families at first, newest sign-up first. *Show more* adds the next 50 below, and what is on screen stays.
- **AC-10** No match shows *No family found* (PT-40). The search box keeps the text.
- **AC-11** Each result shows the account email, the child's first name, each plan in one short line (*Plan line*), the payment codes, and its labels: *Test family*, *Deletion requested*, *Refund to pay* (PT-48, PT-49).
- **AC-12** A result opens the family page. The family page has its own web address, made from a number, never from an email or a name, so reloading or going Back keeps Admin there (PT-5).
- **AC-13** *Weaker* lists every child on the Weaker placement now, longest first, with since when. It is a search like any other: the box empties, and Back returns to it.

## The family page
- **AC-14** The family page shows, in order: the account email in the largest text, its labels, then the sections Child, Plans, Payments, Emails and Account.
- **AC-15** *Back to results* at the top returns to the search with the same results and the same place in the list. The browser's Back does the same.
- **AC-16** The page doesn't change by itself while open. A newer version shows the List changed bar (PT-12 to PT-14).

### Child
- **AC-17** Child shows the child's first name and *Change name*.
- **AC-18** Change name opens a dialog (PT-42 to PT-45) with one box, following sign-in part 1, AC-18. *Save name* changes the name at once, with Undo for 10 seconds (PT-16, PT-17). Nothing is emailed.

### Plans
- **AC-19** Each plan shows the product, length, price paid, payment code, and its state in words (*Plan states*).
- **AC-20** A trial shows the time left, or *Trial not started* for a Spelling parent whose child hasn't opened Writing yet (sign-in part 1, AC-48).
- **AC-21** A waiting plan links to its row on Verify or Activate.
- **AC-22** An activated plan shows Resend activation email (AC-34). An active plan also shows Cancel plan (part 2).

### Placement
- **AC-23** A family with Writing Confidence shows *Placement* under Child: the level (Weaker, Average or Stronger), since when, and why in the owner's words (for example "average 2.3 stars over the last 3 sets").
- **AC-24** A child with no finished sets shows *No sets yet*. A family without Writing shows no Placement.
- **AC-25** Placement shows *Reset placement* when the child is not Average, or has sets in the placement window.
- **AC-26** Reset placement puts the child back to Average and empties the window, so the next set counts as their first (`writing-confidence.md`).
- **AC-27** The child sees nothing. A set the child is doing now keeps its paper; the next set uses the standard paper.
- **AC-28** Reset placement has Undo for 10 seconds (PT-16, PT-17). Undo puts back the level and the window as they were.

### Payments
- **AC-29** Payments lists every receipt, newest first: when it was sent, amount recorded (or *Not checked yet*), payment code, bank transaction number, its state in words (*Payment states*), and *View receipt*. View receipt opens the picture through a link that expires after a few minutes (`site-rules.md`).
- **AC-30** Refunds for this family show in Payments too, with their state (part 2).

### Account
- **AC-31** Account shows the account email, the backup email (or *Backup: not given*, PT-11), when the account was made, when the consent was ticked, and *Codes line* for each of the two emails. *Reset code limit* sets both counts to 0 at once. It sends nothing, and the code the parent already has still works. The line becomes *Limit reset*, with no Undo.
- **AC-32** Reset code limit is off while neither email has had a code in the last hour.
- **AC-33** *See in Log* opens the Log searched for the account email (`sign-in-2-admin.md`, AC-23).

## Resend activation email
- **AC-34** Resend activation email asks where to send it (PT-32): the account email, or the email on the receipt form if it differs.
- **AC-35** It sends the same Subscription activated email again, with the plan's dates unchanged. Nothing else changes.
- **AC-36** It sends at once, with no Undo. The plan shows the Resent line (PT-33).

## Emails
- **AC-37** Emails lists every email sent to this family, newest first: when, which email, and to which address. A failed one shows Didn't arrive with Resend (PT-30 to PT-34). It shows 20 at first, then Show more.

## Move to a new email
- **AC-38** *Move to a new email* (in Account) is off, with *No payment to check*, when the family has no verified payment. Such a parent signs up again with the new email.
- **AC-39** It opens a dialog titled *Move title*. It first shows *Check these*: every verified payment code and bank transaction number, and the child's first name, to compare with the parent's message (`accounts-and-sign-in.md`).
- **AC-40** Next, a *New email* box. It follows sign-in part 1, AC-7 to AC-9 (spaces, capitals, Not an email, Did you mean).
- **AC-41** Last, Typed confirmation of the current account email (PT-27 to PT-29).
- **AC-42** The *Move button* stays off until the new email is an email and the typed email matches.
- **AC-43** If the new email is another account's account email or backup email, pressing Move shows *Email taken* under the box. Nothing changes, and what was typed stays.
- **AC-44** If the new email is the current one, pressing Move shows *Same email*.
- **AC-45** If the new email is this family's backup email, the move goes ahead and the family has no backup email afterwards (as in sign-in part 1, AC-33).
- **AC-46** Move changes the account email at once and closes the dialog. The account email line becomes the *Moved line*, with Undo for 30 seconds (PT-16 to PT-26). Undo puts the old email back.
- **AC-47** When the 30 seconds are over, the new email gets the *Moved email* and the old email gets the Changed email (sign-in part 1, AC-37). An undone move sends nothing (PT-18).
- **AC-48** Devices already signed in stay signed in. A waiting Can't get into my email change is cancelled (sign-in part 1, AC-39).
- **AC-49** Receipts and payment records keep the email they were sent with.

---

## Layout
- **AC-50** From 1024 px up, the results are a table with these columns in order: Account email · Child · Plans · Payment codes · Labels.
- **AC-51** Below 1024 px, each result is a card (PT-6 to PT-11) in this order: account email · labels · child · plans · payment codes. The whole card opens the family page.
- **AC-52** From 640 px up, the search box, Search and Weaker sit on one line. Below 640 px, the box fills the width and Search and Weaker share the next line. Below 400 px, they each take a full line, because a long email needs the whole width.
- **AC-53** The family page is one column, at most 720 px wide, lined up with the page's left edge, at every width, because it is read top to bottom. Inside it, Payments and Emails are tables from 1024 px up and cards below.
- **AC-54** On a narrow screen, the account email, the labels, the child and the plans matter most, so they come first. Nothing is tucked into a menu.
- **AC-55** Buttons sit in the section they act on. Change name, Reset placement and Reset code limit are never filled. Delete this family (part 3) is always last.

## Keyboard and screen reader
- **AC-56** Enter in the search box runs the search. When results arrive, *Results read out* is read out once, politely. Focus stays in the box.
- **AC-57** Results are links. When the family page opens, focus goes to its first heading.

## Action log
- **AC-58** Change name, Reset placement, Reset code limit, Resend activation email, Move to a new email (with the old and new email) and every Undo each write one entry (PT-52). Searching and opening a family write nothing.

---

## Words on screen
`{email}` is an email, `{name}` the child's first name, `{code}` a payment code, `{n}` a number, `{date}` and `{time}` follow PT-50.

| Name | Words | Example |
|---|---|---|
| Find a family | Find a family | |
| Search box | Email, payment code or child's first name | |
| Search | Search | |
| Weaker | Weaker in Writing | |
| Type more | Type at least 2 characters. | |
| No family found | No family found for "{text}". | No family found for "aiman@gmial". |
| Show more | Show more | |
| Results read out | {n} families found | 3 families found |
| Plan line | {product} RM{price} · {state} | Writing RM59.00 · active to 4 Oct 2027 |
| Test family | Test family | |
| Deletion requested | Deletion requested | |
| Refund to pay | Refund to pay | |
| Back to results | Back to results | |
| Change name | Change name | |
| Save name | Save name | |
| Placement | Placement: {level} since {date} · {why} | Placement: Weaker since 3 Nov · average 1.5 stars over the last 3 sets |
| No sets yet | Placement: Average · no sets yet | |
| Reset placement | Reset placement | |
| Not checked yet | Not checked yet | |
| View receipt | View receipt | |
| Backup: not given | Backup email: not given | |
| Codes line | {email}: {n} of 5 codes in the last hour | sharifah.n@yahoo.com.my: 5 of 5 codes in the last hour |
| Reset code limit | Reset code limit | |
| Limit reset | Code limit reset. They can ask for a code now. | |
| See in Log | See in Log | |
| Resend activation email | Resend activation email | |
| Move to a new email | Move to a new email | |
| No payment to check | No verified payment to check. The parent can sign up again with the new email. | |
| Move title | Move {email} to a new email | |
| Check these | Check these match the parent's message: | |
| New email | New email | |
| Move button | Move to new email | |
| Email taken | This email already belongs to another account. | |
| Same email | That's the current email. | |
| Moved line | Moved to {email} | |
| Trial not started | Writing trial: not started | |

### Plan states
| State | Words |
|---|---|
| trial | Trial · {time left} left |
| waiting | Waiting on Verify (or Activate) |
| active | Active {start} to {end} |
| paused | Paused since {date} |
| cancelled | Cancelled · can go on until {date} |
| ended | Ended {date} |

### Payment states
| State | Words |
|---|---|
| waiting to be checked | On Verify |
| verified | Verified {date} · on Activate |
| activated | Activated {date} |
| closed receipt | Closed {date} · {reason} |
| refund instead | Refunded instead |
| payment not found | Payment not found |

### Emails
| Name | Subject | What it says |
|---|---|---|
| Moved email | Your account email has changed | Your Learn English account email is now {email}. Sign in with it to carry on. |

## Content for testing
All names and emails are made up.

| What | Test value |
|---|---|
| Long account email | sharifah.nuraisyahhumaira.syedkhairul@yahoo.com.my |
| Long child's first name | Muhammad Aiman Haziq |
| Searches | #1601319, 1601319, 160131, AIMAN, " aiman ", a, aiman@gmial |
| Result sizes | 0, 1, 2 children called Aiman, 51 (to show Show more) |
| Family with every label | Test family, Deletion requested, Refund to pay |
| Family with the most | Writing RM59 active, a renewal waiting, 4 receipts, 1 refund, 30 emails, one that didn't arrive |
| Families with the least | A Writing trial with no payment; a Spelling parent whose child hasn't opened Writing |
| Screen sizes | 320 × 568, 667 × 375, 390, 768 and 1280 px wide, a 1280 px laptop split in half, large text on |

## Worked examples
| What happens | Result |
|---|---|
| A parent writes "my code is 1601319"; Admin searches 1601319 | One family. Searching #1601319 or 160131 finds the same family |
| Admin searches "aiman" | Every child whose first name starts with Aiman, and every email containing aiman |
| A parent at the code limit writes in; Admin presses Reset code limit | Both counts go to 0; the parent can ask for a code at once |
| Placement is Weaker since 3 Nov; Admin presses Reset placement while the child is on a Guided set | That set stays Guided; the next set is standard and counts as the first |
| A parent lost their email. They send #1601319, transaction 2610051234 and "Aiman". Admin checks them against Check these, types the new email and the current email, and presses Move | The account email changes at once. After 30 seconds the new email gets the Moved email and the old email the Changed email |
| The new email already has a trial account | Email taken. Admin sorts it out with the parent by email |

## Open questions
None.
