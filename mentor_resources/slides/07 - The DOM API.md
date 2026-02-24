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

# Lesson 7: The DOM API

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

Open any website, right-click an element, and choose "Inspect." Can you change the text of a heading in the Elements panel?

<!--
This is a wow moment for many students — realizing they can
modify any page in their browser. It's a natural intro to the DOM.
-->

---

# What You'll Learn This Week

- **The DOM** — what it is and why it matters
- **Selecting elements** — finding things on the page
- **Creating elements** — adding content with JavaScript
- **Event listeners** — responding to user actions
- **Connecting JS to your portfolio** — footer, skills list

---

# I Do: What Is the DOM?

The **Document Object Model** is a tree of every element on your page.

Your browser reads HTML and builds this tree. JavaScript can then:
- **Find** elements
- **Change** their content
- **Add** new elements
- **Remove** elements
- **Listen** for events (clicks, typing, etc.)

> The DOM is what makes web pages interactive.

---

# I Do: Selecting Elements

```javascript
// By ID
let footer = document.querySelector("#footer");

// By tag
let headings = document.querySelectorAll("h2");

// By class
let items = document.querySelectorAll(".skill-item");
```

- `querySelector` — returns the **first** match
- `querySelectorAll` — returns **all** matches

---

# I Do: Creating Elements

```javascript
// 1. Create a new element
let paragraph = document.createElement("p");

// 2. Set its content
paragraph.textContent = "Hello from JavaScript!";

// 3. Add it to the page
document.body.appendChild(paragraph);
```

This adds a new `<p>` at the bottom of the page — without editing your HTML file.

---

# I Do: A Real Example — Copyright Footer

```javascript
let today = new Date();
let thisYear = today.getFullYear();

let footer = document.querySelector("footer");
let copyright = document.createElement("p");
copyright.innerHTML = `&copy; ${thisYear} Maria Santos`;

footer.appendChild(copyright);
```

This dynamically inserts the current year — it updates automatically!

---

# I Do: Loops + DOM

Build a skills list from an array:

```javascript
let skills = ["JavaScript", "HTML", "CSS", "GitHub"];
let skillsList = document.querySelector("#skills ul");

for (let i = 0; i < skills.length; i++) {
    let skill = document.createElement("li");
    skill.textContent = skills[i];
    skillsList.appendChild(skill);
}
```

> This is exactly what you'll do in the assignment.

---

# I Do: Event Listeners

Make your page respond to user actions:

```javascript
let button = document.querySelector("#myButton");

button.addEventListener("click", function() {
    alert("Button clicked!");
});
```

- First argument: the **event** type (`"click"`)
- Second argument: the **callback** function (what to do)

---

<!--
Transition to We Do:
- Ask: "What questions do you have about the DOM?"
- Open browser DevTools to show the DOM tree.
-->

# We Do: Let's Code Together! (15-20 min)

Open your portfolio project. Create `js/index.js` and link it in your HTML:

```html
<!-- Before </body> -->
<script src="js/index.js"></script>
```

---

# We Do: Add a Footer with JavaScript

**Step 1:** Add `<footer></footer>` to your HTML (before the `<script>` tag).

**Step 2:** In `index.js`, let's write the code together:

```javascript
let today = new Date();
let thisYear = today.getFullYear();
let footer = document.querySelector("footer");
let copyright = document.createElement("p");
copyright.innerHTML = `&copy; ${thisYear} Maria Santos`;
footer.appendChild(copyright);
```

**Save and refresh.** What appears?

---

# We Do: Build a Skills List

**Ask the group:** What skills should we include?

```javascript
let skills = ["JavaScript", "HTML", "CSS", "GitHub"];
let skillsList = document.querySelector("#skills ul");

for (let i = 0; i < skills.length; i++) {
    let skill = document.createElement("li");
    skill.textContent = skills[i];
    skillsList.appendChild(skill);
}
```

**Follow-up:** How would we add a new skill to the array?

---

# We Do: Event Listener Demo

Let's make something happen on click:

```javascript
let heading = document.querySelector("h1");

heading.addEventListener("click", function() {
    heading.style.color = "red";
});
```

**Zoom chat:** What do you think happens when you click the heading?

<!--
Let students predict before you demo. Try changing the color
to different values. This builds excitement for the form work
they'll do next week.
-->

---

<!--
Transition to You Do:
Set a timer for 5-10 minutes.
-->

# You Do: Independent Practice (5-10 min)

Try **one** of these in your `index.js`:

**A)** Use `createElement` and `appendChild` to add a new paragraph to your page.

**B)** Create an array and use a loop to build a list on the page.

**C)** Add an event listener that changes something when you click an element.

---

# You Do: Share Out

**Who wants to share what they built?**

- What DOM methods did you use?
- Did the DevTools help you debug?

---

# Assignment Preview

This week you'll connect JavaScript to your portfolio:

- Create `js/index.js` and link it to your HTML
- **Footer:** dynamically insert copyright year and your name
- **Skills:** build a list from an array using a loop
- **Style** your skills section with flexbox or grid

> Your HTML provides the structure, your JS fills in the content!

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel selecting and creating DOM elements?

### Before next session:
- Work through the **lesson materials** (Odin Project or Scrimba)
- **Add JavaScript** to your portfolio (footer + skills)
- **Style** your skills section
- Reach out on **Slack** if you get stuck!

---

# Resources

- **Odin Project:** DOM Manipulation and Events, Form Basics
- **Scrimba:** What is the DOM?, Creating & Modifying Elements, Events
- **MDN:** [Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

> **Next week:** Async Programming and Promises!

---

<!-- _class: title-slide -->

# Great work this week!

## Your portfolio is now interactive.

Questions? Reach out on Slack anytime.
