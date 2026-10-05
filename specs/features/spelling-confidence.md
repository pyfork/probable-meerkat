# Brief: Spelling Confidence

<!-- project-lead-Opus5.5-agent, 2026-10-05. DRAFT for the owner's re-approval. Rewritten from the approved brief of 2026-10-04 (with "also right", 2026-10-05)
     and the decisions of 2026-10-05. Shared parts moved to their own briefs; "How it is built" moved to the plan. History: specs/decisions/spelling-confidence.md. -->

Words follow `specs/glossary.md`. Every-page rules: `site-rules.md`. Sign-up: `accounts-and-sign-in.md`. Trial, plans and payment: `plans-and-payment.md`. Admin's screens: `admin-page.md`. Parent page and emails: `parents-support-and-reviews.md`. Every number marked (TS) is a Teaching setting; its value lives only in `admin-page.md`.

## Who it's for
A Malaysian child aged 10 (Year 4), practising spelling at home on a phone, and the parent who signs them up.

Level: the KPM Year 4 standard is the floor; word list 1 covers it and word list 2 goes above it.

## The problem
Part 5 of the Year 4 English paper tests spelling: a clue, the first letter, one space per letter, 8 words. Children practise from long printed word lists with no feedback and no help remembering. Words they get wrong are rarely seen again at the right time, and the list runs out with nothing harder after it.

## What should happen

### Start screen
- Header: "Learn English at Puascari.com". Title: "Spelling Confidence".
- Line 1: "Spell 8 words per round. Get them right, unlock a bonus round." Line 2: "Ready for today's round?"
- Two choices: **1 Fun mode** ("One word at a time. Qualify for the bonus round!") and **2 Exam mode** ("Just like the test paper, marked at the end").
- No word lists, years, units or levels to choose. The child just starts.

### A round
- 8 words per round, like Part 5. Each word: a clue, the first letter given, one box per letter.
- Every round mixes lengths: 2 short words (up to 5 letters), 4 middle (6–8), 2 long (9 or more).
- Words come from the whole pool, never split by school year or unit.
- Fun mode and Exam mode never share the same words in a sitting. Shuffling the order is not enough.
- No teacher notes and no marking while the child works. Everything is marked at the end, instantly, even with no internet.
- The answer boxes turn off the phone's autocorrect, predictive text, automatic capitals and spell-check underlines, so the phone never spells the word for the child.
- **How a round is filled:** first, words due back (lowest box first, then the longest waiting), with at most a set number of box 1 words (TS) so every round has wins; then new words; always keeping the 2/4/2 length mix. If a length has no due or new word, the next-best word of that length is used.
- **What counts as right:** capital letters and spaces at the ends don't matter. British spelling is right. An American spelling of the right word (for example *color*) counts as right, but the word stays in its box, and the debrief says kindly "In Malaysia we spell it *colour*".
- Daily limit on new rounds (TS), see `site-rules.md`.

### Fun mode
- A card, one word at a time.
- Help: nothing at first. After the Help time (TS) on a word, either the hint shows by itself or a Help button appears (picked at random for each word).
- The hint is about meaning, never letters: a word with the same meaning, a word that goes with it, or its opposite (picked at random). A hint never gives the spelling away.
- Excitement when the child qualifies for the bonus round (animated stars, "You qualify").

### Exam mode
- Looks like the test paper: a minimal, retro page. Questions numbered 25–32; the bonus round is numbered 1–3.
- Typing goes straight in. A chevron marks the current question. Up and Down move between questions, Left and Right between letters.
- Enter asks "Finish Part 5? No | Yes" (and "Mark my paper?" on the bonus page).
- No help of any kind. A rubber-stamp effect when the child qualifies.

### Bonus round
- The last button of the round says "Finish", so nothing is given away.
- The child qualifies with no more than the allowed number wrong (TS). They then choose "Mark my answers only" or "Let's go, bonus round!". Too many wrong: no bonus, straight to marking.
- 3 questions: pick the right spelling from 4 choices. Words the child got wrong in the round come first.
- Wrong choices are near-miss misspellings only, never real words. The child's own mistake is a choice only if it is 1–2 letters off and not a real word.

