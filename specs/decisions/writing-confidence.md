# Decisions: Writing Confidence

<!-- project-lead-Opus5.5-agent, 2026-10-05. History only. The brief (specs/features/writing-confidence.md) holds today's rules; build from the brief, never from here.
     "Replaced" means a later decision changed it. "Moved" means the rule now lives in another brief. -->

## 2026-10-03 to 2026-10-04 (questions 1–24 of the first brief)
1. How is the feedback made? The model writes feedback for each answer through the owner's server, with child-safety checks. (2026-10-03)
2. What ages? Age 10 only for now (Year 4). KPM is the floor; the level target above it stays private. (2026-10-04)
3. How does the product help a stuck child? Idea words for each task, and feedback plus a model answer after submitting. Short answers can still be submitted. No redraft. (2026-10-04)
3a. When do the idea words show? Help me after 2 minutes stuck. (2026-10-04) **Replaced** by the Help time Teaching setting: 25 s, then 9 s, then **6 s** (2026-10-05).
4. What happens after the trial? Pay RM59 for 12 months by QR and send the receipt; the owner verifies and activates. (2026-10-03) **Replaced** by 22 (plans) and **moved** to plans-and-payment.
5. How does the owner add bank payments? By hand on the Verify tab (the bank has no download). (2026-10-03) **Moved** to admin-page.
6. Can the child keep writing while a payment is checked? Yes, up to 2 days after the trial ends. (2026-10-04) **Moved** to plans-and-payment.
7. Can the parent pay before the trial ends? Yes; the plan starts on activation. (2026-10-04) **Moved** to plans-and-payment.
8. Should a verified payment activate by itself? No: Confirm on Verify, then Activate. (2026-10-03) **Moved** to admin-page.
9. Can a click be undone? Activate has a 30-second Undo (bulk too); Confirm has a short Undo. (2026-10-03) **Moved** to admin-page.
10. Later gold standard: a payment service that confirms DuitNow payments by itself. Out of scope for now.
11. Who writes the nudges? The owner's fixed lines, picked by what the child has written. The model writes only the feedback. (2026-10-03)
12. Should the owner see feedback before the child? No approval first; the owner can flag and correct, and the model follows corrections. (2026-10-04) The Feedback tab is **replaced** by the Answers tab (2026-10-05), **moved** to admin-page.
13. Where do reports go? A Reports tab plus an email. (2026-10-04) **Moved** to admin-page.
14. Parent check before Support? Not at launch. (2026-10-04) **Moved** to parents-support-and-reviews.
15. Where are reviews approved? A Reviews tab. (2026-10-04) **Moved** to admin-page.
16. When is the parent asked for a review? Activation email, the parent page after the 5th set, the 23-day email. (2026-10-04) **Moved** to parents-support-and-reviews.
17. What is an active day? A day the child submits at least one task. (2026-10-04) **Moved** to the glossary (now covers spelling too).
18. Product name? "Puascari's Learn English". (2026-10-04) **Replaced** by 22: "Learn English at Puascari.com". **Moved** to site-rules.
19. A small parent page? Yes. (2026-10-04) **Moved** to parents-support-and-reviews.
20. Refunds? Started month counts as used; full months left, minus 5%, within 14 days. (2026-10-04) **Replaced** in part by 22 (30 days). **Moved** to plans-and-payment.
21. Owner's business details for the Terms page. **Given privately** by the owner (2026-10-05). They go on the Terms page only, never in this repository. No phone number; parents use Report an issue and the support email.
22. Plans, prices and names at launch: two products; RM59/12 months (with Spelling) or RM45/6 months; Spelling alone RM39/RM29/RM11; refunds within 30 days. (2026-10-04) **Moved** to plans-and-payment.
23. Writing trial limit: 2 fixed sets a day for 3 days. (2026-10-04) **Moved** to plans-and-payment.
24. Sign-up and sign-in: a 6-digit email code, no password. (2026-10-04) **Moved** to accounts-and-sign-in.

## 2026-10-05 (brief upgrade, walked with the owner)
- Fun mode and Exam mode, named the same as Spelling. Exam mode approved from the mock.
- Three checks: 45–55 words tick, caution above; reasons count only in finished sentences, with or without linking words; the tick is a guide, the model's marking is final.
- Marking: nothing written means nothing marked as correct.
- Suggested starters on screen: two, owner's list. Accepted starters: a longer list behind the scenes. "…is because…" never marked down.
- Model answers: default (long opening kept for strong writers) and short-sentence versions; Weaker children see short first.
- Placement: everyone starts Average; the first set places; a window of recent sets; change after 2 sets in a row; Admin can reset.
- Long-sentence nudge for Weaker children only, kind questions picked at random, once per sentence, soft yellow highlight.
- Task order: sets in order, no repeats until all done, lowest stars back first, separate exam sets; the lead drafts sets, Admin reviews after launch.
- Copied model answers and unkind words: kind fixed line, flagged for Admin.
- Pasting turned off. Offline: writing goes on and answers send later.
- Launch content: 2 trial sets, 60 Fun sets, 12 Exam sets.
