# Brief: Writing Confidence (reply to an invitation)

<!-- project-lead-Opus5.5-agent, 2026-10-05. DRAFT for the owner's re-approval. Rewritten from the approved brief of 2026-10-04 with every decision of
     2026-10-04 and 2026-10-05. Shared parts moved to their own briefs (one fact, one place). History: specs/decisions/writing-confidence.md. -->

Words follow `specs/glossary.md`. Every-page rules: `site-rules.md`. Sign-up: `accounts-and-sign-in.md`. Trials, plans and payment: `plans-and-payment.md`. Admin's screens: `admin-page.md`. Parent page, reports and emails: `parents-support-and-reviews.md`. Every number marked (TS) is a Teaching setting; its value lives only in `admin-page.md`.

## Who it's for
A Malaysian child aged 10 (Year 4), learning English, writing at home on a phone, and the parent who signs them up. The goal is to communicate so the other person understands; a 50-word task needs no complex sentences.

## The problem
Children rarely get to practise short writing with a teacher beside them. Free worksheets give no help while writing and no feedback after. Parents can't tell whether the answer was good or what to fix.

## What should happen

### The task
- Each task is an invitation: "Your friend invites you to join her to go to the beach. Would you like to go? Give TWO reasons." The person, the place, the occasion and the wording change from task to task.
- The child writes about 50 words. Both yes and no answers are fine. A hint shows how to start, in the owner's wording: "Yes, I would like to go to {place} because…" or "No, I don't want to go to {place} because…".
- A set is 3 tasks, one at a time. After the 3rd task, the set is done and the child can start the next set.

### Start screen
- "Writing Confidence", then two choices: **1 Fun mode** (help while writing) and **2 Exam mode** (just like the test paper, marked at the end).
- A Stronger child also sees a gentle "Ready to try Exam mode?".

### Which sets a child gets
- Admin's content has fixed sets of 3 tasks, in a fixed order (drafted by the lead under the owner's model-answer rules, live at launch, reviewed by Admin afterwards).
- Children do the sets in order: set 1, 2, 3…
- No set repeats until the child has done every set. Then the sets with the fewest stars come back first.
- Exam mode has its own sets, so a child never sits an exam on a task they have practised.
- Trial sets are fixed and separate (see `plans-and-payment.md`).
- Daily limit on new sets (TS), see `site-rules.md`.

### Fun mode: while writing
- **Paper:** the standard paper, or the Guided paper for a Weaker child (a sentence starter printed on each line: the opening, reason 1, reason 2 with a suggested starter, and the thank-you line).
- **Three checks** tick while the child writes: **Yes / No**, **2 reasons**, **About 50 words**.
  - *Yes / No* ticks when the answer starts with yes or no, or says "I would like to go" / "I don't want to go".
  - *2 reasons* counts reasons only in **finished sentences** (ending in . ! or ?). A reason is "because" with 3 or more words after it; a second idea joined by "and I/it/we…" after because; a sentence with an accepted starter; or, with no linking word at all, any later finished sentence of 3 or more words that isn't a closing line ("Thank you…", "Can we… instead?", "Maybe…"). When both reasons have no linking word, the tick still comes, with a note inviting the child to join them with a suggested starter.
  - *About 50 words* ticks inside the word range (TS). Above it, the box shows a caution icon and a note says about 50 words is enough. Words are counted so that "don't", "ice-cream" and "11" are one word each.
  - The ticks are a guide. The model's marking at Submit is final.
- **Teacher notes:** one short, kind note at a time, picked instantly by what the child has written so far (no yes/no yet, no reason yet, one reason, short, ready). The owner's lines, in the database. A note never gives the answer away.
- **Help me** appears after the Help time (TS) with no typing while the three checks are not all ticked, counted from when the task opens too. Once it appears it stays for that task. Tapping it shows:
  - the idea words: Yes ideas if the child has written yes, No ideas if no, both (labelled) if neither;
  - the suggested starters.
- **Long-sentence nudge (Weaker only):** when a sentence reaches the length (TS) with no full stop, one kind question, picked at random from the owner's lines, invites the child to put a full stop. It shows once per sentence with a soft yellow highlight on the sentence (never red), disappears at the full stop and doesn't repeat.
- **Pasting is turned off** in the answer box.
- Each try records whether Help me appeared and whether it was opened, so Admin can tune the Help time with real data (Answers tab and Numbers).
- Screen readers read out the ticks and teacher notes politely, and the lined paper stays lined up with large text turned on.
- The child can submit a short answer. Nothing blocks them; the checks stay unticked and the feedback says what's missing.
- Answers are saved as the child types, so nothing is lost if the page closes or the internet drops.

### Exam mode
- Looks like the test paper: "WRITING", "Question 1 of 3", the invitation in a box, ruled lines with handwriting-style typing, and only a word count.
- No ticks, no notes, no Help me, no timer.
- The child moves freely between the 3 questions (numbered circles, Back, Next).
- "Finish paper" asks "Finish your paper? No / Yes" and warns about any empty question.
- "Your teacher is marking your paper", then all 3 answers come back marked at once, in green pen: Yes/No circled, linking words underlined, mistakes with a wavy line, the marking list, the stars, the feedback and the model answers.

