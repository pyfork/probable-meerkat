# PRD: Learn English at Puascari.com

<!-- project-lead-Opus5.5-agent, 2026-10-20. From docs/claude-pkg/TEMPLATE-PRD.md, by interview with the owner.
     Who, journeys and rules come from the approved specs in specs/features/; this file holds only what they don't say. -->

Words follow `specs/glossary.md`. The detailed rules live in `specs/features/`; this page says what the first version is and how we know it works.

## The problem
Form 2 and Form 3 learners rarely practise English with a teacher beside them: worksheets give no help while they work and no feedback after, so the same mistakes come back and nobody can tell what to fix next.

### Concept checks
1. Is the problem a lack of practice material? → No. It is no help while practising and no feedback after.
2. Is the learner the teen or the parent? → The teen. The parent pays and reads progress.
3. Is the problem passing UASA? → No. It is getting better at English; UASA practice is one path.
4. Do learners at different levels get the same tasks? → No. The band comes from their answers.

## Who has it
| Who | What they need |
|---|---|
| A Form 2 or Form 3 learner in Malaysia (about 13–15), anywhere from A1 to B1 | Short writing practice on a phone, with help while writing, warm feedback after, and tasks at their level with topics for their age |
| The parent or guardian | To sign the learner up safely, and later to pay and see progress without becoming the teacher |
| Admin (the owner, a CELTA-certified teacher) | To see that the AI's feedback is good and safe, fix it when it isn't, and keep costs in check |

## Top three journeys
1. **Learner:** opens the invite link on a phone → does a short starter set that finds their band → writes a set of 3 tasks in Fun mode (the three checks, teacher notes, Help me) → gets marking, stars, feedback and a model answer → comes back the next day for the next set.
2. **Parent:** gets the invite → signs up with an email code, adds the learner's first name and gives consent → the phone stays signed in so the learner just opens the site.
3. **Admin:** invites families → reads the To check list each week (flagged answers, 1-star answers, 10 random answers) → marks each Checked or writes a better feedback with Fix feedback → watches the AI bill against the cost budget.

## How we'll know it works
Read over the 4 weeks of the invited group.

| Measure | Target, in a time window | How it is read | When it is read |
|---|---|---|---|
| Feedback is good | 9 in 10 checked answers need no Fix feedback, over the 4 weeks | Checked vs Fix feedback on the Answers tab (a query) | weekly, and at the end of week 4 |
| Feedback is safe | no unsafe feedback reaches a learner, over the 4 weeks | flagged answers and the 10 random a week, read by Admin | weekly |
| Learners come back | 6 in 10 invited learners are active on 8 or more days in the 4 weeks | active days per learner (a query) | end of week 4 |
| Writing improves | more answers pass "Gives two reasons" in week 4 than in week 1, for the same learners | the marking list rows by week (a query) | end of week 4 |
| The AI rarely fails | the fixed line replaces the AI in fewer than 1 in 20 answers | fixed-line count over answer count (a query) | weekly |
| AI cost stays in budget | see the cost budget below | tokens logged per answer, times the provider's price | weekly |

## Not in the first version
- Payment (DuitNow QR, receipts, Verify and Activate, refunds): safe because the first version is free for invited families; revisit when the invited group has had 4 weeks and prices are set (it is the next feature).
- Form 2–3 prices and plan levels: safe because nobody pays yet; revisit after the invited group's 4 weeks. An agent works out the levels from real use, the owner decides. A level buys a daily set cap and products, never unlimited use.
- Spelling Confidence: safe because it uses no AI, so it isn't the risky part; revisit when Writing has had 4 weeks and meets "Feedback is good".
- Exam mode (UASA practice papers): safe because AI feedback is tested in Fun mode first; revisit when the Form 2 and Form 3 paper formats are confirmed against official sources and Fun mode has had 4 weeks.
- Reading and listening: safe because nothing public promises them yet; revisit when Writing meets its measures.
- The public landing page going live: safe because invited families get a direct link; revisit when payment ships.
- Booking live speaking sessions: safe because there is no spec for it; revisit when the owner writes that spec.
- Parent page, monthly progress email, Report an issue, reviews: safe because Admin knows the invited families and reaches them by email; revisit when payment ships (parent page, reports), and when a learner has 4 weeks of answers (monthly email, once specced).
- The Year 4 product: safe because no Year 4 family is promised anything, and its task shapes serve A1 and A2 teens meanwhile; revisit when Form 2–3 Writing meets its measures.
- Outside Malaysia (other exam modules): safe because Malaysia comes first, by the owner's choice; revisit at 300 paying learners in Malaysia.
- A second child per account: safe because plans are saved under the child, so siblings add cleanly; revisit when 10 parents ask.
- Automatic payment confirmation: safe because checking by hand works at this size; revisit when checking payments takes Admin over 30 minutes a day.
- A second server (99.9% uptime): safe because learners keep working offline through short drops; revisit at 1,000 learners, or after a month below 99.5%.
- Admin's "soon after launch" tabs (`specs/design-order.md` 12–17): safe because Teaching settings keep their defaults and content is checked through To check; revisit when the invited group ends.

