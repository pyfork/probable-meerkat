# Glossary

<!-- project-lead-Opus5.5-agent, 2026-10-05. DRAFT for the owner's re-approval. One meaning per word, used by every brief in specs/features/.
     Meanings only: rules and numbers live in the brief named in "Rules in" (one fact, one place). Code names are what the screens, the database
     and the code call each thing. History: specs/decisions/glossary.md. -->

Every brief, screen, database table and piece of code uses these words with these meanings. A new word is added here first.

## People and places

| Word | Code name | Means | Rules in |
|---|---|---|---|
| **Child** | `child` | The learner, aged 10 (Malaysian Year 4). | accounts-and-sign-in |
| **Parent** | `parent` | The adult who signs up, pays and gets the emails. Also the guardian. | accounts-and-sign-in |
| **Admin** | `admin` | Whoever runs the admin page. Today, the owner. | admin-page |
| **Admin page** | `admin` (area) | The private page only Admin can open. | admin-page |
| **Parent page** | `parent_page` | The small page for parents, reached from a quiet "Parent" link. | parents-support-and-reviews |

## Money

| Word | Code name | Means | Rules in |
|---|---|---|---|
| **Plan** | `plan` | What was paid for: a product and a length, for one child, with a start and an end date. | plans-and-payment |
| **Trial** | `trial` | The free start before paying. | plans-and-payment |
| **Payment code** | `payment_code` | The parent's own code, typed in the bank's Reference box. | plans-and-payment |
| **Receipt** | `receipt` | What the parent sends after paying: the picture and the details from the form. | plans-and-payment |
| **Verified** | `verified` | Admin found the payment code in bank account transactions list and clicked Confirm. | admin-page |
| **Activated** | `activated` | Admin clicked Activate; the plan starts that day. | admin-page |
| **Grace time** | `grace` | The time after a trial ends when a child whose parent has sent a receipt can keep going. | plans-and-payment |
| **Possible double payment** | `possible_double_payment` | A label: the same plan for the same child was paid again while it is active or waiting. | plans-and-payment |
| **Refund** | `refund` | Money paid back to a parent after a cancellation or a double payment. | plans-and-payment |
| **Refunds to pay** | `refunds_due` | Admin's list of refunds not yet sent. | admin-page |

### A plan's states (`plan.state`)
| State | Means |
|---|---|
| `trial` | in its free trial |
| `waiting` | a receipt is sent and not yet activated (during grace time the child can keep going) |
| `active` | activated and before its end date |
| `paused` | the trial or grace time ran out with no activation; nothing is lost |
| `cancelled` | cancelled by the parent; the child can go on until the end of the month used |
| `ended` | past its end date, or after a cancellation's last day |

## Time

| Word | Code name | Means | Rules in |
|---|---|---|---|
| **Day** | `day` | A calendar day in Malaysia time, midnight to midnight. | site-rules |
| **Active day** | `active_day` | A day with at least one writing task submitted or one spelling round finished. | parents-support-and-reviews |

## Both products

| Word | Code name | Means | Rules in |
|---|---|---|---|
| **Fun mode** | `fun` | The mode with help while working. | each product brief |
| **Exam mode** | `exam` | The mode that looks like the test paper: no help while working, marked at the end. | each product brief |
| **Help time** | `help_after` | How long a child is stuck before help appears in Fun mode. Writing: no typing while the checks aren't all ticked. Spelling: time on one word. | admin-page (number), product briefs |
| **Try** | `attempt` | One go at a task, set, paper or round, from opening it to finishing or leaving. | each product brief |
| **Marking** | `marking` | What the child sees after finishing: ticks and crosses, stars and notes. | each product brief |
| **Teaching settings** | `teaching_settings` | The numbers Admin can change. | admin-page |
| **Content** | `content` | Everything a child reads, answers or is marked against. | site-rules |
| **Version** | `content_version` | One saved form of a piece of content. An edit makes a new version; old answers keep the version the child saw. | site-rules |
| **Needs change** | `needs_change` | Admin's mark on content. It pauses that content for children until it is fixed. | admin-page |
| **Child-safety check** | `safety_check` | The check that reads the model's feedback and the child's answer before anything is shown. | writing-confidence |
| **Fixed line** | `fixed_line` | One of the owner's ready-written lines, used when the model's feedback can't be used. | writing-confidence |
| **Flag** | `flag` | A mark that puts an answer on Admin's To check list (a copied model answer, unkind words). | writing-confidence |
| **Report** | `report` | A message from the Report an issue form. | parents-support-and-reviews |
| **Review** | `review` | A parent's text or video about the product, shared only once Admin approves it. | parents-support-and-reviews |
| **Deletion request** | `deletion_request` | A parent's "Delete my account and data", waiting for Admin to finish it. | parents-support-and-reviews |

