# Lesson 7 Mentor Resource: The DOM API

## Lesson Overview
This week students learn about the Document Object Model (DOM): what it is, how to select elements, create elements, modify them, add styles dynamically, and handle events. They also learn about browser developer tools. The assignment is significant — students create a `js/index.js` file linked to their portfolio, use DOM manipulation to add a footer with the current year, dynamically populate a skills list from a JavaScript array, and build a "Leave a Message" form with full event handling (submit, display, and remove functionality).

This is where JavaScript and HTML/CSS come together in a powerful way. Students see how JavaScript can change what's on the page, which is the foundation for interactive web applications.

---

## Group Mentor Sessions

### Explore Session

**Warm-Up** (5-10 minutes)
- Ask: "When you click a button on a website and something changes without the page reloading, how do you think that works?"
- Or: "Have you ever used 'Inspect Element' in your browser? What did you see?"

**I Do** (~15 minutes)
- Explain the DOM as a tree structure: the HTML document is represented as objects that JavaScript can interact with.
- Demo key DOM methods in the browser console:
  - `document.querySelector()` to select an element
  - `document.createElement()` to create a new element
  - `.textContent` or `.innerHTML` to set content
  - `.appendChild()` to add elements to the page
- Show how to add an event listener to a button.

**We Do** (15-20 minutes)
- Build a simple interactive example together: a button that, when clicked, adds a new list item to a `<ul>` on the page. Walk through each step (select the list, create an item, set text, append it).
- Discussion: "What's the difference between `textContent` and `innerHTML`? When would you use each?"
- If using breakout rooms: give each group a challenge like "Use JavaScript to change the background color of the page when a button is clicked." Rotate and ask "How did you select the element? What event did you listen for?"

**You Do** (15-20 minutes)
- Have students open their portfolio's `index.html`, create the `js/index.js` file, and link it with a `<script>` tag.
- Challenge: "Can you use JavaScript to add a footer element to the page with your name and the current year?"

**Wrap-Up** (5-10 minutes)
- Ask: "How does it feel to use JavaScript to change what's on a web page?"
- Preview next week: async programming and promises — understanding how JavaScript handles tasks that take time.
- Remind students that the form and message functionality is the bulk of this week's work.

---

### Apply Session

**Warm-Up** (5-10 minutes)
- Ask: "Has anyone gotten the footer to show up on their portfolio yet?"
- Quick question: "What method do you use to select an element by its ID?"

**I Do** (~15 minutes)
- Pull up the assignment and walk through the footer section step by step:
  1. Create a footer element with `createElement`
  2. Use `new Date()` and `getFullYear()` for the year
  3. Select the body and append the footer
- Demo the skills list: show how a `for` loop iterates over an array and creates/appends `<li>` elements.

**We Do** (15-20 minutes)
- Work through the form handling together. This is the most complex part:
  1. Select the form using `document.forms`
  2. Add an event listener for "submit"
  3. Use `event.preventDefault()` to stop the page from refreshing
  4. Get form values from `event.target`
  5. Create a list item, set its innerHTML, and append it
- Ask students to predict: "What happens if we don't call `preventDefault()`?"

**You Do** (15-20 minutes)
- Give students time to implement the "remove" button functionality and the form reset.
- For students who finish early: encourage the stretch goals (hiding the messages section when empty, adding an edit button).

**Wrap-Up** (5-10 minutes)
- Ask: "What's the most surprising thing about how the DOM works?"
- Remind students about styling their form in CSS.
- Point ahead: async programming — understanding how JavaScript handles operations that aren't instant.

---

## 1:1 Session Guide

- **Build rapport**: This is a big week with a lot of new concepts. Check in on how the student is handling the workload.
- **Check understanding**: Ask the student to explain the flow of their form handling code. What happens when the user clicks Submit? Walk through it step by step.
- **Encourage independence**: If the form isn't working, guide the student to use `console.log` at each step to see what values they're getting. Ask: "What does `event.target.usersName.value` give you?"
- **Goal-setting**: The assignment has multiple parts (footer, skills list, form, messages, remove button). Help the student break it into smaller milestones.
- **Common sticking points this week**:
  - Forgetting `event.preventDefault()` — the page refreshes and students think their code isn't working
  - The `<script>` tag placement: it should be at the bottom of `<body>` so the HTML loads before the JS runs
  - Confusing `textContent` with `innerHTML` — using `textContent` when they need HTML elements inside
  - Event listener syntax: passing the function reference vs. calling it (no parentheses)
  - The remove button: understanding DOM traversal with `parentNode`
