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
  Mentor 1 leads the Explore section (slides 3–14).
  Mentor 2 leads the Apply section (slides 15–24).
  Both mentors stay on screen throughout. The second mentor can support chat
  and answer questions during Explore, then takes over at the Apply section break.

Speaker notes (mentor-only guidance) appear in comment blocks like this one.
In Marp presenter mode, notes display in your presenter panel.
-->

<!-- _class: title -->

# Lesson 7: The DOM API

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Explain what the DOM is and how JavaScript uses it
- Select elements on a page using `querySelector`
- Create new elements and add them to the page
- Use a loop to build a list from an array
- Get the current year dynamically using the `Date` object

<!--
This session is very hands-on. Students will leave with working JavaScript
in their portfolio projects. Keep the energy high — seeing their own page
change in real time is a motivating moment.
-->

---

<!-- _class: section-break -->

# Explore

---

# What Is the DOM?

The **Document Object Model (DOM)** is a tree of every element on your page.

When your browser loads HTML, it builds this tree.
JavaScript can then read and change that tree.

> The DOM is what makes web pages interactive — without reloading the page.

<!--
Warm-up activity before this slide (optional):
Ask students to open any website, right-click an element, and choose "Inspect."
Have them try changing the text of a heading in the Elements panel.
It's a great "wow moment" — and it shows the DOM is live.
-->

---

# The DOM Tree

Your HTML becomes a tree of **nodes**.

```
document
  └── <html>
        ├── <head>
        │     └── <title>
        └── <body>
              ├── <h1>
              ├── <section>
              └── <footer>
```

- Every tag is a **node**
- Nodes have **parents**, **children**, and **siblings**

<!--
Use the "family tree" analogy from the lesson material.
A <section> can be a parent to an <h2> and a <ul> inside it.
Students don't need to memorize this — just understand the concept
before they start selecting and building nodes.
-->

---

# Selecting Elements

`querySelector` finds the **first** matching element.

```javascript
// Select by tag name
let footer = document.querySelector("footer");

// Select by ID
let skills = document.querySelector("#skills");

// Select by class
let items = document.querySelector(".card");
```

> CSS selectors work here — `#` for ID, `.` for class.

<!--
Students will use querySelector throughout the assignment.
Mention: querySelector searches the whole document by default.
They'll also query a specific element in the assignment (skillsSection.querySelector).
-->

---

# querySelector vs. querySelectorAll

| Method | Returns |
|--------|---------|
| `querySelector` | The **first** match (one element) |
| `querySelectorAll` | **All** matches (a list) |

```javascript
// Returns the first <h2> it finds
let heading = document.querySelector("h2");

// Returns every <h2> on the page
let allHeadings = document.querySelectorAll("h2");
```

<!--
Keep this brief. The assignment only uses querySelector.
Just flag that querySelectorAll exists so students aren't confused if
they see it in the lesson materials.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**You want to select the element with `id="skills"`. Which is correct?**

A) `document.querySelector("skills")`

B) `document.querySelector(".skills")`

C) `document.querySelector("#skills")`

D) `document.querySelector("<skills>")`

<!--
Answer: C.
Teaching note: CSS selector syntax — # for ID, . for class, nothing for tag.
This matters directly for the assignment where students select the skills section by ID.
Give students 20–30 seconds to think before asking for answers.
-->

---

# Creating Elements

Three steps to add something new to the page:

```javascript
// Step 1: Create a new element
let paragraph = document.createElement("p");

// Step 2: Set its content
paragraph.textContent = "Hello from JavaScript!";

// Step 3: Add it to the page
document.body.appendChild(paragraph);
```

No need to edit your HTML file — JavaScript does it.

<!--
Emphasize the three-step pattern. Students will repeat this pattern
multiple times in the assignment (creating a footer, creating list items).
-->

---

# innerHTML vs. textContent

Both set the content of an element — but they are different.

```javascript
// textContent — plain text only
paragraph.textContent = "Hello!";

// innerHTML — can include HTML tags and entities
paragraph.innerHTML = "&copy; 2025 Maria Santos";
```

- Use `textContent` for plain text
- Use `innerHTML` when you need HTML (like `&copy;`)

