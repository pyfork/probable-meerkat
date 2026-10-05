# Brief: Admin page

<!-- project-lead-Opus5.5-agent, 2026-10-05. DRAFT for the owner's re-approval. Was "Owner page" in the writing brief; split out and grown to 8 tabs
     (owner, 2026-10-04 and 2026-10-05). Decisions: specs/decisions/admin-page.md. -->

Words follow `specs/glossary.md`. Rules for every page are in `site-rules.md`. Admin signs in as described in `accounts-and-sign-in.md`.

## Who it's for
Admin (today, the owner). Nobody else can open this page.

## The problem
Payments are checked by hand, the model writes feedback without approval, and all content goes live before review. Admin needs one place to check money, feedback, content, families and numbers, quickly and safely.

## What should happen
Eight tabs: **Verify, Activate, Answers, Reviews, Reports, Numbers, Parents, Content.** A small **Log** link shows the admin action log (see `accounts-and-sign-in.md`).

### Verify
- Receipts waiting to be checked, newest first.
- Each row: payment code, plan and amount, parent name, email, child's name, WhatsApp number, and a link to view the receipt picture.
- Admin finds the payment code in the bank's transactions list, then clicks **Confirm**. Confirm marks the payment as verified and moves the row to Activate. It sends nothing to the parent. An Undo shows for a few seconds after Confirm, and a verified parent can be sent back to Verify until activated.
- **"Possible double payment"** label when the same plan for the same child is paid again while active or waiting (see `plans-and-payment.md`).
- **"Problem with this payment"** button: Admin picks a reason (wrong amount, code not found, receipt unclear, possible double payment) and can add a note of up to 300 characters. It emails the parent the owner's fixed wording for that reason plus the note, and reopens their receipt form. The row shows what was sent and when.
- **"Mark sorted"** clears a row once it is dealt with.

### Activate
- Verified payments only, each with an **Activate** button.
- Admin can tick one row, several rows or all rows and activate them in one go.
- Activate starts the plan from that day and sends the parent's confirmation email with the start and end dates.
- An Undo shows for 30 seconds. The email waits until the 30 seconds are over, so an undone activation sends nothing. After a bulk Activate, the one Undo reverses the whole list. Undo puts the rows back in Activate, still verified.
- After 30 seconds the activation is final and the email goes out, even if Admin has left the page.

### Answers
- Every writing answer with what the child saw: the task, the answer with its colour marking, the marking list, the stars, the model's feedback, the model answer shown, and the version of the owner's feedback rules that wrote the feedback.
- **To check:** a list of all flagged answers (a copied model answer, unkind words), all 1-star answers, and 10 random answers a week (a fair spot-check).
- **Checked** saves who checked it and when.
- Filters: To check, by child, by task, by date, by stars.
- **Fix feedback:** Admin flags a feedback and writes a better one. Each correction is saved, and the model is given the owner's corrections as examples from then on. The child who got the flagged feedback isn't sent the new one; only future feedback improves.
- A Report about feedback links to that answer.
- Spelling answers come later.

### Reviews
- Parents' reviews, newest first: date, name to show, parent's email, the text, and a video player if there is a video.
- **Approve** marks a review as OK to share. **Hide** keeps it private. Admin posts approved reviews to Threads or the website by hand.

### Reports
- Reports from the Report an issue form, newest first: date, report number, parent name, email, child's name, what it's about, and the message.
- Each new report also sends Admin an email. Its subject carries the report number, so replies can be found in Admin's inbox.
- **"Mark sorted"** clears a report once it is dealt with.

### Numbers
How we know the products work. Targets are set after the first month of real data and kept in the owner's private notes.

| Measure | What it tells Admin |
|---|---|
| **Trial to paid:** of parents who finish a trial, how many send a receipt | Is the trial convincing parents? |
| **Keeps coming back:** of paying children, how many have 3 or more active days a week | Do children actually use it? |
| **Writing gets better:** answers with Yes/No, 2 reasons and about 50 words, week 1 compared with week 4 | Is it teaching? |
| **Is the model's feedback good enough?** Of the 10 random answers a week, how many Admin had to fix | Is the feedback right? |
| **Confident words** per spelling child per month | Is spelling sticking? |

