# Brief: Writing Confidence (write a reply to an invitation)

<!-- project-lead-Opus5.5-agent, 2026-10-03. From the writing spike and the approved teaser (v4). APPROVED by the owner, 2026-10-04. Open question 21 (owner's business details) is deferred to before launch. Plans and prices, product names, trial limits and email-code sign-in updated by the owner, 2026-10-04 (open questions 22–24), and APPROVED the same day. Payment added from owner's scope note, 2026-10-03; owner page (Verify and Activate tabs) added the same day. -->

## Who it's for
A Malaysian child aged 10 (Year 4), learning English, writing at home on a phone, and the parent who signs them up. Ages 10 only for now; the wider site is for ages 10 to 15.

Level: the Malaysian KPM (Ministry of Education) standard for Year 4 is the floor. Tasks, nudges and Claude's feedback never fall below it. The level target above the floor is set in the owner's private notes and lives in the database with the teaching content, never in this public repository.

## The problem
Children rarely get to practise short writing with a teacher beside them. Free worksheets give no help while writing and no feedback after. Parents can't tell whether the answer was good or what to fix.

## What should happen
- A parent starts a free 3-day trial with their email: they type it, get a 6-digit code by email, and type the code in. No password. Signing in later (a new phone, or after signing out) works the same way: email, then a 6-digit code. The phone stays signed in, so the child just opens the site. Then the parent adds one child. The child can start writing straight away on the parent's phone or computer.
- The child does a set of 3 short tasks, one at a time. Each task is an invitation: "Your friend invites you to join her to go to the beach. Would you like to go? Give TWO reasons." The person, the place and the wording change from task to task.
- The child writes about 50 words on lined paper. A hint shows how to start: "Yes, I would like to go to {place} because…" or "No, I don't want to go to {place} because…". Both yes and no answers are fine.
- Idea words help a child who is stuck: words that fit this task's place and activities (for the beach: swim, sandcastle, seashells). There are idea words for a yes answer and for a no answer. The owner writes them for each task, in the database.
  - A "Help me" button appears when the child has been stuck for 2 minutes: no typing for 2 minutes while the three checks are not all ticked. The 2 minutes count from when the task opens, too.
  - Tapping Help me shows the idea words. If the child has already written yes or no, they see that set. If not, they see both sets, labelled Yes and No.
  - Once the button has appeared, it stays for the rest of that task.
- While the child writes, three checks tick on: Yes / No, 2 reasons, about 50 words.
- A teacher voice gives one short note at a time: a hint to start, then small nudges ("Use because…", "Try Also,…"). Each nudge is short and kind and never gives the answer away. Nudges are the owner's fixed lines from the database, picked by what the child has written so far, and they show instantly.
- After each task, the child gets warm feedback written for their own answer: what they did well, and one thing to try next time.
  - Claude writes it, through the owner's server, following the owner's feedback rules. The owner's rules and sample feedback live in the database.
  - Every piece of feedback passes a child-safety check before the child sees it. Anything that fails is replaced by the owner's fixed feedback line.
  - While the feedback is being written, the child sees a short "Your teacher is reading your answer" note. If it takes too long or fails, the owner's fixed feedback line shows instead. The child is never stuck.
  - Feedback is kind, short and at the child's level. It never rewrites the whole answer for them.
  - Every piece of feedback is saved, so the owner can read what children were told, and correct it (see the Feedback tab).
- With the feedback, the child sees a model answer for the same task, matching their choice: the yes model if they said yes, the no model if they said no. The owner writes both for each task, in the database.
- The child can submit a short answer. Nothing blocks them. The checks stay unticked, and the feedback says what's missing.
- After the 3rd task, the set is done. The child can start a new set.
- Answers are saved, so nothing is lost if the page closes.
- Calm and simple. No timer, no score to beat, no ranking.

### Plans and prices
<!-- project-lead-Opus5.5-agent: owner, 2026-10-04. Launch as two products: Writing Confidence and Spelling Confidence. -->
- **Writing Confidence:** RM59 for 12 months, or RM45 for 6 months. 3 days free first.
- The 12-month Writing Confidence plan includes Spelling Confidence free. The 6-month plan is writing only.
- **Spelling Confidence on its own:** RM39 for 12 months, RM29 for 6 months, or RM11 for 1 month. See `spelling-confidence.md`.
- No plan renews by itself.

### Paying after the trial
- The free trial lasts up to 3 days. The child can do tasks any time during those days.
- During the trial the child gets 2 sets a day (3 tasks each, so 6 tasks a day). The trial sets are fixed: the same 2 sets for every trial user, every day (owner, 2026-10-04). A new account, clearing cookies or a VPN gives no new questions.
- Feedback is still written for every trial answer, so a repeated set gets fresh feedback on the new answer.
- The pay page shows a short how-to guide: save or scan the DuitNow QR, pick a plan and pay its price to KIP ADVISORS, type your own payment code in the bank's Reference box, then screenshot the receipt.
- Each parent gets their own payment code: # and 6 digits, counting up from #160131 (the first parent gets #160131, the next #160132). It shows on the pay page with a Copy button. If a bank won't accept the #, the parent types just the digits.
- The parent sends the receipt: the screenshot, the transaction number, their name, their email, and a WhatsApp number (optional).
- The email field starts filled with the parent's account email. The form and the "Payment receipt received" screen both name that email: "we'll send your subscription activation to {parent's email}". If the parent changes the field, the named email changes with it.
- The owner verifies each payment by hand, by finding its payment code in the RHB transactions list (RHB shows the payer's Reference text). See the owner page below.
- When the owner activates the subscription, the parent sees "Subscription activated" with the plan, start date, end date, amount paid and payment code. A confirmation email with the same details is sent to them.
- Once a parent has sent a receipt, the child can keep writing for up to 2 days after the trial ends, while the owner verifies and activates.
- If those 2 days pass before activation, the child's tasks pause. The parent sees that the payment is still being verified and the subscription activation will be sent to their email. Nothing the child wrote is lost.
- Without a receipt sent, the child's tasks pause when the trial ends, and the parent sees the pay page.
- One payment can activate only one account.
- The receipt screenshot alone never verifies a payment, because a screenshot can be edited. It is only for the owner to look at.
- Receipts are private. Only the owner can see them.
- Wording: standard subscription terms (Subscription activated, payment verified, start date, end date). Avoid "year" and "match".
- Mock of the pay page (private): `docs/spikes/subscribe/index.html`.

### Owner page: subscription activations
A private page only the owner can open, with five tabs: Verify, Activate, Feedback, Reviews and Reports.

**Verify tab**
- A table of receipts waiting to be verified, newest first.
- Each row shows: payment code, plan and amount, parent name, email, child's name, phone number, and a link to view the receipt screenshot.
- The owner checks the payment code in the RHB transactions list, then clicks Confirm on that row.
- Confirm marks the payment as verified. The row leaves the Verify tab and appears in the Activate tab.
- Confirm sends nothing to the parent.
- After Confirm, an Undo shows for a few seconds. A verified parent can also be sent back to the Verify tab until they are activated.

**Activate tab**
- A table of verified parents only.
- Each row has an Activate button.
- The owner can tick one row, several rows, or all rows, and activate them in one go.
- Activate starts the parent's plan (its 6 or 12 months) from that day and sends the parent's confirmation email with the start and end dates.
- After Activate, an Undo shows for 30 seconds. The confirmation email waits until the 30 seconds are over, so an undone activation sends nothing.
- After a bulk Activate, the one Undo reverses the whole selected list.
- Undo puts the parents back in the Activate tab, still verified.
- Once the 30 seconds are over, the activation is final and the email goes out, even if the owner has left the page.
- Activated parents leave the Activate tab.

**Feedback tab**
- All feedback Claude has written, newest first.
- Each row shows: date, child's name, the task, the child's answer, and the feedback they got.
- The owner can flag a feedback and write a better version.
- Each correction is saved in the database. Claude is given the owner's corrections as examples every time it writes feedback from then on.
- The child who got the flagged feedback is not sent the new version (they've moved on). Only future feedback improves.
- A report about feedback (from the Support page) links to that feedback here.

**Reviews tab**
- Reviews from parents, newest first.
- Each row shows: date, name to show, parent's email, the text review, and a video player if there is a video.
- Approve marks a review as OK to share. Hide keeps it private.
- The owner posts approved reviews to Threads or the website by hand.

**Reports tab**
- Reports from the Support page, newest first.
- Each row shows: date, parent name, email, child's name, what it's about, and the message.
- Each new report also sends the owner an email.

### Parent page
- A small page for parents, reached from a quiet "Parent" link at the top of the child's screens.
- It shows the subscription: plan, start date and end date. During the trial it shows the trial days left and a Subscribe button instead.
- It shows the "Help other students" card once the child has finished 5 sets, until the parent sends a review.
- It links to Support and to Help other students.
- It is not a progress page. Progress goes in the 23-day email for now.
- Support and Help other students are reached through this page, never directly from the child's screens.

### Support page (parents)
- A Support page with a "Report an issue" form: what it's about (feedback my child received, payment or subscription, something isn't working, something else) and a text box for the details (up to 1000 characters).
- The reply goes to the parent's account email, which the form names.
- After sending, the parent sees "Report received".
- The Support link appears only in parent places: the parent page, the pay page footer and the emails. The child's writing screens have no Support or report link, so a child can't send reports by tapping around.
- A parent can send up to 5 reports a day, so repeated taps can't flood the owner.
- Mock (private): `docs/spikes/subscribe/support.html`.

### How you can help other students (parents)
- A page that asks parents for a text review or a video testimonial, so other students can also improve their English writing.
- Step 1, explain: why a review helps other children, the two ways to help (write a short review, upload a short video), and that the owner reads every review before anything is shared.
- Step 2, review: a text box (up to 600 characters) and/or a video upload (up to 1 minute, from the phone's gallery). At least one is needed. A name to show (first name is fine). A tick box to agree that the owner may share it on the website and social media, and, if the child appears in the video, the parent's consent for the child.
- Step 3, thank you: thanks by name, and a link to follow Cikgu Ahmad on Threads (https://www.threads.com/@cikgucelta).
- Nothing is shared publicly until the owner approves it (see the Reviews tab).
- Parent places only. Never on the child's screens. Parents are asked in three places:
  1. The activation email: a "Help other students" line.
  2. The parent's screen, after the child finishes their 5th set: a "Help other students" card. It stays there until the parent sends a review.
  3. A thank-you email after 23 days of active use: "Hope {child's name} is enjoying Writing Confidence", a quick progress report, then "Here's how you can help others enjoy learning to write with confidence in English", linking to this page. Sent once, and not sent if the parent has already sent a review.
- Also linked from the pay page footer and the Support page.
- Active use: a day counts as active when the child submits at least one task that day. The 23 days are counted from activation and don't need to be in a row.
- The quick progress report in that email: tasks done, active days, average words per answer in the first week compared with the last week, how often the answer had two reasons, one thing the child now does well, and one thing to work on next. Written for parents, in plain words.
- Mock (private): `docs/spikes/subscribe/review.html`.

### Terms of Subscription page
- A Terms of Subscription page, linked from the pay page ("By sending your receipt, you agree to the Terms of Subscription"), the Support page and the footer.
- Covers: who we are (Kip Advisors, registration number, address), what the parent gets, the free trial, plans and prices (see Plans and prices; each plan runs from activation, no automatic renewal), cancellation and refunds, using the service, AI-written teacher feedback, the child's work and personal data, reviews, changes, the parent's rights and disputes, and contact details.
- Cancellation and refunds follow the Consumer Protection Act 1999 (s.17). A parent can cancel at any time. Months run from the activation date and a started month counts as used. Refund = plan price × full months left ÷ plan months − 5% of the plan price (RM2.95 on the RM59 plan), paid within 30 days of the cancellation, never below RM0. The page shows a month-by-month refund table. A blanket "no refunds" term is not allowed.
- A Bahasa Malaysia version sits beside the English one.
- A Privacy Notice in Bahasa Malaysia and English is needed too (Personal Data Protection Act 2010), with the parent's consent for their child's data.
- The terms are checked by a Malaysian lawyer before launch.
- Mock (private, draft): `docs/spikes/subscribe/terms.html`.

## Out of scope
Card or online-banking payment (only QR transfer plus receipt for now). Renewal reminders before the end date. A second child. Other kinds of writing (emails, stories). A parent progress page. Malay text. Schools and teachers. The reading sheets, which are a separate later product (`specs/later/language-practice/`).

## Anything to match
Site name: "Learn English at Puascari.com" (short form "Learn English"). Products: "Writing Confidence" (this brief) and "Spelling Confidence" (`spelling-confidence.md`). Address: puascari.com/learnenglish.
Every page and email ends with a quiet footer: "Learn English is brought to you by Kip Advisors".
The approved teaser (v4): a calm, light page, with the retro task card (ink border, flat shadow, small Mario-colour touches) and the teacher notes with a smiley. The CTA is "Try 3 days for free". The credit line is "Created by Cikgu Ahmad, a CELTA-certified English teacher." Fonts: Manrope on the page, Nunito on the task card. The prototype is the writing spike (kept privately).

All task text, hints, nudges and feedback lines live in the database, never in the code.

## Open questions
1. ~~How is the feedback made?~~ Answered by the owner, 2026-10-03: the gold standard. Claude writes feedback for each answer through the owner's server, with child-safety checks. The teaser stays as it is.
2. ~~What ages, exactly?~~ Answered by the owner, 2026-10-04: age 10 only for now (Malaysian Year 4). KPM is the floor. The level target above it stays private.
3. ~~How does the product help a stuck child?~~ Answered by the owner, 2026-10-04: idea words for each task (place and activities), and feedback plus a model answer after submitting. Short answers can still be submitted. No redraft for now.
3a. ~~When do the idea words show?~~ Answered by the owner, 2026-10-04: a Help me button appears after 2 minutes stuck, and tapping it shows the idea words.
4. ~~What happens after the 3-day trial?~~ Answered by the owner, 2026-10-03: pay RM59 for a 12-month subscription by QR transfer and upload the receipt. The owner verifies the payment in the RHB transactions list, then activates the subscription on the owner page. See "Paying after the trial".
5. ~~How does the owner add the bank's payments?~~ Answered by the owner, 2026-10-03: RHB shows the Reference text but has no Excel or CSV download, so the owner verifies by hand on the Verify tab. Pasting the RHB list so the site pre-checks payment codes is a possible later helper.
6. ~~While a payment is being verified, can the child keep writing?~~ Answered by the owner, 2026-10-04: yes, for up to 2 days after the trial ends.
7. ~~Can the parent pay before the trial ends?~~ Answered by the owner, 2026-10-04: yes. The pay page is open from day 1, paying early doesn't cut the trial short, and the 12 months start on the day the owner activates.
8. ~~Should a verified payment activate by itself?~~ Answered by the owner, 2026-10-03: no. The owner confirms each payment on the Verify tab, then activates on the Activate tab (one, several or all at once).
9. ~~Can a click be undone?~~ Answered by the owner, 2026-10-03: Activate has a 30-second Undo, and after a bulk Activate the Undo reverses the whole selected list. Confirm gets a short Undo too (lead's lean, not objected to).
10. Gold standard, later: a payment service that confirms DuitNow payments by itself, so the owner never adds payments. Small fee per payment.
11. ~~Who writes the nudges while the child is writing?~~ Answered by the owner, 2026-10-03: the owner's fixed lines, picked by what the child has written so far (no Yes/No yet, no "because" yet, under 50 words). Claude writes only the feedback after each task.
12. ~~Should the owner see Claude's feedback before the child does?~~ Answered by the owner, 2026-10-04: the gold standard. No approval before the child sees it, but the owner can flag any feedback and write a better one, and Claude follows those corrections from then on. See the Feedback tab.
13. ~~Where do reports go?~~ Answered by the owner, 2026-10-04: a Reports tab on the owner page, newest first, plus an email to the owner for each new report.
14. ~~Should the Support page sit behind a parent check?~~ Answered by the owner, 2026-10-04: not at launch. The link stays off the child's screens, with the 5-a-day limit. A parent check (a short sum) is added later if children still find it, or for a phone app.
15. ~~Where does the owner read and approve reviews?~~ Answered by the owner, 2026-10-04: a Reviews tab on the owner page.
16. ~~When is the parent asked for a review?~~ Answered by the owner, 2026-10-04: in the activation email; on the parent's screen after the 5th set (it stays); and a thank-you email with a quick progress report after 23 days of active use.
17. ~~What counts as a day of active use?~~ Answered by the owner, 2026-10-04: a day the child submits at least one task. 23 such days since activation, not necessarily in a row.
18. ~~Product name?~~ Answered by the owner, 2026-10-04: "Puascari's Learn English", at puascari.com/learnenglish, with the footer "Learn English is brought to you by Kip Advisors". The approved teaser still says "Learn English"; whether to update it is the owner's call.
19. ~~Add a small parent page?~~ Answered by the owner, 2026-10-04: yes. See "Parent page".
20. ~~Refunds?~~ Answered by the owner, 2026-10-04: keep RM59 for 12 months. A parent can cancel at any time (Consumer Protection Act 1999, s.17). Subscription months run from the activation date; a month counts as used from its first day, with no part-month refunds. The refund is the full months after the current one, up to the end date, minus a 5% charge (RM2.95), paid within 14 days and never below RM0. A Malaysian lawyer checks the terms before launch.
21. Owner's details for the Terms page (Kip Advisors' registration number, business address, support email, phone number): the owner gives them later, 2026-10-04. They go into the Terms page only, never into this public repository. Needed before launch.
22. ~~Plans, prices and names at launch?~~ Answered by the owner, 2026-10-04: two products, Writing Confidence and Spelling Confidence, on "Learn English at Puascari.com". Writing Confidence is RM59 for 12 months (Spelling Confidence included free) or RM45 for 6 months, with 3 days free. Spelling Confidence alone is RM39 for 12 months, RM29 for 6 months or RM11 for 1 month. Refunds are now paid within 30 days of the cancellation (was 14 days). This replaces the single RM59 plan in answers 4 and 20 and the name in answer 18.
23. ~~Should the writing trial be limited?~~ Answered by the owner, 2026-10-04: 2 sets a day (3 tasks each) for the 3 days, always the same 2 fixed sets, so cheating the trial gives no new questions.
24. ~~How does a parent sign up and sign in?~~ Answered by the owner, 2026-10-04: both with a 6-digit code sent to their email, no password. A new email only gets the same fixed trial sets, so fake emails gain nothing. A limit on sign-ups from one network stops a script from making hundreds of accounts.
