# Brief: Next sheet built from mistakes

<!-- content-writer-Opus5.5-agent, 2026-10-03. DRAFT v2. Follows do-a-sheet.md. Owner has not approved. Not committed. Rebuilt around eliciting (CELTA): the sheet draws the answer out and never just tells it. Mock board: docs/worksheets/mocks/seven-ideas-board.html. Numbers marked (lean) wait for the owner. -->

## Who it's for
The same Year 4 child (about 10) in Malaysia who has already done at least one sheet (see `do-a-sheet.md`), at home with a parent.

## The problem
After the first sheet, the child's answers are saved against named skills, but nothing uses them. Every child would get the same next sheet, and a child who gets something wrong is only told the answer, never helped to find it.

## The idea in one line
Draw the answer out of the child, never just tell it (CELTA eliciting), and shape each week's sheet from both their right and wrong answers. Same shape as a CELTA test → teach → test lesson: the sheet tests, eliciting teaches, spread-out questions test again.

## What should happen

### On the sheet (the child sees this)
- **Show me where.** After picking an answer, the child taps the sentence in the text that proves it. (Idea 1)
- **A question back.** When the sheet is marked, each wrong answer gets one short question that leads the child to spot their mistake (for example, "Is that in the whole text, or only one part?"), then one more try. The right answer shows only after that second try. (Idea 2)
- **Hints on the retry.** The retry item at the end offers hints one at a time, smallest first: where to look, then which sentence, then how to do it. (Idea 5)
- **Work out the rule.** Every sheet has one short example where the child answers two tiny questions and finds a reading rule themselves. The rule is only said after they find it. Every child gets one, so it never hints the sheet was made for them. (Idea 3)
- **Nudges that shrink.** Practice on a weak skill starts with a nudge ("Look at paragraph 2"). Each time the nudge gets smaller, until there is none. (Idea 4)

### Between sheets (behind the scenes)
- **Slip or error.** One miss on a skill might be a slip: the next sheet gives one more question on that skill, on a different text. Only a skill missed twice, on different texts, is treated as an error and gets the rule example and nudged practice. (Idea 7)
- **Spread out and mixed.** A weak skill comes back a little at a time, about 1, 2 and 4 weeks later, mixed in with other skills, never crammed into one sheet. (Idea 6)

### How right and wrong answers change next week

| What the child did | What changes next week |
|---|---|
| Wrong once | One more question on that skill, on a different text |
| Wrong twice, on different texts | Error: rule example + nudged practice; level steps down if needed |
| Right, but only after hints or the question back | Noted, not counted as fixed; skill comes back soon |
| Right, no hint, new question | Counts towards fixed; skill comes back less often |
| Right, no hint, on 2 different days | Fixed; skill comes back only now and then |
| Several right in a row on a skill | Questions on that skill step up a level |

### Always true
- The sheet is set so the child gets about 8 in 10 right (lean).
- The child never sees a level, a score, or any sign that sheets are changing. Every sheet looks the same.
- A child never sees the same question twice, except the retry item.
- Everything else from `do-a-sheet.md` stays: marked at once, one thing done well, one thing to try, one retry item, no timer, no streaks, no reward.

## Build in two steps
- **Step A (first):** show me where, a question back, hints on the retry, slip or error. These work from week 1.
- **Step B (after a few weeks of use):** work out the rule, nudges that shrink, spread out and mixed. These need a few weeks of a child's history.

## Sheet shape (lean)
- 10 questions per sheet: 5 short reading texts, 2 questions each (never more than 2 per text).
- About 4 questions on skills that are due back or weak, 6 on other skills (keeps the mix and the 8-in-10 aim).
- Levels behind the scenes: A1 (easier), A1/A2 (main), A2 (harder). Every child starts at A1/A2.

## What the app keeps
- Every answer: child, question, answer picked, right or wrong, sentence tapped, hints used, date.
- One line per child per skill: where it stands (new, maybe a slip, error, practising, fixed), its level, and the week it is due back.
- The next sheet is picked by a short written set of rules from those lines. No AI, and no paths drawn by hand.
- Each set of rules has a version number, so we know which rules made which sheet, and can go back.
- Before real children see a rule change, pretend children (strong, weak, careless) run 10 weeks of sheets to check nobody gets stuck and most get about 8 in 10 right.

## Question bank
- Every question has: one skill, one level, the proof sentence, one question back for each wrong option, and 2–3 hints (the first hint is also the nudge).
- One "work out the rule" example per skill per level (21 in all).
- The 7 reading skills: gist, specific information, detail, inference, word from context, reference, writer's purpose.
- With 500 children, a question almost everyone gets wrong is flagged for the owner to check.
- Questions are stored in the database only, never in git. Working copies live in `docs/worksheets/` (private).

## Changes this needs in `do-a-sheet.md`
- "Correct answers show only after submitting, never before" → correct answers show after submitting **and after one question back and one more try**.
- The retry item gains hints, one at a time. An answer after a hint is saved as "with help", not as a first sign.

## Out of scope
The parent's progress view. Skills other than reading. Written answers. Any year but Year 4. Malay text. Schools and teachers.

## Anything to match
Same look and feel as `do-a-sheet.md`: calm, plain, phone-first, nothing childish, no game features.

## Decisions (owner, 2026-10-03)
- First version: the weekly loop for reading. It adjusts on both wrong and right answers.
- Used by parents at home. No schools or teachers in this version.
- The owner (a CELTA-certified teacher) owns and signs off the learning rules.
- A website that works on phones. No app-store app.
- The gold standard is the approach closest to CELTA eliciting: all 7 ideas, built in two steps.
- A wrong answer gets one question back and one more try before the right answer shows.

## Open questions
1. How many questions per sheet? Lean: 10 (5 texts × 2).
2. How do due/weak and other skills split? Lean: about 4 due/weak, 6 other.
3. When does a child move to an easier or harder level for a skill? Lean: easier after it is marked an error twice; harder after 3 right in a row, no hint, on new questions.
4. What happens if a skill runs out of new questions at a level? Lean: borrow from the closest level, never repeat.
