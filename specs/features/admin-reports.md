# Spec: Admin: Reports

## Problem
Parents reach us only through Report an issue and the support email, and some reports carry a deadline (a data request, 21 days) or start a money step (a cancel request), so Admin must see every report, act from it, and know which ones are still open.

### Concept checks
1. Does a new report reach Admin only on the Reports tab? → No. An email goes to support@ too (AC-17).
2. Admin presses Reply on the report email. Who gets the reply? → The parent's account email (AC-19).
3. Can a report number be mistaken for a payment code? → No. It starts with R (AC-2).
4. Does Mark sorted email the parent? → No (AC-11).
5. Does Mark sorted delete the report? → No. It moves to Sorted (AC-13).
6. Does a "my data" report have a due date? → Yes, 21 days after it arrived (AC-8).
7. Does a "cancel my plan" report cancel the plan? → No. Admin opens the family and uses Cancel plan, with Date asked set to the day the report arrived (AC-9).
8. Can Admin click a link the parent typed in the message? → No. The message is plain text (AC-6).
9. Does the list jump when a new report arrives? → No (PT-12).
10. A report is about feedback. Does the parent pick which answer? → No. The report lists the child's last 10 answers, and Admin picks (AC-23).

## Goals and non-goals
1. **Goals**
   - Admin sees every report, newest first, on a phone or a laptop, and in the inbox.
   - From a report, Admin reaches the family (and, for feedback, the answer) in one tap.
   - Data requests show their legal due date, so none is missed.
   - Admin clears a report once it is dealt with, and can still find it later.
2. **Non-goals**
   - The Report an issue form and its "Report received" screen (area 10, Parent page). This spec only reads what the form sends.
   - Replying on the admin page. Conversations stay in Admin's inbox (`admin-page.md`, out of scope).
   - Searching or filtering reports. Reports are few at launch.
   - A Reports section on the family page.
   - The daily to-do email's line for reports, and test families (area 6).

<!-- ux-designer-Opus5.5-agent, 2026-10-11. DRAFT for the owner. Rules for the Reports tab and the report email of the
     approved brief specs/features/admin-page.md (Reports, Emails and replies) and parents-support-and-reviews.md
     (Report an issue). Shared rules (PT-n): specs/patterns.md. Decisions: specs/decisions/admin-reports.md. -->

Words follow `specs/glossary.md`. The briefs: `admin-page.md` (Reports, Emails and replies), `parents-support-and-reviews.md` (Report an issue). Words in *italics* are on-screen words from the table at the end. "Parents part n, AC-n" means a rule in `admin-parents-n-*.md`.

## Patterns used
Admin tabs (PT-1 to PT-5), Row becomes a card (PT-6 to PT-11), Lists move only when Admin asks (PT-12 to PT-15), Undo in place (PT-16 to PT-26), Email didn't arrive (PT-30, PT-31, PT-33, PT-34), Buttons that change something (PT-35 to PT-38), List states (PT-39 to PT-41), Labels on a row (PT-48, PT-49), Times and money (PT-50), Action log (PT-52).

---

