# Brief: Write a reply to an invitation

<!-- project-lead-Opus5.5-agent, 2026-10-03. DRAFT from the writing spike and the approved teaser (v4). Owner has not approved. -->

## Who it's for
A child learning English at A1–A2 level, writing at home on a phone, and the parent who signs them up.

## The problem
Children rarely get to practise short writing with a teacher beside them. Free worksheets give no help while writing and no feedback after. Parents can't tell whether the answer was good or what to fix.

## What should happen
- A parent starts a free 3-day trial and adds one child. The child can start writing straight away on the parent's phone or computer.
- The child does a set of 3 short tasks, one at a time. Each task is an invitation: "Your friend invites you to join her to go to the beach. Would you like to go? Give TWO reasons." The person, the place and the wording change from task to task.
- The child writes about 50 words on lined paper. A hint shows how to start: "Yes, I would like to go to {place} because…" or "No, I don't want to go to {place} because…". Both yes and no answers are fine.
- While the child writes, three checks tick on: Yes / No, 2 reasons, about 50 words.
- A teacher voice gives one short note at a time: a hint to start, then small nudges ("Use because…", "Try Also,…"). Each nudge is short and kind and never gives the answer away.
- After each task, the child gets warm feedback: what they did well, and one thing to try next time.
- After the 3rd task, the set is done. The child can start a new set.
- Answers are saved, so nothing is lost if the page closes.
- Calm and simple. No timer, no score to beat, no ranking.

## Out of scope
Payment after the trial. A second child. Other kinds of writing (emails, stories). A parent progress page. Malay text. Schools and teachers. The reading sheets, which are a separate later product (`specs/later/language-practice/`).

## Anything to match
The approved teaser (v4): a calm, light page, with the retro task card (ink border, flat shadow, small Mario-colour touches) and the teacher notes with a smiley. The CTA is "Try 3 days for free". The credit line is "Created by Cikgu Ahmad, a CELTA-certified English teacher." Fonts: Manrope on the page, Nunito on the task card. The prototype is the writing spike (kept privately).

All task text, hints, nudges and feedback lines live in the database, never in the code.

## Open questions
1. How is the feedback made? Lean: fixed checks plus teacher lines the owner writes, for launch. Feedback written for each answer by Claude comes as a later feature, and the teaser is softened so it doesn't promise it.
2. What ages, exactly? Lean: 8 to 12.
3. Can the child submit a short answer? Lean: yes, but the checks stay unticked and the feedback says what's missing. Never block.
4. What happens after the 3-day trial? Lean: decide with payment, which is a later feature.