<!--
Students use innerHTML in the copyright footer part of the assignment
(to render the © symbol) and textContent in the skills list loop.
Worth spending an extra moment here.
-->

---

# Getting the Current Year

Use the `Date` object — no hardcoding!

```javascript
let today = new Date();
let thisYear = today.getFullYear();

console.log(thisYear);  // e.g. 2025
```

> If you hardcode `2024`, your site will be wrong next year.

<!--
This is a small but satisfying concept. The assignment specifically warns
students not to hardcode the year — this slide explains why and how.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What does `document.createElement("li")` do?**

A) Finds an existing `<li>` element on the page

B) Creates a new `<li>` element in memory

C) Deletes an `<li>` element from the page

D) Changes the text of an existing `<li>` element

<!--
Answer: B.
Key teaching point: createElement creates the element in memory but doesn't
add it to the page yet. You still need appendChild (or similar) to actually
place it. This is a common source of confusion.
-->

---

# Building a List with a Loop

Combine arrays, loops, and DOM methods:

```javascript
let skills = ["JavaScript", "HTML", "CSS"];
let skillsList = document.querySelector("#skills ul");

for (let i = 0; i < skills.length; i++) {
    let skill = document.createElement("li");
    skill.textContent = skills[i];
    skillsList.appendChild(skill);
}
```

> This is the core pattern for the skills section in your assignment.

<!--
Walk through this slowly. Students have seen arrays and loops before — 
this is the first time those concepts connect to the page they can see.
Ask: "What does skills[i] refer to on the first loop? The second?"
-->

---

<!-- _class: cfu -->

# Check for Understanding

**In the loop above, what does `skillsList.appendChild(skill)` do?**

A) Creates a new `<li>` element

B) Sets the text inside `<li>`

C) Adds the `<li>` into the `<ul>` on the page

D) Selects the `<ul>` from the document

<!--
Answer: C.
Reinforce the three-step pattern: create → set content → append.
Each line in the loop body is one of those steps.
If students are confused, draw the three steps on a whiteboard or ask
them to match each line to a step.
-->

---

<!-- _class: section-break -->

# Apply

<!--
Mentor 2 leads from here (suggested).
Before presenting: open your portfolio project in VS Code and a browser side by side.
Students should have their own portfolio projects open too.
Goal: by the end of Apply, every student has working JS in their portfolio.
-->

---

# Core Activity: Live Coding Demo

**We'll build the assignment together, step by step.**

Open your portfolio project now:
- Open `index.html` and `index.js` in your editor
- Open `index.html` in your browser

> If you don't have `js/index.js` yet, we'll create it together.

<!--
Mentor creates the file live if needed. The goal is to model the workflow,
not to rush through the code. Pause after each step and ask students
to predict what will appear before refreshing the browser.
-->

---

# Step 1 — Link JavaScript to HTML

In `index.html`, add this just before the closing `</body>` tag:

```html
<script src="js/index.js"></script>
```

Then create the file `js/index.js`.

Open `index.js` and add:

```javascript
console.log("JavaScript is connected!");
```

**Save and refresh.** Check the browser console. Do you see the message?

<!--
Chrome/Edge: Right-click → Inspect → Console tab
Firefox: Right-click → Inspect → Console tab
This is a confidence check — if the console.log appears, the connection works.
Common issue: path is wrong (e.g. "index.js" instead of "js/index.js").
-->

---

# Step 2 — Add a Footer with JavaScript

In `index.html`, add `<footer></footer>` before the `<script>` tag.

Then in `index.js`:

```javascript
let today = new Date();
let thisYear = today.getFullYear();

let footer = document.querySelector("footer");
let copyright = document.createElement("p");
copyright.innerHTML = `&copy; ${thisYear} Your Name`;
footer.appendChild(copyright);
```

**Save and refresh.** You should see your name and year at the bottom.

<!--
Pause before refreshing and ask: "What do you expect to see?"
Have students use their own names. If someone sees nothing, check:
  1. Is the <footer> element in the HTML?
  2. Is the script tag in the right place (after <footer>)?
  3. Any errors in the console?
-->

---

# Step 3 — Add a Skills Section in HTML

Before moving to JavaScript, add this to `index.html`:

