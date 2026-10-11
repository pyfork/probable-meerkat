# Shared patterns

## Problem
1. **The problem:** Every admin tab meets the same small problems: undoing a slip, a list on a phone, an email that bounced, a button pressed twice. Solved separately on each tab, they would behave differently, and Admin would have to learn each one again.
2. **Why this spec exists:** To solve each of those problems once, here, so every tab uses the same answer and the admin page feels like one app, not eight.

## Goals and non-goals
1. **Goals**
   - Each pattern is written once, and screens point at it instead of repeating it.
   - The same action gives the same feedback on every tab.
   - Every pattern works on a phone, by keyboard and with a screen reader.
2. **Non-goals**
   - Colours, fonts and spacing. The look follows `site-rules.md` and the approved teaser.
   - Patterns for the child's and the parent's pages, until those pages are designed.
   - Rules for one screen only. Those live in that screen's spec.

<!-- ux-designer-Opus5.5-agent, 2026-10-10. DRAFT for the owner. One entry per pattern, each written once. Screens point at
     a pattern's rule IDs (PT-n) instead of restating it. IDs are permanent: never reused or renumbered; a removed rule retires its ID. -->

Words follow `specs/glossary.md`. Widths follow the responsive rules: drawn at 390, 768 and 1280 px, working at every width from 320 to 1440 px. Icons are Heroicons only (`site-rules.md`).

Before adding a pattern, check this list. The same problem gets the same pattern. Words in *italics* are on-screen words from the table at the end.

---

PATTERN: Admin tabs
RULE:
- **PT-1** Every admin screen has the tab bar at the top. The tab Admin is on is filled with colour, never outlined (`site-rules.md`).
- **PT-2** A tab shows only once it works. Tabs not built yet are not shown.
- **PT-3** Verify and Activate show how many rows are waiting (*Tab count*). With nothing waiting, no number shows. The numbers update by themselves; the lists don't (PT-12).
- **PT-4** When the tabs don't fit on one line, they wrap onto a second line. They never scroll sideways and are never tucked into a menu.
- **PT-5** Each tab has its own web address, so reloading or going Back keeps Admin on the same tab.
WHY: Admin moves between Verify and Activate many times in one sitting, often on a phone. Every tab must be in sight and one tap away.
USED BY: every admin tab.
EXCEPTIONS: none.

---

PATTERN: Row becomes a card
RULE:
- **PT-6** From 1024 px up, an admin list is a table with one row per item. Below 1024 px, each row becomes a card, because the columns stop fitting and Admin needs big buttons on a phone with the bank app open alongside.
- **PT-7** Cards sit one per line, at most 640 px wide, lined up with the page's left edge.
- **PT-8** A card starts with the item's key (for a payment, the payment code) in the largest text. Details come next. Buttons come last, one per line, the full width of the card and at least 48 px tall, with the main one first and filled.
- **PT-9** The top part of a card holds nothing that changes anything (a Copy button is fine). So a quick second tap, after a card above shrinks, lands on something harmless.
- **PT-10** Long values (emails, names, transaction numbers) wrap onto more lines, breaking inside the word if they have to. They are never cut off, faded out or made smaller.
- **PT-11** An optional value that is missing says so (for example "WhatsApp: not given"), so every card has the same lines in the same order.
WHY: The brief asks for big buttons on a phone. Keeping the key first and the buttons last means Admin's eye and thumb always go to the same places.
USED BY: Verify, Activate. Later: every admin list.
EXCEPTIONS: none.

---

PATTERN: Lists move only when Admin asks
RULE:
- **PT-12** Once a list is on screen, its rows never move, appear or disappear by themselves.
- **PT-13** The page checks for a newer list when it comes back into view (for example, back from the bank app) and once a minute while it is open.
- **PT-14** When there is a newer list, the *List changed bar* shows at the top of the list. The list updates when Admin taps it, changes tab or reloads the page.
- **PT-15** A row Admin has dealt with shrinks to a slim line in the same place (PT-16) and stays there until the list updates.
WHY: Admin taps Confirm on a phone while switching to and from the bank app. A row that jumps under the thumb could confirm the wrong payment.
USED BY: Verify, Activate. Later: every admin list.
EXCEPTIONS: none.

---

