# Brief: Site rules (every page)

<!-- project-lead-Opus5.5-agent, 2026-10-05. APPROVED by the owner, 2026-10-05. NEW shared brief, added during the rewrite so that
     rules for every page live in one place (owner's one-fact-one-place rule, 2026-10-04). Decisions: specs/decisions/site-rules.md. -->

Words follow `specs/glossary.md`.

## Who it's for
Everyone who opens Learn English at Puascari.com: the child, the parent and Admin. These rules apply to every page and email of both products.

## Name and look
- Site name: "Learn English at Puascari.com" (short form "Learn English"). Products: **Writing Confidence** and **Spelling Confidence**.
- Every page and email ends with a quiet footer: "Learn English is brought to you by Kip Advisors".
- The look follows the approved teaser (v4): a calm, light page, the retro task card (ink border, flat shadow, small Mario-colour touches) and teacher notes with a smiley. The CTA is "Try 3 days for free". The credit line is "Created by Cikgu Ahmad, a CELTA-certified English teacher." Fonts: Manrope on the page, Nunito on the task card.
- Icons: Heroicons only.
- A selected choice fills with colour (no outline). Up and Down move the selection, Enter picks it.
- Calm and simple: no timer, no score to beat, no ranking, and no level names anywhere a child can see.

## Phones and speed
- Works on Android phones (Chrome) and iPhones (Safari) from the last 3 years, from 320 pixels wide, with large text turned on. Nothing scrolls sideways.
- The child's pages open in under 3 seconds on a cheap Android phone on 4G, and in under 1 second on later visits.
- The child's pages keep working when the internet drops: typing, checks, notes, help, hints and spelling marking all work without it. A finished answer waits on the phone and sends itself when the internet is back. A child who has opened the site before can open it with no internet.

## Time
- Every "day" is a Malaysia-time day (see the glossary): daily limits, active days, plan start and end dates. The writing trial and grace time are counted in hours from the moment they start (see `plans-and-payment.md`).

## New-task limits (stops anyone copying all the content)
- Each child can open a limited number of new sets or rounds a day (numbers in Teaching settings, `admin-page.md`).
- At the limit the child sees a kind message that new tasks unlock tomorrow. Tasks already opened can still be practised.

## Content
- All content (tasks, idea words, starters, nudges, model answers, feedback rules, words, clues, hints, sentences, tips, audio) lives in the database and the private store, never in the code or this repository.
- All content is live for children from launch. Admin reviews it afterwards on the Content tab. Content marked "Needs change" pauses until it is fixed.
- A changed piece of content is saved as a new version. A child's old answers always show the content they actually saw.
- The level floor is the Malaysian KPM Year 4 standard. The level target above it is in the owner's private notes, never in this repository.

## The model (AI)
- Feedback is written by the model through the owner's server. The model's key is never on a phone.
- The model's instructions and the child-safety check wording live in the database, not in the code.
- A monthly spending limit is set in the model provider's console (Admin chooses the amount). If it is reached, children get the owner's fixed feedback line and Admin gets an email.
- Each child can submit at most a set number of answers a day (Teaching settings), so one account can't run up costs.

## Privacy Notice (PDPA)
<!-- project-lead-Opus5.5-agent, 2026-10-05: owner asked for a privacy / PDPA statement. Plain-words requirements; a Malaysian lawyer writes and checks the final text. -->
- A **Privacy Notice** page, in English and Bahasa Malaysia side by side, under the Personal Data Protection Act 2010 (and its 2024 amendments).
- Linked from the footer of every page, the sign-up page, the pay page, the parent page and every email.
- It says, in plain words:
  - **who we are** and how to contact us about personal data (Report an issue and the support email);
  - **what we collect:** the parent's name, email, backup email (optional) and WhatsApp number (optional), the child's first name, the child's answers and marks, payment receipts and payment records, reviews and videos the parent chooses to send, and basic device and usage information;
  - **why:** to run the lessons, mark and give feedback, check payments, send emails about the account, improve the lessons, and meet the law;
  - **who else handles it, for us:** the model provider that writes feedback, the email service, and the hosting and storage services. Nobody sells or rents personal data;
  - **data sent outside Malaysia:** some of these services run outside Malaysia, and the Notice says so and how the data is protected;
  - **how long we keep it** (see Keeping and deleting data below);
  - **the parent's rights:** to see a copy of their and their child's data, to correct it, to withdraw consent, to limit direct marketing, and to delete the account and data. Requests go through Report an issue (or "Delete my account and data" on the parent page) and are answered within 21 days;
  - **children:** the child's data is collected only with the parent's or guardian's consent;
  - **security**, and that the parent will be told if a data breach puts their data at real risk;
  - **which details are needed and which are optional,** and what happens without them.
- **Consent at sign-up:** a tick box: "I am the parent or guardian of this child, and I agree to the Privacy Notice for myself and my child." No account without it.
- **Spelling trial:** collects no name or email; only the anonymous answers of the trial. The Privacy Notice link is still shown.
- If the Notice changes in a way that matters, parents are emailed before it takes effect.
- A Malaysian lawyer writes or checks the final English and Bahasa Malaysia text before launch, including whether a Data Protection Officer must be named.

## Keeping and deleting data
- Children's answers are private: only Admin sees them, and the model reads them only to mark them. (Open results files are used only on preview pages, never in the product.)
- A child's work is kept while their plan runs and for 12 months after it ends, then deleted. Only counts with no names or answers stay, for the Numbers tab.
- A parent can delete their account and data from the parent page ("Delete my account and data", confirmed with an email code; see `parents-support-and-reviews.md`). Admin finishes it on the Parents tab within 21 days and the parent is told by email. Payment records stay (see `plans-and-payment.md`).
- Receipts and payment records are kept 7 years. Only Admin can open them, and receipt pictures open only through links that expire after a few minutes.
- Review videos are kept until the parent withdraws consent, then taken down and deleted within 21 days.
- Every night the database is copied, locked (encrypted), to a private store separate from the website, and copies are kept 30 days. Once a month a copy is restored into a test database to prove it works.

## Out of scope
Malay text (a Bahasa Malaysia version of the Terms and Privacy Notice is required; see `plans-and-payment.md`). A phone app. Schools and teachers.

## Open questions
None.
