---
marp: true
theme: default
paginate: true
style: |
  section {
    background-color: #FFFFFF;
    color: #1C1C1C;
    font-family: 'Segoe UI', Arial, sans-serif;
  }
  h1 {
    color: #12284C;
    border-bottom: 3px solid #FF5C35;
    padding-bottom: 6px;
    margin-bottom: 12px;
  }
  h2 { color: #12284C; }
  h3 { color: #FF5C35; }
  pre {
    background-color: #1C1C1C;
    border-left: 5px solid #FF5C35;
    border-radius: 4px;
  }
  code {
    background-color: #F1F2F2;
    border-radius: 3px;
    padding: 1px 5px;
    color: #12284C;
  }
  pre code {
    background-color: transparent;
    color: #F1F2F2;
    padding: 0;
  }
  blockquote {
    border-left: 4px solid #F3C300;
    background-color: #F1F2F2;
    padding: 8px 16px;
    border-radius: 0 4px 4px 0;
    color: #12284C;
    margin: 8px 0;
  }
  section.title {
    background-color: #12284C;
    color: #FFFFFF;
    text-align: center;
  }
  section.title h1 {
    color: #F3C300;
    border-color: #FF5C35;
  }
  section.title h2,
  section.title h3,
  section.title p {
    color: #F1F2F2;
    border: none;
  }
  section.section-break {
    background-color: #FF5C35;
    color: #FFFFFF;
    text-align: center;
  }
  section.section-break h1 {
    color: #FFFFFF;
    border: none;
    font-size: 2.8em;
  }
  section.section-break h2,
  section.section-break p {
    color: #FFFFFF;
    border: none;
  }
  section.cfu {
    background-color: #F1F2F2;
  }
  section.cfu h1 {
    color: #12284C;
    border-bottom-color: #F3C300;
  }
---

<!--
MENTOR SETUP — Read before presenting. This is not a slide.

Opening Marp:
  VS Code: Install the Marp extension → open this file → "Open Preview" → fullscreen
  Browser: marp.app → paste this markdown → present from browser

Two-mentor structure (suggested):
  First mentor leads the Explore section (synchronous vs. asynchronous, Promises).
  Second mentor leads the Apply section (live coding demo of the message form).
  Both mentors stay on screen throughout. The first mentor can support questions during Apply.

Speaker notes appear in comment blocks like this one.
In Marp presenter mode, notes display in your presenter panel.
-->

<!-- _class: title -->

# Lesson 8: Async Programming and Promises

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Explain the difference between synchronous and asynchronous code
- Describe what a Promise is and its three possible states
- Prevent a form's default page-refresh behavior with `preventDefault`
- Read form values from a submit event
- Add and remove items from the DOM dynamically

---

<!-- _class: section-break -->

# Explore

---

# Synchronous Code

Synchronous code runs **one step at a time**, in order.

```javascript
console.log("Step 1");
console.log("Step 2");
console.log("Step 3");
// Always prints: Step 1, Step 2, Step 3
```

Each line **waits** for the line above it to finish.

> Real-life example: a phone call — you wait for the other person to finish before you speak.

<!--
Keep this brief. The goal is a clear mental model before introducing async.
Ask the group: "Can you think of other real-life examples of doing things one at a time?"
-->

---

# Asynchronous Code

Asynchronous code lets you **start a task and keep moving** — you don't wait.

```javascript
console.log("Order placed");

setTimeout(function () {
  console.log("Food is ready!");
}, 2000);

console.log("Chatting with friends...");
```

Output: `Order placed` → `Chatting with friends...` → (2 sec) → `Food is ready!`

> Real-life example: a text message — you send it and do other things while you wait for a reply.

<!--
Run this in the browser console if possible. Seeing the delay land after "Chatting..."
makes the concept click better than any explanation.
-->

---

# Why Async Matters for the Web

Web pages often need to wait for things:

- Loading data from a server
- Waiting for a user to submit a form
- Fetching an image or a file

If those tasks were **synchronous**, the entire page would **freeze** while waiting.

Async code keeps the page **interactive** — users can still click and scroll.

<!--
Connect this to what students have already seen: event listeners are already async!
The browser doesn't freeze waiting for a click — it just listens and responds when it happens.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**You visit a website and click a button to load new data. The page stays usable while the data loads. Which type of code is handling that?**

A) Synchronous — it runs one step at a time

B) Asynchronous — it starts the task and keeps the page responsive

C) Neither — JavaScript cannot load data from servers

D) Both — synchronous and asynchronous always work together

<!--
Answer: B.
If students pick A, revisit the "freeze" concept: sync would lock the page until the data arrived.
This question sets up why async — and eventually fetch — matters for real web apps.
-->

