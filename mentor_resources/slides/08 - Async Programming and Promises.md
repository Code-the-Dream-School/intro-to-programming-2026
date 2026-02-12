---
marp: true
theme: default
paginate: true
style: |
  section {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #ffffff;
    color: #333333;
  }
  h1 { color: #1a73e8; }
  h2 { color: #1a73e8; }
  code {
    background-color: #f0f4f8;
    padding: 2px 6px;
    border-radius: 4px;
  }
  pre code { padding: 16px; }
  section.title-slide {
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  blockquote {
    border-left: 4px solid #1a73e8;
    padding-left: 16px;
    color: #555;
  }
---

<!--
FOR MENTORS: Using These Slides

IN VS CODE:
1. Install the "Marp for VS Code" extension
2. Open this .md file
3. Command Palette > "Marp: Open Preview to the Side"
4. Export: Command Palette > "Marp: Export Slide Deck"

IN THE BROWSER:
1. Go to https://web.marp.app/
2. Paste or upload this file
3. Present directly or export
-->

<!-- _class: title-slide -->

# Lesson 8: Async Programming and Promises

## Intro to Programming

### Code the Dream

---

# Today's Game Plan

| Section | Time |
|---------|------|
| Warm-Up | 5 min |
| I Do | 10-15 min |
| We Do | 15-20 min |
| You Do | 5-10 min |
| Wrap-Up | 5 min |

---

# Warm-Up (5 min)

**Zoom chat:**

Imagine you're at a restaurant. You order food, then:
- **Option A:** Stare at the kitchen door until it's ready
- **Option B:** Chat with friends while you wait

Which sounds better? Which sounds like how a web page should work?

<!--
Option A is synchronous (blocking), Option B is asynchronous.
This analogy sets up the entire lesson.
-->

---

# What You'll Learn This Week

- **Synchronous vs. asynchronous** code
- **Promises** — handling things that take time
- **Event listeners + forms** — your assignment focus
- **preventDefault** — controlling form behavior

---

# I Do: Synchronous Code

Synchronous = **one thing at a time**, in order.

```javascript
console.log("Step 1");
console.log("Step 2");
console.log("Step 3");
```

Output is always: Step 1, Step 2, Step 3.

Like a **phone call** — you wait for the other person to finish before you speak.

---

# I Do: Asynchronous Code

Asynchronous = **start a task and move on** without waiting.

```javascript
console.log("Order placed");
setTimeout(function() {
    console.log("Food is ready!");
}, 3000);
console.log("Chatting with friends...");
```

Output: "Order placed", "Chatting with friends...", then 3 seconds later, "Food is ready!"

Like a **text message** — you send it and keep doing other things.

---

# I Do: Why Async Matters

Web pages need to stay responsive while waiting for:
- Data from a server (API calls)
- User input (form submissions)
- File loading (images, scripts)

If these were synchronous, your page would **freeze** every time it waited for something.

---

# I Do: Promises

A **Promise** represents a value that isn't available yet.

It has three states:
- **Pending** — still waiting
- **Fulfilled** — success! Here's the data.
- **Rejected** — something went wrong.

Think of it as an IOU: "I promise to give you data when it's ready."

> We won't create promises yet — just understand the concept for next week's `fetch` lesson.

---

# I Do: Event Listeners (Review)

Remember from last week:

```javascript
button.addEventListener("click", function() {
    console.log("Clicked!");
});
```

This week, we'll use event listeners on **forms** — listening for the `"submit"` event.

---

# I Do: Form Events and preventDefault

When a form submits, the browser **refreshes the page** by default. We don't want that!

```javascript
let form = document.querySelector("form");

form.addEventListener("submit", function(event) {
    event.preventDefault();  // Stop the refresh!

    let name = event.target.usersName.value;
    console.log("Name:", name);
});
```

`event.preventDefault()` is the key line — always put it first.

---

<!--
Transition to We Do:
- Ask: "What questions do you have about sync vs. async?"
- Reassure students: promises will click more next week with fetch.
  Today is about forms and event listeners.
-->

# We Do: Build a Form Together! (15-20 min)

Let's add a "Leave a Message" form to the portfolio.

Open your `index.html` and `index.js`.

---

# We Do: HTML Form

Add this to your `index.html`:

```html
<section>
    <h2>Leave a Message</h2>
    <form name="leave_message">
        <label>Name: <input type="text" name="usersName" required></label>
        <label>Email: <input type="email" name="usersEmail" required></label>
        <label>Message: <textarea name="usersMessage" required>
        </textarea></label>
        <button type="submit">Submit</button>
    </form>
</section>
```

---

# We Do: Handle the Submit

In `index.js`:

```javascript
let messageForm = document.forms["leave_message"];

messageForm.addEventListener("submit", function(event) {
    event.preventDefault();

    let name = event.target.usersName.value;
    let email = event.target.usersEmail.value;
    let message = event.target.usersMessage.value;

    console.log(name, email, message);
    messageForm.reset();
});
```

**Save, refresh, submit the form.** Check the console!

---

# We Do: Display Messages

Let's show messages on the page instead of just the console:

```javascript
let messageList = document.querySelector("#messages ul");
let newMessage = document.createElement("li");

newMessage.innerHTML = `<a href="mailto:${email}">${name}</a>
    <span>${message}</span>`;

messageList.appendChild(newMessage);
```

**Ask the group:** What does `mailto:` do?

---

# We Do: Add a Remove Button

```javascript
let removeButton = document.createElement("button");
removeButton.textContent = "remove";
removeButton.type = "button";

removeButton.addEventListener("click", function() {
    let entry = this.parentNode;
    entry.remove();
});

newMessage.appendChild(removeButton);
```

**Zoom chat:** What does `this.parentNode` refer to?

<!--
Walk through the DOM traversal: the button's parent is the <li>,
so entry.remove() deletes the entire message.
-->

---

<!--
Transition to You Do:
Set a timer for 5-10 minutes.
-->

# You Do: Independent Practice (5-10 min)

Try **one** of these:

**A)** Create the form HTML and verify it appears in your browser.

**B)** Add the submit event listener and log the form values to the console.

**C)** Display submitted messages on the page with a remove button.

---

# You Do: Share Out

**Who wants to demo their form?**

- Did `preventDefault` work?
- Were you able to see values in the console?

---

# Assignment Preview

This week you'll build a **message form** for your portfolio:

- HTML form with name, email, and message fields
- Event listener for submit (with `preventDefault`)
- Display messages as a list with:
  - Clickable name (links to email)
  - Message text
  - Remove button
- Style the form in your CSS

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel with event listeners and forms?

### Before next session:
- Work through the **lesson materials** (async, promises)
- Build the **message form** for your portfolio
- **Style** the form and messages
- Reach out on **Slack** if you get stuck!

---

# Resources

- **Odin Project:** Asynchronous Code
- **Scrimba:** Events, Creating & Modifying Elements
- **MDN:** [preventDefault](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault) | [Forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)

> **Next week:** Fetch API — pulling real data from the internet!

---

<!-- _class: title-slide -->

# Great work this week!

## Your portfolio now responds to user input.

Questions? Reach out on Slack anytime.