PATTERN: Undo in place
RULE:
- **PT-16** An action Admin can take back turns the row into a slim line in the same place. The line says what happened, in words, and has an *Undo* button with the seconds left beside it.
- **PT-17** Undo lasts 10 seconds for an action that sends nothing, and 30 seconds for an action that emails a parent.
- **PT-18** An action that emails a parent holds the email until its Undo time is over. An undone action sends nothing.
- **PT-19** The server keeps the time, not the page. Closing the page, losing the internet or signing out never stops or cancels the action. If the server restarts, the action finishes and any held email goes out as soon as the server is back.
- **PT-20** When several rows are done in one go, each row shrinks without its own Undo, and one Undo shows where the button was pressed. That one Undo reverses all of them.
- **PT-21** Undo puts each row back where it was, as it was before the action, with no ticks.
- **PT-22** Undo pressed after the time is up (for example, on a slow connection) shows *Too late* and what happened.
- **PT-23** If Undo can't reach the server, the line shows *Couldn't undo* with *Try again*, until the time is up. After that, the line shows what happened as soon as the page can reach the server.
- **PT-24** When the time is up, the Undo button goes and the line says the final result.
- **PT-25** Keyboard: after the action, focus moves to the slim line itself, not to its Undo button, so a second Enter does nothing. Undo is the next Tab stop. When Undo goes, focus stays on the line.
- **PT-26** Screen reader: the line's words are read out once, politely, with how long Undo lasts (*Undo read out*). The countdown is not read out. The final result is read out once.
WHY: Mistakes are easy on a phone. Undo fixes a mistake without slowing down every right tap with "Are you sure?". Actions that can't be undone use Typed confirmation (PT-27) instead.
USED BY: Verify (Confirm, Close receipt), Activate (Activate, Activate several, Send back to Verify).
EXCEPTIONS: none.

---

PATTERN: Typed confirmation
RULE:
- **PT-27** An action that can't be undone opens a dialog (PT-42 to PT-45). The dialog says in plain words what will happen and asks Admin to type the parent's email.
- **PT-28** The action button names the action (for example "Delete this family") and stays off until the typed text matches the email. Capital letters and spaces at either end don't matter. Pasting is allowed.
- **PT-29** Closing the dialog does nothing and clears what was typed.
WHY: The brief makes dangerous actions hard to press by accident. It guards against accidents, not strangers (Admin is already signed in), so pasting is fine.
USED BY: Parents tab: Delete this family, Move to a new email (in their own specs, later). Not used on Verify or Activate.
EXCEPTIONS: none.

---

PATTERN: Email didn't arrive
RULE:
- **PT-30** An email "didn't arrive" when the email service reports it couldn't deliver it (it bounced or was refused), or when the site still couldn't hand it to the email service after trying again.
- **PT-31** The row the email belongs to shows *Didn't arrive* with a warning icon, and *Resend*.
- **PT-32** Resend shows the address it will send to (*Resend to*). If the parent's account email is different, Admin picks one of the two.
- **PT-33** Resend sends the same email again, and the note becomes the *Resent line*. If that one doesn't arrive either, *Didn't arrive* comes back.
- **PT-34** Whatever the email was about (an activation, a problem) stays done. Only the email is tried again.
WHY: The usual cause is a mistyped email on the receipt form, so Admin needs to see the address and be able to choose the account email instead.
USED BY: Verify, Activate. Later: every tab that emails parents.
EXCEPTIONS: none.

---

PATTERN: Buttons that change something
RULE:
- **PT-35** Pressing one switches it off at once and changes to its *Working words*, so a second tap does nothing.
- **PT-36** If it fails, the row stays as it was. Under the button, the *Failed message* says what went wrong and what to do. The button works again, and nothing typed or picked is lost.
- **PT-37** If the row was already dealt with on another device, the *Done elsewhere* message says so, and the row becomes a slim line with no Undo.
- **PT-38** If Admin's sign-in has ended (`accounts-and-sign-in.md`), the page shows *Signed out* with *Sign in*. The action was not done. After signing in, Admin is back on the same tab.
WHY: Admin often works on a phone signal that comes and goes, and sometimes has the admin page open on two devices.
USED BY: Verify, Activate. Later: every admin button that changes something.
EXCEPTIONS: none.

---