## Smallest working version
Writing Confidence in **Fun mode**, free, for **20–30 invited families**:
- Sign-up is open only to emails Admin has invited, with the email code and consent tick of `accounts-and-sign-in.md` and `site-rules.md`.
- A short starter set places the learner in a band (A1, A2, A2+ or B1); the band then moves with their answers and is never shown.
- The Writing Confidence engine as approved: the paper, the three checks, teacher notes, Help me, marking, stars, feedback with the child-safety check and fixed-line fallback, model answers, offline writing. Task lengths and topics follow the band. A1 and A2 sets reuse the Year 4 task shapes with topics rewritten for teens.
- Admin's Answers tab with To check, Checked and Fix feedback, plus the admin sign-in and action log.

It needs a Form 2–3 version of the Writing brief before its child's pages are designed (design area 8).

## Load
| What | At launch | In a year | Where the number came from |
|---|---|---|---|
| Users | 20–30 learners | 300 learners | launch: the invited group; year: the owner's estimate |
| Answers a month | about 1,100 | about 11,000 | 3 answers a session × about 12 days a month (the daily caps are the ceiling, not the norm) |
| Peak requests per second | under 2 (about 10 learners at once) | about 10 (about 60 at once) | evenings after school; answers save as the learner types, about once every 5 s |
| Rows and storage per year | under 50 MB | about 400 MB of answers, plus about 150 MB of receipts once payment ships | about 3 KB per answer with its marking and feedback; about 0.5 MB per receipt |
| Monthly cost at this load | about US$30 hosting, plus AI | about US$50 hosting, plus AI within the cost budget | a small server with managed Postgres, email and storage; the hosting ADR confirms |

Nothing changes in kind until about 3,000 learners.

## Budgets
At 300 learners, about 60 at once, unless a row says otherwise.

| Budget | Target | At what load | How it is checked |
|---|---|---|---|
| Speed: learner's page, first visit | under 3 s on a cheap Android phone on 4G (`site-rules.md`) | any | a throttled browser test on every change |
| Speed: learner's page, later visits | under 1 s (`site-rules.md`) | any | the same test |
| Speed (95% of requests faster than) | 300 ms for saving and reading answers | 10 requests a second | the server times every request |
| Speed: AI feedback | 95% within 15 s; after that the fixed line shows (Teaching settings) | 60 learners at once | the server times every AI call |
| Uptime | 99.5% a month | one server | an outside check every minute |
| Monthly cost cap: hosting, email, storage | US$60 | 300 learners | the monthly bills |
| Monthly cost cap: AI | per learner, at the daily caps, at most 25% of what their plan brings in a month; a hard monthly spending limit with the AI provider (`site-rules.md`) | the heaviest use the caps allow | tokens logged per answer; the provider's usage page |
| Accessibility | WCAG 2.1 AA, from 320 px wide, large text, screen readers (`site-rules.md`) | — | an automatic check on every screen; one pass by hand per release |
| CI time | 10 minutes from push to verdict | — | written down by the walking skeleton |

The AI cost budget is a test every choice must pass: the AI model, and any change to the daily caps.

## For the ADRs
Costly-to-reverse choices this PRD leaves to `specs/adr/`, the owner deciding each: the data model; email-code sign-in; hosting; manual DuitNow payment verification; the back-end stack; the AI model (it must pass the AI cost budget).