---

# What Is a Promise?

A **Promise** is an object that represents a result that **isn't ready yet**.

It has three possible states:

| State | Meaning |
|-------|---------|
| **Pending** | Still waiting — no result yet |
| **Fulfilled** | Success — here is the value |
| **Rejected** | Something went wrong |

Think of it like an online order confirmation: you don't have the item yet, but you have a *promise* it's coming.

<!--
Students do not create Promises in this lesson. The goal is conceptual readiness for Lesson 9 (fetch).
Emphasize: "We won't write Promises ourselves today. You'll use them next week when we fetch real data."
-->

---

# Promises vs. Callbacks

We used **callbacks** in earlier lessons — functions passed to other functions.

```javascript
// Callback style
setTimeout(function () {
  console.log("Done!");
}, 1000);
```

Promises give us a **cleaner way** to handle async results, especially when multiple async steps chain together.

> "Callback hell" — deeply nested callbacks — is hard to read and debug. Promises help avoid that.

<!--
Students saw callbacks in Lesson 4. This is a bridge slide — they don't need to master Promises today,
just understand why they exist and what problem they solve.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**A Promise is in the "Pending" state. What does that mean?**

A) The operation failed and returned an error

B) The operation succeeded and returned a value

C) The operation has started but has not finished yet

D) The Promise was never created

<!--
Answer: C.
Common confusion: students sometimes think "pending" means "not started." Clarify that the operation
is in progress — JavaScript is waiting for a response (from a server, a timer, etc.).
-->

---

# Forms and Event Listeners (Review)

We used event listeners in Lesson 7. This week we attach one to a **form**.

```javascript
let btn = document.querySelector("button");
btn.addEventListener("click", function () {
  console.log("Clicked!");
});
```

Forms fire a `"submit"` event when the user clicks the submit button.

We listen for it the same way — just with a different event name.

<!--
Quick retrieval check: "What method do we call to attach an event listener?"
Let students answer before moving on.
-->

---

# The Problem: Default Form Behavior

When a form submits, the browser **refreshes the page** by default.

That wipes out everything — the form values, the DOM changes, all of it.

We need to **stop that** before we do anything else.

```javascript
form.addEventListener("submit", function (event) {
  event.preventDefault(); // Stop the page refresh
  // Now we can safely read the form values
});
```

> Always put `event.preventDefault()` as the **first line** inside the callback.

<!--
Demo this live if possible: submit the form without preventDefault first so students see the refresh,
then add it and show it stops. The "aha" moment is much stronger from observation.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**You add a submit event listener to a form, but the page refreshes every time you submit. What is most likely missing?**

A) The form does not have a `name` attribute

B) `event.preventDefault()` was not called

C) The event listener is using `"click"` instead of `"submit"`

D) You cannot attach event listeners to forms

<!--
Answer: B.
If students pick C: that's a reasonable guess — mention that "click" on the submit button would fire,
but using "submit" on the form is the correct and more robust approach.
-->

---

<!-- _class: section-break -->

# Apply

<!--
Second mentor leads from here (suggested).
Have index.html and index.js open in your editor before this slide.
You'll code the message form live, step by step, inviting students to direct you.
-->

---

# Core Activity: Build a Message Form

We'll build the message form from the assignment together.

**Open your files:**
- `index.html` — we'll add the form markup
- `index.js` — we'll handle the submit event

**Tell me what to type!**

<!--
You type, students direct. If someone suggests something incorrect, type it and let the class
see the result. Real debugging in the moment is more valuable than a clean demo.
-->

---

# Step 1 — Add the Form HTML

In `index.html`, above `<footer>`, add a new section:

```html
<section>
  <h2>Leave a Message</h2>
  <form name="leave_message">
    <label>Name:
      <input type="text" name="usersName" required>
    </label>
    <label>Email:
      <input type="email" name="usersEmail" required>
    </label>
    <label>Message:
      <textarea name="usersMessage" required></textarea>
    </label>
    <button type="submit">Submit</button>
  </form>
</section>
```

<!--
Point out the `name` attribute on the form — "leave_message". We'll use that to select the form in JS.
Also add the Messages section (id="messages") with an empty <ul> now, so it's ready for Step 3.
-->

---

# Step 2 — Handle the Submit Event

In `index.js`, select the form and listen for `"submit"`:

```javascript
let messageForm = document.forms["leave_message"];

messageForm.addEventListener("submit", function (event) {
  event.preventDefault();

  let name = event.target.usersName.value;
  let email = event.target.usersEmail.value;
  let message = event.target.usersMessage.value;

  console.log(name, email, message);
  messageForm.reset();
});
```