PATTERN: List states
RULE:
- **PT-39** First load: the tab bar shows at once, and *Loading* shows where the list will be.
- **PT-40** Empty: one short line saying there is nothing, shown only after the list has loaded with no rows.
- **PT-41** Load error: *Load failed* with *Try again*. Anything already on screen stays.
WHY: One model for loading, empty and error on every list, so Admin never mistakes "still loading" or "failed" for "nothing to do".
USED BY: Verify, Activate. Later: every admin list.
EXCEPTIONS: none.

---

PATTERN: Dialog
RULE:
- **PT-42** Below 640 px a dialog fills the screen. From 640 px up it is a box in the middle, over a dimmed page. Below 640 px a small box would leave no room for the phone keyboard.
- **PT-43** The dialog's title says what it is for and which row (for example "Problem with #1601319").
- **PT-44** A Close button (x-mark icon, 44 by 44 px) at the top right and the Escape key both close it. While it is open, focus stays inside it. When it closes, focus goes back to the button that opened it.
- **PT-45** Everything in it can be reached by scrolling, on a short screen too. The main button sits at the end of the content, not fixed to the edge of the screen, so the phone keyboard can't cover it.
WHY: One way in and one way out for every pop-up, on every screen size.
USED BY: Verify (Problem with this payment, Close receipt, receipt viewer). Later: Typed confirmation and every admin dialog.
EXCEPTIONS: none.

---

PATTERN: Choice list
RULE:
- **PT-46** The picked choice fills with colour, never an outline. Up and Down move the choice; Enter or a tap picks it (`site-rules.md`).
- **PT-47** A screen reader hears it as one group of choices, with the picked one named.
WHY: The owner's rule for every choice list: it should feel like a proper app.
USED BY: Verify (reason for a payment problem, reason for closing a receipt). Later: every choice list.
EXCEPTIONS: none.

---

PATTERN: Labels on a row
RULE:
- **PT-48** A label is words plus a Heroicons icon. Colour is never the only sign.
- **PT-49** A row can carry several labels at once. They wrap onto more lines rather than hiding one another.
WHY: Labels warn Admin before they act. A warning that is only a colour can be missed, and screen readers can't read colour.
USED BY: Verify, Activate.
EXCEPTIONS: none.

---

PATTERN: Times and money
RULE:
- **PT-50** Times are Malaysia time, written like "10 Oct, 9:14pm". The year is added when it isn't this year. Dates on their own are written like "10 Oct 2026".
- **PT-51** Money is RM with 2 decimals, as `plans-and-payment.md` says, with a comma for thousands (for example RM5,900.00).
WHY: One way to write each, so Admin can compare at a glance.
USED BY: every admin screen.
EXCEPTIONS: none.

---

PATTERN: Action log
RULE:
- **PT-52** Every admin action that changes something writes one entry in the admin action log: who, what, which payment code or family, and when. An Undo writes its own entry (`accounts-and-sign-in.md`).
WHY: The brief asks for a record nobody can edit, so a stranger's or a mistaken action can always be traced.
USED BY: every admin action.
EXCEPTIONS: none.

---

## Words on screen
`{code}` is the payment code, `{n}` a number, `{s}` the seconds left, `{date}` and `{time}` follow PT-50.

| Name | Words | Example |
|---|---|---|
| Tab count | {tab name} {n} | Verify 3 |
| List changed bar | The list has changed · Show latest | |
| Undo | Undo · {s} s | Undo · 9 s |
| Undo read out | Undo available for {s} seconds | Undo available for 30 seconds |
| Too late | Too late to undo. {what happened} | Too late to undo. #1601319 is activated and the email has gone. |
| Couldn't undo | Couldn't undo. Check your internet. | |
| Try again | Try again | |
| Didn't arrive | Email didn't arrive: {which email} to {address} | Email didn't arrive: activation email to sharifah.n@yahoo.com.my |
| Resend | Resend | |
| Resend to | Resend to {address} | |
| Resent line | Resent {date}, {time} | Resent 10 Oct, 9:40pm |
| Working words | the button's action word, ending in "…" | Confirming…, Activating…, Sending… |
| Failed message | Couldn't {action}. Check your internet and try again. | Couldn't confirm. Check your internet and try again. |
| Done elsewhere | Already {done} on another device | Already confirmed on another device |
| Signed out | Your sign-in has ended. | |
| Sign in | Sign in | |
| Loading | Loading… | |
| Load failed | Couldn't load the list. Check your internet. | |