### Feedback and marking (both modes)
- The model writes warm feedback for the child's own answer, through the owner's server, following the owner's feedback rules and corrections (in the database): what they did well and one thing to try next time. Kind, short, at the child's level, and never a rewrite of the whole answer.
- Every feedback passes a child-safety check before the child sees it. Anything that fails is replaced by the owner's fixed line.
- While it's being written the child sees "Your teacher is reading your answer". If it takes longer than the wait (TS) or fails, the owner's fixed line shows. The child is never stuck.
- **The marking list:** Answers the question (Yes / No) · Gives two reasons · About 50 words · Capital letters and full stops.
  - **Who decides each row:** *Yes / No* and *About 50 words* use the same rules as the ticks, so they always match what the child saw. *Gives two reasons* and *Capital letters and full stops* are decided by the model.
  - When the model disagrees with a tick the child saw, the feedback explains it kindly (for example, that the second idea is a nice detail and could become a reason with "because").
  - The model returns its marking in a fixed format that is checked before use. If it is missing or broken, all four rows come from the rules and the feedback is the owner's fixed line, so the child always gets a full marking.
- **Stars:** 3 when all four pass; 2 with yes/no, at least one reason and 30 or more words; otherwise 1.
- **Nothing written means nothing marked as correct:** an empty answer gets 0 stars and every row says "No answer". Capital letters and full stops pass only when something with a full stop was written.
- "The second reason is because…" is never marked down: it counts as a reason, passes, and the feedback never corrects it (the model answers use "…is that…").
- For Average and Stronger children, a long sentence is only commented on when it has mistakes in it (a kind suggestion to split it). For Weaker children, the marking also suggests one idea in each sentence.
- **Copied model answer:** an answer with 8 in 10 of its words the same, in the same order, as any model answer gets a kind "try writing it in your own words", no stars, and is flagged for Admin.
- **Unkind words** (rude or hurtful words about a person; disliking a place, like "I hate the zoo", is fine): the child-safety check reads the child's answer too. The child gets a fixed kind line, and the answer is flagged for Admin. Nothing is sent to the parent automatically.
- Every feedback is saved with what the child saw (Answers tab).

### Model answers
- Each task has four model answers in the database: Yes and No, each in a **default** version (for strong writers; its opening sentence carries reason 1 and is long on purpose) and a **short-sentence** version (short sentences, one idea in each, reason 2 with a suggested starter). The owner's model-answer rules for both versions are private teaching content.
- After feedback the child sees the model answer that matches their choice (Yes or No), with a switch: **Model answer | Short sentences**. A Weaker child sees Short sentences first; others see Model answer first.

### Placement (behind the scenes)
- Everyone starts as Average. The first set places the child; after that, the last few sets (TS) decide, so a child who improves isn't held back by old results.
- **Weaker** → Guided paper, long-sentence nudge, short model answer first. **Average** → standard paper. **Stronger** → standard paper plus "Ready to try Exam mode?".
- A level changes only when two sets in a row point the same way (TS), so one bad day doesn't move a child. Exam mode results count too.
- No level name is ever shown to the child or parent. Admin sees and can reset placement (Parents tab).

## Worked examples

**About 50 words** (range 45–55)
| Words | Box | Note or feedback |
|---|---|---|
| 44 | empty | write a little more |
| 45 | ticked | – |
| 55 | ticked | – |
| 56 | caution icon | about 50 words is enough |

**2 reasons**
| The child has typed… | Reasons | Tick |
|---|---|---|
| "No, I don't want to go to the zoo because" | 0 | no |
| "…because it is far" (no full stop yet) | 0 | no |
| "…because it is far." | 1 | no |
| "…far. I don't like hot places." | 2 | yes, with the "join them" note |
| "…because I love swimming and I want to build a sandcastle." | 2 | yes |
| "…because it is fun and nice." | 1 (one reason, two describing words) | no |
| "…far. Thank you." | 1 ("Thank you" is a closing line) | no |

**Stars**
| Answer | Stars |
|---|---|
| empty | 0, every row "No answer" |
| "Yes." | 1 |
| yes, two reasons, 41 words, a lowercase "i" | 2 |
| yes, two reasons, 49 words, capitals and full stops right | 3 |

**Help me** (Help time 6 seconds): the child stops typing with one check unticked → after 6 seconds Help me appears and stays until the task is submitted.

**Placement:** a Weaker child's last 3 sets average 2.1, then 2.3 after the next set → two sets in a row point to Average → the next set is on the standard paper.

## When things go wrong
| Situation | What happens |
|---|---|
| The internet drops while writing or submitting | Writing goes on; the answer waits on the phone and sends itself later; feedback comes when the internet is back |
| The same child on two phones | See `accounts-and-sign-in.md` |
| The model is slow or fails | The owner's fixed line after the wait (TS) |
| Trial or plan ends mid-set | See `plans-and-payment.md` |
| Copied model answer, unkind words | See Feedback and marking above |

## Out of scope
Other kinds of writing (emails, stories). Redrafting an answer after feedback. A timer. Spelling answers on the Answers tab.

## Anything to match
The approved teaser (v4) and the approved Exam mode mock (kept privately). Everything in `site-rules.md` (name, look, icons, selection).

## Open questions
None.