```html
<section id="skills">
  <h2>Skills</h2>
  <ul></ul>
</section>
```

Place it above your "Connect" section.

**Save and refresh.** You should see the "Skills" heading.

<!--
The empty <ul> is intentional — JavaScript will fill it in the next step.
If students already have a skills section, help them add the id="skills"
attribute and the empty <ul>.
-->

---

# Step 4 — Build the Skills List

Back in `index.js`, add:

```javascript
let skills = ["JavaScript", "HTML", "CSS", "GitHub"];

let skillsSection = document.querySelector("#skills");
let skillsList = skillsSection.querySelector("ul");

for (let i = 0; i < skills.length; i++) {
    let skill = document.createElement("li");
    skill.textContent = skills[i];
    skillsList.appendChild(skill);
}
```

**Save and refresh.** Your skills should appear as a list.

<!--
Point out that skillsList is queried on skillsSection (not document).
This is a pattern from the assignment instructions and worth highlighting.
Ask students to add their own real skills to the array before moving on.
-->

---

<!-- _class: section-break -->

# Extension Activity

*Only if students are ready and time allows.*

---

# Extension — Highlight a Skill on Click

Add an event listener to make skills interactive:

```javascript
let allSkills = skillsList.querySelectorAll("li");

allSkills.forEach(function(item) {
    item.addEventListener("click", function() {
        item.style.fontWeight = "bold";
        item.style.color = "#FF5C35";
    });
});
```

**Try it:** Click a skill in the browser. What happens?

<!--
This introduces event listeners in a low-stakes way.
forEach is new here — briefly explain it as "do this for each item in the list."
Challenge: can students make a second click undo the highlight?
  Hint: check item.style.fontWeight — if it's "bold", reset it; otherwise set it.
Don't feel pressure to finish. This is a stretch goal.
-->

---

# Assignment Preview

This week you will connect JavaScript to your portfolio:

- Create `js/index.js` and link it to your HTML with `<script>`
- **Footer:** use `new Date()` to insert copyright year and your name
- **Skills:** create an array, loop through it, and build a `<li>` for each skill
- **Style:** use flexbox or grid to lay out your skills in CSS

> By the end: your HTML provides the structure, your JS fills in the content.

<!--
The assignment also has a stretch goal: include the © symbol using &copy; in innerHTML.
Point students to the hint comments in the assignment — they name the exact methods
they'll need (querySelector, createElement, appendChild, getFullYear).
-->

---

# Tips for the Assignment

1. **Work in small steps** — add one piece, refresh, check the console
2. **Use `console.log()`** to inspect variables before using them
3. **Check your selectors** — if nothing appears, `console.log(footer)` to see if it's `null`
4. **Stuck on a method?** MDN has clear examples for every DOM method
5. **Ask for hints, not answers:**

> "My querySelector is returning null. Can you give me a hint about what might be wrong?"

<!--
The most common bug: querySelector returns null because:
  - The element doesn't exist in HTML yet
  - The selector syntax is wrong (missing # or .)
  - The script runs before the element is in the DOM (script tag placement)
Encourage students to post their error messages in Slack — not just "it doesn't work."
-->

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel selecting elements and adding them to the page?

### Before next session:
- Complete the **lesson materials** (Odin Project or Scrimba)
- Finish the **assignment** — footer, skills list, and CSS styling
- Post questions in the **Slack** `#discussion` channel anytime

<!--
If confidence is mostly 1–2: reassure students that the assignment
has detailed hints for every step. They don't need to have it all memorized —
they just need to know where to look.
If confidence is 3–5: encourage them to try the event listener extension.
-->

---

# Resources

| Resource | What it's for |
|----------|---------------|
| Odin Project — DOM Manipulation | Written lesson with exercises |
| Odin Project — Form Basics | Background for next week |
| Scrimba — JavaScript Deep Dive | Video walkthroughs |
| MDN — Introduction to the DOM | Reference for all DOM methods |
| MDN — Document.querySelector | Selector syntax and examples |

> **Next week:** Async Programming and Promises!

---

<!-- _class: title -->

# Great work today!

## Your portfolio is now powered by JavaScript.

Questions? Reach out on Slack anytime.
