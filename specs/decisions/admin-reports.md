# Decisions: Admin: Reports

<!-- ux-designer-Opus5.5-agent, 2026-10-11. History only. Build from specs/features/admin-reports.md and specs/patterns.md. -->

- One part: the Reports tab and the report email. The Report an issue form itself is area 10 (Parent page).
- Choices where the brief was loose (told the owner, 2026-10-11):
  - Report numbers are R and 5 digits from R10001, so they never look like a payment code (# and 7 digits).
  - The tab has To sort and Sorted. Mark sorted moves a report to Sorted (10-second Undo); it is kept until the family is deleted, and Back to To sort undoes a slip later.
  - The tab count is reports in To sort.
  - "My data" reports show a due date 21 days after they arrive and turn red when overdue, like Deletion requested (the brief's 21-day legal deadline). Once sorted they keep "done {date} · was due {date}" as a record. "Cancel my plan" reports remind Admin to use the report's day as Date asked.
  - The report email goes to support@puascari.com (which forwards to Admin), so the allow-list email is never in the site. Its Reply-To is the parent's account email, so Reply reaches the parent. Its subject holds the report number and topic, never the parent's email.
  - The message is plain text: line breaks kept, web addresses never clickable.
  - No search, filters or family-page Reports section at launch.
- **OQ-1, which answer a feedback report links to (owner gwl, 2026-10-11):** the report lists the child's last 10 writing answers before it arrived, and Admin picks the one the message describes. The parent's form is unchanged, because a list of the child's answers would make the parent page a progress page, which the brief rules out.
