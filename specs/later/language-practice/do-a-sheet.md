# Brief: Do a sheet

<!-- scaffolder-sonnet5.5-agent, 2026-09-29. DRAFT, rewritten from the updated docs/uploads/first context.md. Owner has not approved. Not committed. -->

## Who it's for
A child in Year 4 (about 10) in Malaysia, and the parent who sets them up. The product is for ages 10 to 12 (Years 4 to 6); this first feature covers Year 4 only.

## The problem
Free worksheets have no answer key and no memory. Nobody records which skills a child keeps getting wrong, so nothing can be built around them.

## What should happen
- A parent signs up with an email code, no password, and adds one child. The child signs in with a code the parent gives them. Everyone stays signed in for months on a shared phone.
- The child does one sheet a week, in portrait on a phone. This feature delivers the first sheet: pick-an-answer and fill-in-the-blank questions only. It is never called a test.
- The order of questions and answer options is shuffled for each child.
- If the connection drops midway, the answers so far are kept.
- When the child submits, the sheet is marked at once. Correct answers show only after submitting, never before.
- The child then gets three things: one thing done well, one thing to try, and one retry item, a question they missed, offered again straight away.
- There is no score to beat, no timer, no streaks, no ranking, no reward, and no level. Nothing on screen hints that later sheets will change.
- A retry item answered correctly is saved as a first sign only, never as fixed. One right answer could be memory or luck. (Later, a skill counts as fixed after two correct answers on new items, on different days, with no hint. That rule belongs to a later feature.)
- Every wrong answer is saved against a plainly named skill, for that child. This record is the point of the feature, even though the parent can't see it yet.

## Out of scope
Written answers. Photographing a sheet. The parent's progress view, including the side-by-side writing samples. Sheets built from mistakes. Payment. A second child. Any year but Year 4. Malay text.

## Anything to match
The first sheet's questions are supplied by the owner. They are stored in the database only and never saved into git.

Calm, plain, low-chrome. Mobile first at 360px on a mid-range Android with patchy data. No gamification of any kind. Cannot look juvenile: the oldest users are 12.

## Open questions
None.
