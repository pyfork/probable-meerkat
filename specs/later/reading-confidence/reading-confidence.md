# Brief: Reading Confidence

<!-- project-lead-Opus5.5-agent, 2026-10-05. DRAFT. Owner has not approved. Merged from the two earlier drafts, "Do a sheet" (2026-09-29) and
     "Next sheet built from mistakes" (2026-10-03), so every fact is in one place. Content only merged, not added to. History: specs/decisions/reading-confidence.md. -->

Words follow `specs/glossary.md`. Every-page rules: `site-rules.md`. Sign-up: `accounts-and-sign-in.md`. Numbers marked (lean) wait for the owner; when this product is picked up, they become Teaching settings in `admin-page.md`.

## Who it's for
A Malaysian child aged 10 (Year 4), doing a reading sheet at home on a phone, and the parent who signs them up. The product is for ages 10 to 12 (Years 4 to 6); this first version covers Year 4 only.

## The problem
Free worksheets have no answer key and no memory. Nobody records which skills a child keeps getting wrong, so nothing is built around them, and a child who gets something wrong is only told the answer, never helped to find it.

## The idea in one line
Draw the answer out of the child, never just tell it (CELTA eliciting), and shape each week's sheet from both their right and wrong answers. Same shape as a CELTA test → teach → test lesson: the sheet tests, eliciting teaches, spread-out questions test again.

## What should happen

### Signing up
As in `accounts-and-sign-in.md`: the parent signs up with an email code and adds one child, and the child uses the parent's phone.

### The sheet
- One sheet a week, in portrait on a phone. It is never called a test.
- Pick-an-answer and fill-in-the-blank questions only.
- The order of questions and answer options is shuffled for each child.
- If the connection drops midway, the answers so far are kept.
- **Show me where.** After picking an answer, the child taps the sentence in the text that proves it.
- There is no score to beat, no timer, no streaks, no ranking, no reward, and no level. Every sheet looks the same; nothing on screen hints that sheets change.

### Marking and the question back
- When the child submits, the sheet is marked at once.
- Each wrong answer gets one short **question back** that leads the child to spot their mistake (for example, "Is that in the whole text, or only one part?"), then one more try.
- The right answer shows only after that second try, never before.
- The child then gets three things: one thing done well, one thing to try, and one retry item.

### Retry item and hints
- The retry item is a question the child missed, offered again straight away.
- It offers hints one at a time, smallest first: where to look, then which sentence, then how to do it.
- Right without a hint is saved as a first sign only, never as fixed (one right answer could be memory or luck). Right after a hint is saved as "with help".

### Work out the rule
Every sheet has one short example where the child answers two tiny questions and finds a reading rule themselves. The rule is only said after they find it. Every child gets one, so it never hints the sheet was made for them.

### Nudges that shrink
Practice on a weak skill starts with a nudge ("Look at paragraph 2"). Each time the nudge gets smaller, until there is none.

### Remembering skills (for each child)
- Every answer is saved against a plainly named skill, for that child. This record is the point of the product, even though the parent can't see it yet.
- **Slip or error.** One miss on a skill might be a slip: the next sheet gives one more question on that skill, on a different text. Only a skill missed twice, on different texts, is an error and gets the rule example and nudged practice.
- **Spread out and mixed.** A weak skill comes back a little at a time, about 1, 2 and 4 weeks later (lean), mixed in with other skills, never crammed into one sheet.

| What the child did | What changes next week |
|---|---|
| Wrong once | One more question on that skill, on a different text |
| Wrong twice, on different texts | Error: rule example + nudged practice; level steps down if needed |
| Right, but only after hints or the question back | Noted, not counted as fixed; skill comes back soon |
| Right, no hint, new question | Counts towards fixed; skill comes back less often |
| Right, no hint, on 2 different days | Fixed; skill comes back only now and then |
| Several right in a row on a skill | Questions on that skill step up a level |

- A child never sees the same question twice, except the retry item.

### Sheet shape
- The sheet is set so the child gets about 8 in 10 right (lean).
- 10 questions per sheet: 5 short reading texts, 2 questions each, never more than 2 per text (lean).
- About 4 questions on skills that are due back or weak, 6 on other skills (lean).
- Levels behind the scenes: A1 (easier), A1/A2 (main), A2 (harder). Every child starts at A1/A2.

### What the app keeps
- Every answer: child, question, answer picked, right or wrong, sentence tapped, hints used, date.
- One line per child per skill: where it stands (new, maybe a slip, error, practising, fixed), its level, and the week it is due back.
- The next sheet is picked by a short written set of rules from those lines. No AI, and no paths drawn by hand.
- Each set of rules has a version number, so we know which rules made which sheet, and can go back.
- Before real children see a rule change, pretend children (strong, weak, careless) run 10 weeks of sheets to check nobody gets stuck and most get about 8 in 10 right.

### Question bank
- The 7 reading skills: gist, specific information, detail, inference, word from context, reference, writer's purpose.
- Every question has: one skill, one level, the proof sentence, one question back for each wrong option, and 2–3 hints (the first hint is also the nudge).
- One "work out the rule" example per skill per level (21 in all).
- With 500 children, a question almost everyone gets wrong is flagged for the owner to check.
- Questions are supplied by the owner and stored in the database only, never in git.

## Build in two steps
- **Step A (first):** the sheet, marking, show me where, the question back, the retry item with hints, slip or error, and saving every answer against its skill. These work from week 1.
- **Step B (after a few weeks of use):** work out the rule, nudges that shrink, spread out and mixed. These need a few weeks of a child's history.

## Out of scope
Written answers. Photographing a sheet. The parent's progress view, including side-by-side writing samples. Skills other than reading. Payment. A second child. Any year but Year 4. Malay text. Schools and teachers.

## Anything to match
Calm, plain, low-chrome. Mobile first at 360px on a mid-range Android with patchy data. No game features of any kind. Cannot look childish: the oldest users are 12. Everything in `site-rules.md`.

## Open questions
1. How many questions per sheet? Lean: 10 (5 texts × 2).
2. How do due/weak and other skills split? Lean: about 4 due/weak, 6 other.
3. When does a child move to an easier or harder level for a skill? Lean: easier after it is marked an error twice; harder after 3 right in a row, no hint, on new questions.
4. What happens if a skill runs out of new questions at a level? Lean: borrow from the closest level, never repeat.