### A try's status (`attempt.status`)
| Status | Means |
|---|---|
| `submitted` | a writing task was submitted (Fun mode) |
| `finished` | a writing exam paper or a spelling round was finished and marked |
| `left_unfinished` | the child left part-way, after writing or typing something |
| `left_empty` | the child left without writing or typing anything |

## Writing Confidence

| Word | Code name | Means | Rules in |
|---|---|---|---|
| **Task** | `task` | One invitation the child replies to. | writing-confidence |
| **Set** | `writing_set` | Tasks done one after another as a group. | writing-confidence |
| **Exam paper** | `exam_paper` | A set done in Exam mode. | writing-confidence |
| **Idea words** | `idea_words` | Help words for one task, split into **Yes ideas** and **No ideas**. Never called "sets". | writing-confidence |
| **Suggested starters** | `starters_suggested` | The sentence starters the app offers on screen. | writing-confidence |
| **Accepted starters** | `starters_accepted` | The starters the "2 reasons" tick counts as linked. Never shown. | writing-confidence |
| **Check** | `check` | One of the ticks while writing: Yes / No, 2 reasons, About 50 words. | writing-confidence |
| **Nudge** | `nudge` | A short teacher note while writing, picked by what is written so far. | writing-confidence |
| **Help me** | `help_me` | The button that appears after the Help time. | writing-confidence |
| **Feedback** | `feedback` | What the teacher (or model) says after a task is submitted. | writing-confidence |
| **Correction** | `feedback_correction` | Admin's better version of a feedback; the model learns from these. | admin-page |
| **Model (AI)** | `model` | The AI that writes feedback. Not the same as a model answer. | site-rules |
| **Model answer** | `model_answer` | The owner's example answer for a task, in a default and a short-sentence version, for Yes and for No. | writing-confidence |
| **Stars** | `stars` | The 0–3 mark for one writing answer. | writing-confidence |
| **Placement** | `placement` | Weaker, Average or Stronger, worked out from recent sets. Never shown to the child or parent. | writing-confidence |
| **Guided paper** | `paper_guided` | The writing paper with a sentence starter on each line. | writing-confidence |
| **Standard paper** | `paper_standard` | The writing paper with plain lines. | writing-confidence |

## Spelling Confidence

| Word | Code name | Means | Rules in |
|---|---|---|---|
| **Round** | `spelling_round` | A group of spelling words done together, like Part 5 of the test paper. Spelling only. | spelling-confidence |
| **Bonus round** | `bonus_round` | Pick-the-right-spelling questions after a round, if the child qualifies. | spelling-confidence |
| **Hint** | `hint` | Help about a word's meaning, never its letters. | spelling-confidence |
| **Debrief** | `debrief` | The cards after marking that go through each mistake, with Listen. | spelling-confidence |
| **Box** | `box` | Where each word sits for each child (Leitner boxes). A higher box means known better. | spelling-confidence |
| **Confident words** | `confident_words` | A child's words in the higher boxes. | spelling-confidence |
| **Word list 1** | `word_list_1` | The Year 3 and Year 4 Part 5 spelling words. | spelling-confidence |
| **Word list 2** | `word_list_2` | The harder words that join once word list 1 is mostly confident. | spelling-confidence |
| **Also right** | `also_right` | Another real word that fits a clue, first letter and boxes, approved by the owner. Counts as right. | spelling-confidence |
| **Recording** | `recording` | A recorded voice reading a word's sentence for Listen. | spelling-confidence |