## Report numbers
- **AC-1** Every report gets a report number when it is sent. It is never reused, even after the report or the family is deleted.
- **AC-2** A report number is R and 5 digits, counting up from R10001 (*Report number*). The R keeps it apart from payment codes (# and 7 digits), so an inbox search finds one or the other.

## The Reports tab
- **AC-3** The tab has two lists, *To sort* (open first) and *Sorted*, as two buttons at the top of the list. The one showing is filled (PT-1). Each list has its own web address (PT-5).
- **AC-4** The tab count (PT-3) is the number of reports in To sort.
- **AC-5** To sort shows every report not yet sorted, newest first, 50 at first. *Show more* adds the next 50 below, and what is on screen stays.

### Each report
- **AC-6** A report shows: its report number in the largest text, its labels, the topic in the parent's words (*Topics*), when it arrived (PT-50), the account email, the child's first name (or *No child yet*, PT-11), and the message. The message shows in full as plain text, with the parent's line breaks kept. A web address in it is shown as text, never as a link.
- **AC-7** *Open family* opens the family page (Parents part 1, AC-12). It is on every report.
- **AC-8** A report on "My data (see a copy or correct it)" shows *Due* (21 days after it arrived) as a label. From the day after, it shows *Overdue* instead, in red with a warning icon (PT-48).
- **AC-9** A report on "Cancel my plan" shows the *Cancel hint*, so Admin sets Date asked in Cancel plan to the day the report arrived (Parents part 2, AC-4).
- **AC-10** A report from a test family shows the *Test family* label (Parents part 1, AC-11).

### Mark sorted
- **AC-11** *Mark sorted* is the report's only button. It moves the report to Sorted and sends nothing.
- **AC-12** It has Undo for 10 seconds (PT-16, PT-17). Undo puts the report back in To sort.
- **AC-13** A sorted report is kept, until the family is deleted (Parents part 3, AC-13).
- **AC-14** A My data report can be marked sorted before its due date. Once sorted, it shows *Data done* instead of Due or Overdue, so Sorted keeps a record that the 21 days were met (or not).

### Sorted
- **AC-15** Sorted shows sorted reports, the most recently sorted first. Each shows what To sort shows, plus *Sorted line* (who and when). Show more works as in To sort (AC-5).
- **AC-16** *Back to To sort* moves a report back, with Undo for 10 seconds.

## The report email
- **AC-17** Each new report sends one email to support@puascari.com, which forwards to Admin's inbox. The admin allow-list email is never written into the site.
- **AC-18** Its subject is *Report email subject*: the report number, then the topic. It never holds the parent's email, because Admin's reply keeps the subject.
- **AC-19** Its Reply-To is the parent's account email, so Reply in the inbox goes to the parent. Admin replies as support@puascari.com (`admin-page.md`, Emails and replies).
- **AC-20** Its body holds everything the report shows (AC-6), plus links to the report on the Reports tab and to the family page. Both links need Admin's sign-in.
- **AC-21** If the report email doesn't arrive (PT-30), the report shows *Didn't arrive* with *Resend* (PT-31). Resend goes to support@ again; there is no address to pick. The report itself is on the tab either way.

## Reports and deleted families
- **AC-22** Deleting a family deletes its reports (Parents part 3, AC-13). A deleted family's reports leave the lists when the list next updates (PT-14). Emails already in Admin's inbox stay there.

## Feedback reports
- **AC-23** A report on "Feedback my child received" shows *Recent answers*: the child's last 10 writing answers sent before the report arrived, newest first. Each shows when it was sent, the task's first words and the stars.
- **AC-24** Each recent answer is a link that opens that answer on the Answers tab (`admin-page.md`, Answers). Admin matches it to the parent's message.
- **AC-25** A child with no writing answers before the report shows *No answers yet*. Spelling answers aren't listed, because the Answers tab shows writing only at launch.

---

## Layout
- **AC-26** From 1024 px up, each list is a table with these columns in order: Report (number and labels) · Arrived · Parent (account email and child) · Topic · Message (with Recent answers under it) · Mark sorted. The message column takes the spare width and wraps (PT-10).
- **AC-27** Below 1024 px, each report is a card (PT-6 to PT-11) in this order: report number · labels · topic · arrived · account email · child · message · Recent answers · Open family · Mark sorted (filled). The links change nothing, so they sit above the button (PT-9).
- **AC-28** To sort and Sorted sit side by side at every width. They are short words, so they fit at 320 px.

## Keyboard and screen reader
- **AC-29** Tab order on a report: each recent answer, Open family, Mark sorted. Undo follows PT-25 and PT-26.
- **AC-30** Due and Overdue are read out as words, never only as colour (PT-48).

## Action log
- **AC-31** Mark sorted, Back to To sort and each Undo write one entry with the report number and the family (PT-52). A new report writes an entry with "parent" as who.

---

## Words on screen
`{n}` is a number, `{email}` an email, `{date}` and `{time}` follow PT-50.

| Name | Words | Example |
|---|---|---|
| Report number | R{5 digits} | R10042 |
| To sort | To sort | |
| Sorted | Sorted | |
| Topics | Feedback my child received · Payment or subscription · Something isn't working · Cancel my plan · My data (see a copy or correct it) · Something else | |
| No child yet | Child: not added yet | |
| Open family | Open family | |
| Due | Data request · due {date} | Data request · due 1 Nov 2026 |
| Overdue | Data request · overdue since {date} | |
| Data done | Data request · done {date} · was due {date} | Data request · done 20 Oct 2026 · was due 1 Nov 2026 |
| Cancel hint | Use {date} as Date asked in Cancel plan | Use 11 Oct 2026 as Date asked in Cancel plan |
| Test family | Test family | |
| Recent answers | Last 10 answers before this report | |
| Answer line | {date}, {time} · {task's first words}… · {n} stars | 10 Oct, 8:02pm · Would you like to visit the zoo… · 1 star |
| No answers yet | No writing answers before this report. | |
| Mark sorted | Mark sorted | |
| Sorted slim line | {report number} sorted | R10042 sorted |
| Sorted line | Sorted by {email}, {date}, {time} | |
| Back to To sort | Back to To sort | |
| Show more | Show more | |
| Nothing to sort | No reports to sort. | |
| Nothing sorted | No sorted reports yet. | |

### Emails
| Name | Subject | What it says |
|---|---|---|
| Report email | {report number} {topic} | R10042 Cancel my plan · the topic, arrived, account email, child, the message as plain text · links: Open report, Open family. From the site's address, to support@puascari.com, Reply-To the parent's account email. |

## Content for testing
| What | Test value |
|---|---|
| Longest message | 1000 characters with no spaces; 1000 characters with 20 line breaks; a message holding a web address |
| Longest email | sharifah.nurul.aisyah.binti.abdullah@yahoo.com.my |
| Topics | one of each topic, a Data request 20 days old and one 22 days old |
| Families | a feedback report from a child with 3 answers, and one with 40; a Spelling-only family's feedback report; a parent with no child added; a test family; a family deleted after sending a report |
| List sizes | 0 reports, 1, 60 (Show more) |
| Screen sizes | 320 × 568, 667 × 375, 390, 768 and 1280 px wide, large text on |

## Worked examples
| What happens | Result |
|---|---|
| A parent sends "Cancel my plan" on 11 Oct 2026 | R10042 shows on To sort; Admin gets "R10042 Cancel my plan"; the report says to use 11 Oct 2026 as Date asked |
| Admin presses Reply on that email | The reply goes to the parent's account email, from support@puascari.com, with R10042 in the subject |
| A parent sends "My data" on 11 Oct 2026 | Due 1 Nov 2026; from 2 Nov it shows Overdue, in red with a warning icon |
| Admin marks R10042 sorted, then presses Undo after 4 seconds | R10042 is back in To sort; the Log has two entries |
| A parent sends "Feedback my child received" about "the zoo one yesterday" | The report lists the child's last 10 answers; Admin opens the zoo answer on Answers |
| The report email bounces | R10042 shows Didn't arrive with Resend; the report is on the tab as normal |

## Open questions
None. (OQ-1 settled by the owner, gwl 2026-10-11: the report lists the child's last 10 answers and Admin picks; the parent's form is unchanged.)
