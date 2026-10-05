# Brief: Site rules (every page)

<!-- project-lead-Opus5.5-agent, 2026-10-05. DRAFT for the owner's re-approval. NEW shared brief, added during the rewrite so that
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
- Every "day" is a Malaysia-time day (see the glossary): trial days, daily limits, active days, plan start and end dates.

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

## Keeping and deleting data
- Children's answers are private: only Admin sees them, and the model reads them only to mark them. (Open results files are used only on preview pages, never in the product.)
- A child's work is kept while their plan runs and for 12 months after it ends, then deleted. Only counts with no names or answers stay, for the Numbers tab.
- A parent can ask (through Report an issue) for everything to be deleted. Admin clicks "Delete this family" on the Parents tab; it is done within 21 days and the parent is told by email. Payment records stay (see `plans-and-payment.md`).
- Receipts and payment records are kept 7 years. Only Admin can open them, and receipt pictures open only through links that expire after a few minutes.
- Review videos are kept until the parent withdraws consent, then taken down and deleted within 21 days.
- Every night the database is copied, locked (encrypted), to a private store separate from the website, and copies are kept 30 days. Once a month a copy is restored into a test database to prove it works.

## Out of scope
Malay text (a Bahasa Malaysia version of the Terms and Privacy Notice is required; see `plans-and-payment.md`). A phone app. Schools and teachers.

## Open questions
None.