### Marking and debrief
- After the round (and the bonus round): spelling score, bonus score and stars.
- Each mistake gets a card: what the child wrote, the right spelling, a short tip that names the spelling pattern (for example a double letter, or *-ful* with one *l*) so the child can use it on other words, and a Listen button. Tips are the owner's content, in the database.
- A mistake that is a real word (right meaning, wrong word) gets a meaning note instead of a spelling tip.
- Listen plays one simple sentence with the word, read twice; the second reading stresses the word. Always recorded voices, never a computer voice made on the spot.
- Two recorded voices (British, one female, one male) take turns from card to card. Each debrief starts with a random one. Children never choose a voice.
- Words spelled right are listed under "You spelled these right".
- **Also right:** a word can have a short list of other answers that truly fit its clue, first letter and number of boxes, approved by the owner. A correctly spelled "also right" answer counts as right in both modes (score and bonus qualifying). Its card says "{answer} is right too! The word we were thinking of is {word}", with the Listen sentence for the target word.
- Then: "Practise these words again" or "Next task".

### Remembering words (for each child)
- Every word the child meets sits in one of 5 boxes for that child (Leitner boxes). New words start in box 1. The child never sees the boxes.
- **Right:** up one box. **One letter wrong, missing or extra** (a near miss): down one box, never below box 1. **A bigger mistake:** back to box 1. **Right with a hint, an "also right" answer, or an American spelling:** stays in the same box.
- Only the **first try** of a word in a Fun or Exam round moves its box. "Practise these words again" rounds are practice and don't move boxes.
- The higher the box, the longer before the word comes back (return times: TS). The worked example below uses the defaults.
- A word that comes back shows a different clue and sentence when one exists. Each word has up to 3 versions; the original always comes first.
- A child's old answers always show the clue and sentence they actually saw.

### Word list 1 and word list 2
- **Word list 1:** the Year 3 and Year 4 Part 5 spelling words (about 160). Never changed unless the owner asks.
- **Word list 2:** 300 harder words, approved by the owner. Same task: clue, first letter, boxes, the same length mix and bonus round.
- **When word list 2 starts:** when the child has met every list 1 word and enough of them are confident (TS).
- **After it starts:** rounds mix the lists (TS, 30 : 70 list 1 : list 2): across every 5 rounds, 12 list 1 words and 28 list 2 words; each round has 2 or 3 list 1 words, weakest first.
- **Invisible to the child:** no "list 2", "level up" or level name anywhere. The words simply get harder.
- The owner can add more lists later the same way.

### For parents
- No spelling progress page. Spelling lines go in the 23-day email (see `parents-support-and-reviews.md`): words practised, confident words, words still to practise.

## Worked examples

**Bonus round** (qualify with up to 4 wrong out of 8)
| Wrong | Bonus round? |
|---|---|
| 0–4 | offered: "Mark my answers only" or "Let's go, bonus round!" |
| 5–8 | no; straight to marking |

**Boxes**
| The word… | Box before | Box after |
|---|---|---|
| right | 2 | 3 |
| one letter missing ("butterfy") | 4 | 3 |
| a bigger mistake ("butifly") | 4 | 1 |
| right with a hint | 2 | 2 |
| "also right" answer, or "color" | 3 | 3 |
| right again in "Practise these words again" | 1 | 1 (practice doesn't move boxes) |

**One word over two weeks** ("butterfly")
| Day | What happens | Box | Comes back |
|---|---|---|---|
| Mon | wrong | 1 | next round |
| Mon | right | 2 | after 1 day |
| Tue | right | 3 | after 3 days (now a confident word) |
| Fri | right | 4 | after 7 days |
| next Fri | "butterfy" (near miss) | 3 | after 3 days |

**Filling a round** (at most 3 box 1 words): 5 words are due (4 in box 1, 1 in box 2) → the round takes 3 box 1 words and the box 2 word, then 4 new words, keeping 2 short, 4 middle and 2 long. The 4th box 1 word waits for the next round.

**Word list 2 start** (every list 1 word met; 8 in 10 confident)
| List 1 words met | Confident | List 2 starts? |
|---|---|---|
| all 159 | 120 (75%) | not yet |
| all 159 | 128 (81%) | yes |
| 150 of 159 | 140 | not yet (9 not met) |

**30 : 70** across 5 rounds after list 2 starts: rounds with 3, 2, 3, 2, 2 list 1 words = 12 list 1 words and 28 list 2 words.

## When things go wrong
| Situation | What happens |
|---|---|
| The internet drops in a round | The round, help, bonus and marking all go on; the answers send themselves later |
| A recording won't play | The sentence shows on the card to read, and Listen can be tapped again (never a computer voice) |
| A clue is marked "Needs change" by Admin | The word leaves new rounds until it is fixed |

## Out of scope
Choosing words by year or unit. Choosing a voice. Speaking or handwriting. A spelling progress page. Spelling answers on the Answers tab (later). Lists beyond list 2 (later).

## Anything to match
The spelling spike (kept privately) is the prototype for both modes, the bonus round and the debrief. Everything in `site-rules.md`.

## Open questions
None.