### Parents
- Search a parent by email. Each family shows: plan(s), start and end dates or trial time left, payments, and the child.
- **Placement** (writing): the child's level (Weaker, Average or Stronger), since when, and why (for example "average 2.3 stars over the last 3 sets"), plus a history of changes. **"Reset placement"** puts the child back to Average and clears the window, so the next set counts as their first. The child sees nothing. A **"Weaker"** filter shows who is on the Guided paper now.
- **"Reset code limit"**, **"Resend activation email"** and **"Move to a new email"** (after Admin has checked the parent is the payer; see `accounts-and-sign-in.md`).
- **"Cancel plan":** a box shows the plan, activation date, the date the parent asked (Admin can change it), the month now in (counts as used), full months left, the refund worked out with the formula, the last day the child can go on, and the pay-by date (30 days). Confirming ends the plan and emails the parent the same figures. When the refund is RM0 the box says "No refund due".
- **"Refunds to pay":** a list at the top of the tab with pay-by dates. Overdue ones turn red. Double-payment refunds join the same list for the full extra amount. **"Mark refunded"** with the bank transfer reference sends the parent a "refund sent" email.
- **"Deletion requested":** a list at the top of the tab of parents who asked to delete their account and data, each with its due date (21 days after the request). Overdue ones turn red. **"Delete this family"** deletes the account and the child's work, keeps the payment records, and emails the parent.

### Content
- An inventory per product (Writing / Spelling): for each kind of content, how many there are and how many are Approved, Not reviewed and Needs change. Each row has **"Start review"**.
- Review one item at a time: a writing task shows the invitation, Yes and No idea words and all 4 model answers; a spelling word shows the clue, first letter, hint, all versions with play buttons and any "also right" answers.
- Buttons: **Approve**, **Needs change** (with a note), **Edit** (fix the text right there), **Skip**. Arrows move between items; Enter approves. Filters: Not reviewed, Needs change, Approved. Each item remembers who approved it and when.
- All content is live from launch; review happens as Admin goes. **Needs change** pauses that item for children until it is fixed.
- An edit saves a new version. An edited spelling sentence shows **"recording needed"** until its new audio is made.

### Teaching settings (on the Content tab)
Every number below lives only here. Admin can change each one within a safe range. A change applies from the child's next task or round, never in the middle of one, and a history records who changed what and when.

| Setting | Default | Product |
|---|---|---|
| Help time (Fun mode) | 6 seconds | Writing and Spelling |
| Help in Exam mode | none | Writing and Spelling |
| "About 50 words" ticks | 45 to 55 words; caution icon above 55 | Writing |
| Long-sentence nudge (Weaker only) | at 13 words with no full stop | Writing |
| Wait for the model's feedback | 15 seconds, then the owner's fixed line | Writing |
| Placement window | the last 3 sets | Writing |
| Placement: first set | 2 or more tasks with 0–1 star → Weaker; all 3 with 3 stars → Stronger | Writing |
| Placement: later sets | average stars below 1.7 → Weaker; 2.7 or more → Stronger | Writing |
| Placement: change only after | 2 sets in a row point the same way | Writing |
| New sets a day | 5 | Writing |
| Answers a day (cost cap) | 30 | Writing |
| Bonus round: qualify with | up to 4 wrong out of 8 | Spelling |
| Word list 2 starts when | every list 1 word met and 8 in 10 confident | Spelling |
| Word list mix after that | 30 : 70 (list 1 : list 2) | Spelling |
| New rounds a day | 10 | Spelling |
| Trial sizes | as written in `plans-and-payment.md` (that brief holds them) | Writing and Spelling |

### Emails and replies
- Every email to a parent is sent from the site's address with **Reply-To support@puascari.com**, which forwards to Admin's inbox. Admin answers from that inbox as support@puascari.com.
- Conversations stay in Admin's inbox, not on the admin page. Every email subject carries the payment code or report number, so a search finds the whole conversation, and each row shows what was sent and when.

## Worked examples
| What happens | Result |
|---|---|
| Admin confirms #160135, then clicks Undo within a few seconds | The row is back in Verify; nothing was sent |
| Admin ticks 4 rows on Activate, clicks Activate, then Undo after 10 s | All 4 are back in Activate, still verified; no emails sent |
| A child's last 3 sets average 2.3 stars after being Weaker, and the next window is 2.4 | Two sets in a row point to Average, so the child moves to the standard paper |
| Admin changes Help time from 6 to 10 seconds while a child is on task 2 | Task 2 keeps 6 seconds; task 3 uses 10 |
| Admin marks a spelling clue "Needs change" | That word leaves new rounds until the clue is fixed |

## Out of scope
Conversations with parents on the admin page (they stay in Admin's inbox; later, if volume grows or a helper joins). More than one Admin login. Spelling answers on the Answers tab (later).

## Open questions
None.
