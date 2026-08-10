# Week 8 — Async Programming and Promises

**Learning objective:** Distinguish between synchronous and asynchronous execution, understand the role of Promises in managing non-blocking operations, and implement a dynamic message form using DOM manipulation and event handling.

## Key concepts taught

- **Synchronous vs. asynchronous execution** — blocking, sequential, predictable code vs. non-blocking code that starts a task and keeps going. Framed with real-life analogies (phone call vs. text message) and the "page freeze" argument for why async matters on the web. `setTimeout` is the running example.
- **Promises (conceptual only)** — a Promise as a placeholder object for a result that hasn't arrived yet, with three states: **pending**, **fulfilled**, **rejected**. Students do *not* create Promises this week; the goal is readiness for the Fetch API in Week 9.
- **Promises vs. callbacks** — callbacks were introduced in Lesson 4; Promises are motivated as a cleaner way to chain async steps and avoid "callback hell."
- **Form handling and events** — attaching a listener for the `"submit"` event, `event.preventDefault()` to stop the default page refresh, reading field values off `event.target`, and `form.reset()` to clear fields.
- **Dynamic DOM building** — `createElement`, `innerHTML`/`textContent`, `appendChild`, `mailto:` links via template literals, and DOM traversal with `parentNode` + `.remove()` for the remove button.
- **Git branching workflow** — merge last week's PR, pull `main`, create a `lesson-8` branch, then stage/commit/push and open a new PR at the end.

Lesson reading is a single Odin Project link (Asynchronous Code) — there is no Scrimba split this week. Two **AI Learning Prompts** are included: Retrieval Practice (explain blocking vs. non-blocking) and Predict-then-Check (what you'd see logging an async result before it resolves).

## Brief overview of the assignment

Unlike the numbered-question format of earlier JS lessons, this is a **checklist-style build** that extends the student's portfolio site (HTML + CSS + JS), grouped into sections:

- **Get organized** — Git housekeeping: merge the lesson-7 PR, `git checkout main`, `git pull origin main`, then `git checkout -b lesson-8`.
- **Create a Message Form** — in `index.html`, add a `<section>` above the footer with an `<h2>` "Leave a Message" and a `<form name="leave_message">` containing name (`usersName`, text), email (`usersEmail`, email), message (`usersMessage`, textarea) — all `required` with `<label>`s — plus a submit button. Add a nav link to the section.
- **Add Message List Section** — a second `<section id="messages">` with an `<h2>` and an empty `<ul>`.
- **Handle Message Form Submit** — in `index.js`, select the form by `name`, add a `"submit"` listener, read the three field values, `console.log` them, then add `preventDefault` and `reset()`. Deliberately staged so students *see* the refresh and the un-cleared fields before fixing each.
- **Display Messages in List** — build an `<li>` with a `mailto:` `<a>` (name → email), a `<span>` for the message, and a "remove" `<button>` (type button) whose click handler removes its `parentNode`; append to the `<ul>`.
- **Style the Message Form** — CSS for spacing, mobile-friendly field sizing in media queries, and tap-friendly buttons.
- **Stretch goals (optional)** — hide the `#messages` section when the list is empty; add a per-message "edit" button.
- **Backup + Submit** — `git add . / commit / push`, then open a "Compare & pull request" and submit the PR URL.

## Likely trouble spots

- **Git setup at the start** — students who never merged the lesson-7 PR, or who branch from `lesson-7` instead of an updated `main`, carry forward a stale or diverging base. Watch for skipping the merge → pull → branch order.
- **Selecting the form** — the assignment says select by `name` attribute ("leave_message"); slides use `document.forms["leave_message"]`. Expect confusion between `querySelector`, `getElementsByName`, and the `forms` collection, and typos in the name string.
- **`preventDefault` placement** — must be the first line in the callback. Symptom of getting it wrong: the page refreshes and the console log flashes and disappears. This is staged intentionally, so students will hit it before fixing it.
- **Reading values off `event.target`** — forgetting `.value` (logging the input element instead of its text), or mixing up `event.target.usersName` with a separate `querySelector`. Field names must match the HTML `name` attributes exactly.
- **Ordering inside the callback** — the remove button must be built and appended to `newMessage` *before* `newMessage` is appended to the list, and all display code must sit *above* `messageForm.reset()`. Getting the order wrong produces empty or buttonless entries.
- **`parentNode` on the remove button** — students expect it to remove the button; it removes the whole `<li>` (its parent). If they attach the listener to the wrong element or call `.remove()` on the button itself, only the button disappears.
- **`mailto:` link + template literals** — backtick/`${}` syntax is still new; missing backticks or wrong quoting is common, as is not understanding that `mailto:` opens the user's email client.
- **CSS on mobile** — under-sized tap targets and crowded fields; the media-query sizing requirement is easy to skim past.
- **Promises anxiety** — some students expect to *write* Promises this week. Reassure them it's conceptual only and returns concretely in Week 9 (Fetch).
- **Final PR submission** — submitting a repo/commit link rather than the pull-request URL, or forgetting to push before opening the PR.
