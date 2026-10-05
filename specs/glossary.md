# Glossary

<!-- project-lead-Opus5.5-agent, 2026-10-05. DRAFT for the owner's re-approval. One meaning per word, used by every brief in specs/features/.
     Decided by the owner, 2026-10-04 and 2026-10-05 (see specs/decisions/glossary.md). -->

Every brief uses these words with these meanings only. If a brief needs a new word, it is added here first.

## People and places

| Word | Means |
|---|---|
| **Child** | The learner, aged 10 (Malaysian Year 4). One child per account at launch. |
| **Parent** | The adult who signs up, pays and gets the emails. |
| **Admin** | Whoever runs the admin page. Today, the owner. |
| **Admin page** | The private page only Admin can open (see `admin-page.md`). |
| **Parent page** | The small page for parents, reached from a quiet "Parent" link (see `parents-support-and-reviews.md`). |

## Plans and payment

| Word | Means |
|---|---|
| **Plan** | What the parent paid for: the product, its length, a start date and an end date. Saved under the child. |
| **Trial** | The free start before paying. Writing: 3 days, 2 fixed sets a day. Spelling: 3 fixed rounds, no sign-up. |
| **Payment code** | The parent's own code, # and 6 digits, typed in the bank's Reference box. |
| **Verified** | Admin found the payment code in bank account transactions list and clicked Confirm. |
| **Activated** | Admin clicked Activate; the plan starts that day. |
| **Possible double payment** | The same plan for the same child was paid again while it is active or waiting. |
| **Refunds to pay** | The list of refunds Admin still has to send, each with a pay-by date. |

## Time

| Word | Means |
|---|---|
| **Day** | A calendar day in Malaysia time, midnight to midnight. Every "day" in every brief means this. |
| **Active day** | A day with at least 1 writing task submitted or 1 spelling round finished. |

## Both products

| Word | Means |
|---|---|
| **Fun mode** | The mode with help while working. Writing and Spelling both have it. |
| **Exam mode** | The mode that looks like the test paper: no help while working, marked at the end. |
| **Help time** | How long a child is stuck before help appears in Fun mode. A Teaching setting. |
| **Marking** | What the child sees after finishing: ticks and crosses, stars, and the notes. |
| **Teaching settings** | The numbers Admin can change (Help time, word range, limits and so on), listed in `admin-page.md`. |
| **Content** | Everything a child reads, answers or is marked against. It lives in the database, never in the code or this repository. |
| **Needs change** | Admin's mark on a piece of content. It pauses that content for children until it is fixed. |

## Writing Confidence

| Word | Means |
|---|---|
| **Task** | One invitation the child replies to, in about 50 words. |
| **Set** | 3 tasks done one after another. |
| **Idea words** | Help words for one task, split into **Yes ideas** and **No ideas**. Never called "sets". |
| **Suggested starters** | The sentence starters the app offers on screen (two at launch). Owner's list, in the database. |
| **Accepted starters** | Every starter the "2 reasons" tick counts as linked. Never shown. Owner's list, in the database. |
| **Nudge** | A short teacher note while writing, picked by what is written so far. Owner's lines, in the database. |
| **Help me** | The button that appears after the Help time and shows idea words and suggested starters. |
| **Feedback** | What the teacher (or model) says after a task is submitted. |
| **Model (AI)** | The AI that writes feedback. Not the same as a model answer. |
| **Model answer** | The owner's example answer for a task. Each task has four: Yes and No, each in a default and a short-sentence version. |
| **Placement** | Weaker, Average or Stronger, worked out from recent sets. Used only behind the scenes; never shown to the child. |
| **Guided paper** | The writing paper for Weaker children: a sentence starter on each line. |
| **Standard paper** | The writing paper for Average and Stronger children. |

## Spelling Confidence

| Word | Means |
|---|---|
| **Round** | 8 spelling words, like Part 5 of the test paper. Spelling only. |
| **Bonus round** | 3 pick-the-right-spelling questions after a round, if the child qualifies. |
| **Hint** | Help about a word's meaning, never its letters. |
| **Debrief** | The cards after marking that go through each mistake, with Listen. |
| **Box** | Where each word sits for each child (Leitner boxes). Higher box = known better. |
| **Confident words** | A child's words in box 3 or higher. |
| **Word list 1** | The Year 3 and Year 4 Part 5 spelling words. |
| **Word list 2** | 300 harder words that join once word list 1 is mostly confident. |
| **Also right** | Another real word that fits a clue, first letter and boxes, approved by the owner. Counts as right. |