**Save and try it.** Check the browser console — you should see the values printed.

<!--
Pause after console.log works. Ask: "What happens if we remove event.preventDefault()?"
Let a student predict, then demo it (or describe what would happen).
The reset() call clears the fields after submit — ask: "What method clears the form?"
-->

---

# Step 3 — Display the Message on the Page

Inside the event listener, before `messageForm.reset()`:

```javascript
let messageSection = document.querySelector("#messages");
let messageList = messageSection.querySelector("ul");

let newMessage = document.createElement("li");
newMessage.innerHTML =
  `<a href="mailto:${email}">${name}</a>
   <span>${message}</span>`;

messageList.appendChild(newMessage);
```

**Ask the group:** What does `mailto:` do when someone clicks the link?

<!--
mailto: opens the user's default email app with the address pre-filled.
Clarify the template literal syntax — students are still getting used to backticks and ${}.
-->

---

# Step 4 — Add a Remove Button

Still inside the event listener, before `messageList.appendChild(newMessage)`:

```javascript
let removeButton = document.createElement("button");
removeButton.textContent = "remove";
removeButton.type = "button";

removeButton.addEventListener("click", function () {
  let entry = removeButton.parentNode;
  entry.remove();
});

newMessage.appendChild(removeButton);
```

**Ask the group:** What does `parentNode` refer to here?

<!--
parentNode of the removeButton is the <li> element (newMessage).
So entry.remove() deletes the entire message item, not just the button.
Draw the DOM tree on screen if it helps: <ul> → <li> → <a>, <span>, <button>
-->

---

<!-- _class: section-break -->

# Extension Activity

*Only if students are ready and time allows.*

---

# Extension — Hide the Messages Section When Empty

**Challenge:** Hide the `#messages` section (including the heading) when there are no messages. Show it again when a message is added.

**Think about it:**
- How do you check whether the `<ul>` is empty?
- What CSS property would you toggle?
- Which events would trigger the check?

> Hint: `messageList.children.length` tells you how many items are in the list.

<!--
This is Stretch Goal 1 from the assignment. Don't provide the solution — let students reason through it.
Possible approach: check children.length after append and after remove, then set
messageSection.style.display = "none" or "block" accordingly.
Students who finish can also tackle Stretch Goal 2: an edit button per message.
-->

---

# Assignment Preview

This week you'll add a full message form to your portfolio:

- **HTML:** form with name, email, and message fields + a messages list
- **JS:** submit event listener with `preventDefault`
- **JS:** display each message as a list item with a `mailto:` link and a remove button
- **CSS:** style the form fields, labels, and buttons (including mobile sizing)
- **Nav:** add a link to the "Leave a Message" section in your `<nav>`

**Stretch goals:** hide the messages section when empty; add an edit button per message.

<!--
Don't walk through every checkbox — students have the full assignment doc.
Draw attention to the CSS task: spacing, readable sizing on mobile, tap-friendly buttons.
Remind students to create a lesson-8 branch before they start coding.
-->

---

# Tips for the Assignment

1. **Do the HTML first** — get the form visible in the browser before writing any JS
2. **Test `preventDefault` early** — submit once without it so you see the refresh, then add it
3. **Use `console.log` often** — log `name`, `email`, and `message` before building the DOM
4. **Build the remove button last** — get the message displaying first, then add the button
5. **Stuck on CSS?** Open DevTools and experiment directly on the element before writing code

> Ask for hints, not answers: "My form resets but the list is empty — can you give me 3 hints?"

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel with form events and updating the DOM?

### Before next session:
- Work through the **lesson materials** (Odin Project — Asynchronous Code)
- Build the **message form** for your portfolio
- **Style** the form fields and buttons
- Post questions in the **Slack** `#discussion` channel anytime

<!--
Note any concepts where multiple students rated 1–2. Those are good candidates for a quick
async review or a 1:1 mention. Promises will come back in Lesson 9 — reassure students
who felt shaky on that part today.
-->

---

# Resources

| Resource | What it's for |
|----------|---------------|
| Odin Project — Asynchronous Code | Main reading for this lesson |
| MDN — `event.preventDefault` | Reference for stopping default behavior |
| MDN — `createElement` / `appendChild` | DOM manipulation reference |
| MDN — HTML Forms | Form elements and attributes |
| Slack `#discussion` channel | Questions between sessions |

> **Next week:** Fetch API — pulling real data from the internet using Promises!

---

<!-- _class: title -->

# Great work today!

## Your portfolio now listens to users.

Questions? Reach out on Slack anytime.
