---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 7: The DOM API"
---

# Lesson 7: The DOM API

**Mentor Session Slide Deck**

Topics: The DOM, Selecting Elements, Creating & Modifying Elements, Events

---

# What is the DOM?

The **Document Object Model** is how JavaScript "sees" your HTML page.

The browser reads your HTML and builds a **tree of objects**:

```
document
 └── html
      ├── head
      │    └── title
      └── body
           ├── h1
           ├── section
           │    ├── h2
           │    └── p
           └── footer
```

JavaScript can **read**, **change**, **add**, and **remove** any part of this tree.

---

# Selecting Elements

Grab elements from the DOM so you can work with them:

```javascript
// By ID — returns one element
let header = document.getElementById("main-title");

// By CSS selector — returns the first match
let firstButton = document.querySelector(".btn");

// By CSS selector — returns ALL matches
let allButtons = document.querySelectorAll(".btn");
```

**Tip**: `querySelector` is the most versatile — it accepts any CSS selector.

---

# Creating New Elements

Build elements with JavaScript and add them to the page:

```javascript
// 1. Create the element
let newItem = document.createElement("li");

// 2. Set its content
newItem.textContent = "Learn the DOM";

// 3. Find where it should go
let list = document.querySelector("#todo-list");

// 4. Append it
list.appendChild(newItem);
```

After this runs, a new `<li>` appears inside `#todo-list` — without editing the HTML file!

---

# `textContent` vs `innerHTML`

```javascript
let box = document.querySelector("#output");

// textContent — treats everything as plain text
box.textContent = "<strong>Hello</strong>";
// Displays: <strong>Hello</strong> (shows the tags as text)

// innerHTML — parses HTML tags
box.innerHTML = "<strong>Hello</strong>";
// Displays: Hello (bold text)
```

**Rule of thumb**:
- Use `textContent` for plain text (safer)
- Use `innerHTML` when you need HTML elements inside

---

# Modifying Existing Elements

```javascript
let title = document.querySelector("h1");

// Change text
title.textContent = "Welcome to My Site";

// Change styles
title.style.color = "#e94560";
title.style.fontSize = "48px";

// Add/remove CSS classes
title.classList.add("highlighted");
title.classList.remove("old-style");
```

You can change **anything**: text, styles, attributes, classes.

---

# Events: Responding to User Actions

An **event listener** waits for something to happen, then runs a function:

```javascript
let button = document.querySelector("#greet-btn");

button.addEventListener("click", function() {
    alert("Hello there!");
});
```

Common events:
| Event | Triggers when... |
|-------|-------------------|
| `"click"` | User clicks an element |
| `"submit"` | A form is submitted |
| `"keydown"` | A key is pressed |
| `"mouseover"` | Mouse hovers over an element |

---

# Handling Form Submissions

```javascript
let form = document.querySelector("#signup-form");

form.addEventListener("submit", function(event) {
    // Stop the page from refreshing!
    event.preventDefault();

    // Get the form values
    let name = event.target.userName.value;
    let email = event.target.userEmail.value;

    console.log(`Name: ${name}, Email: ${email}`);

    // Clear the form
    form.reset();
});
```

**Critical**: `event.preventDefault()` stops the default behavior (page refresh).

---

# Putting It Together: A Dynamic List

```javascript
let form = document.querySelector("#task-form");
let taskList = document.querySelector("#task-list");

form.addEventListener("submit", function(event) {
    event.preventDefault();

    let taskText = event.target.taskInput.value;

    // Create the list item
    let newTask = document.createElement("li");
    newTask.textContent = taskText;

    // Create a remove button
    let removeBtn = document.createElement("button");
    removeBtn.textContent = "Remove";
    removeBtn.addEventListener("click", function() {
        newTask.remove();
    });

    newTask.appendChild(removeBtn);
    taskList.appendChild(newTask);
    form.reset();
});
```

---

# The DOM Manipulation Pattern

Almost every DOM task follows this pattern:

1. **Select** an existing element (`querySelector`)
2. **Create** a new element (`createElement`)
3. **Set** its content or attributes (`textContent`, `innerHTML`, `classList`)
4. **Attach** event listeners if needed (`addEventListener`)
5. **Append** it to the page (`appendChild`)

Once you see this pattern, DOM manipulation becomes predictable.

---

# Try This!

Build a **"Favorites List"** feature:

1. Create HTML with an input, a button, and an empty `<ul>`
2. In JavaScript:
   - Select the button and list
   - Add a click event to the button
   - When clicked, create an `<li>` with the input's value
   - Add a "remove" button to each item
   - Append the item to the list
   - Clear the input

**Bonus**: Add validation — don't allow blank items!

---

# Key Takeaways

- The **DOM** is JavaScript's representation of your HTML page as a tree of objects
- **Select** elements with `querySelector` or `getElementById`
- **Create** elements with `createElement`, set content, then `appendChild`
- **Events** let you respond to user actions — always use `addEventListener`
- **`preventDefault()`** stops forms from refreshing the page
- Follow the pattern: Select → Create → Set → Listen → Append

**Next week**: Asynchronous Programming and Promises — how JavaScript handles tasks that take time
