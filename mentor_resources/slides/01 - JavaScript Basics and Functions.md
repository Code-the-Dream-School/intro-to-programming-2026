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
  h1 {
    color: #1a73e8;
  }
  h2 {
    color: #1a73e8;
  }
  code {
    background-color: #f0f4f8;
    padding: 2px 6px;
    border-radius: 4px;
  }
  pre code {
    padding: 16px;
  }
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

These slides are written in Marp markdown. You can present them two ways:

IN VS CODE:
1. Install the "Marp for VS Code" extension
2. Open this .md file
3. Click the Marp preview icon (top-right), or Command Palette > "Marp: Open Preview to the Side"
4. To export as PDF/PPTX: Command Palette > "Marp: Export Slide Deck"

IN THE BROWSER:
1. Go to https://web.marp.app/
2. Paste or upload this file
3. Present directly or export

Feel free to edit these slides to match your style and your cohort's needs!

Speaker notes like this one (inside HTML comments) won't appear on the slides.
They're just for you!
-->

<!-- _class: title-slide -->

# Lesson 1: JavaScript Basics and Functions

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

Since this is our first session, let's go around and share:

1. Your **name**
2. **Where you're joining from**
3. **Why you're interested in learning to code**

<!--
If the group is large, use the Zoom chat instead.
Consider a fun prompt like: "If you could build any app, what would it be?"
-->

---

# What You'll Learn This Week

- **Problem-solving** — the #1 developer skill
- **JavaScript basics** — variables, data types, conditionals
- **Naming conventions** — writing clean, readable code
- **Debugging basics** — finding and fixing errors
- **Functions** — reusable blocks of code
- **GitHub repos** — where developers store code

<!--
This is students' first week. Many concepts are introduced but the goal is
exposure, not mastery. Focus on making students feel welcome, building
confidence with variables and console.log(), and giving a taste of functions.
Don't try to cover everything — the lesson materials handle the rest.
-->

---

# I Do: Problem-Solving

The three steps:

1. **Understand the problem** — Rewrite it in your own words
2. **Plan** — What inputs? What output? What steps?
3. **Divide and conquer** — Break the big problem into smaller ones

> Don't jump straight into code. Plan first!

---

# I Do: Problem-Solving

**Discussion:** What's a non-coding problem you've solved by breaking it into smaller steps?

<!--
Give students a minute to think. This is a good icebreaker and helps
connect the concept to everyday life.
-->

---

# I Do: Variables

Variables are **containers that store data**.

```javascript
let firstName = "Maria";      // Can be reassigned later
const birthYear = 1995;        // Cannot be reassigned
```

- `let` — the value **can change**
- `const` — the value **stays the same**

> We avoid `var` in modern JavaScript.

---

# I Do: Data Types

This week focuses on three types:

**String** — text, wrapped in quotes
```javascript
let name = "Alejandro";
```

**Number** — integers and decimals
```javascript
let age = 28;
let temperature = 72.5;
```

**Boolean** — true/false values
```javascript
let isStudent = true;
```

---

# I Do: Conditionals

Conditionals let your code **make decisions**.

```javascript
let temperature = 75;

if (temperature > 80) {
    console.log("It's hot outside!");
} else if (temperature > 60) {
    console.log("Nice weather!");
} else {
    console.log("It's cold!");
}
```

**Zoom chat poll:** What will this print?
A) "It's hot outside!" — B) "Nice weather!" — C) "It's cold!"

---

# I Do: Conditionals — Answer

```javascript
if (temperature > 80) {         // 75 > 80? No — skip
    console.log("It's hot outside!");
} else if (temperature > 60) {  // 75 > 60? YES
    console.log("Nice weather!");
} else {
    console.log("It's cold!");
}
```

**Answer: B) "Nice weather!"**

JavaScript checks conditions **top to bottom** and runs the **first** block that is `true`.

---

# I Do: Functions

A function is a **reusable block of code** that performs a task.

```javascript
function greet() {
    return "Welcome to Code the Dream!";
}

console.log(greet());
```

Why use functions?
- **Reusability** — write once, use many times
- **Organization** — break code into logical pieces

---

# I Do: Functions with Parameters

Parameters let you **pass information into** a function.

```javascript
function greetStudent(name) {
    return "Hello, " + name + "!";
}

console.log(greetStudent("Maria"));  // "Hello, Maria!"
console.log(greetStudent("James"));  // "Hello, James!"
```

- `name` is the **parameter** (placeholder)
- `"Maria"` is the **argument** (actual value)

---

# I Do: Naming Conventions

JavaScript uses **camelCase** for variables and functions:

```javascript
// Good — clear and descriptive
let totalPrice = 29.99;
let firstName = "Maria";
function calculateSum(a, b) { return a + b; }
```

```javascript
// Not so good — hard to understand
let tp = 29.99;
let fn = "Maria";
function cs(a, b) { return a + b; }
```

---

# I Do: Debugging Basics

Bugs are **normal**! Your first debugging tool: `console.log()`

```javascript
let firstName = "Rubaina";
let lastName = "Roshan";
let fullName = firstName + lastName;

console.log("Full Name:", fullName);
// "Full Name: RubainaRoshan" — oops, forgot the space!
```

Common errors: syntax, reference, type, and logical.

---

<!--
Transition to We Do:
- Ask: "What questions do you have so far?"
- Remind students they don't need to memorize everything — the
  lesson materials are there to reference.
-->

# We Do: Let's Code Together! (15-20 min)

**I want to hear your ideas** — tell me what to type!

Open your browser console:
- **Chrome/Edge:** Right-click > Inspect > Console
- **Firefox:** Right-click > Inspect > Console

---

# We Do: Variables and Strings

**Challenge:** Create variables to introduce ourselves.

```javascript
let firstName = "Maria";
let lastName = "Santos";
let country = "Brazil";
```

**Ask the group:** How can we combine these into one sentence?

---

# We Do: String Concatenation

### Using the `+` operator
```javascript
let intro = "Hi! I'm " + firstName + " " + lastName
            + " from " + country + ".";
```

### Using template literals (backticks)
```javascript
let intro = `Hi! I'm ${firstName} ${lastName} from ${country}.`;
```

**Which do you find easier to read?**

---

# We Do: Writing a Conditional

**Challenge:** Check if someone is old enough to vote.

**What do we need?** (ask the group)

```javascript
let age = 17;

if (age >= 18) {
    console.log("You can vote!");
} else {
    console.log("Not old enough to vote yet.");
}
```

**Follow-up:** What if `age` is `18`? What about `21`?

---

# We Do: Writing a Function

**Challenge:** Write a function that makes a name uppercase.

**Walk through it step by step with the group.**

```javascript
function shoutName(name) {
    return name.toUpperCase();
}

console.log(shoutName("maria"));  // "MARIA"
console.log(shoutName("james"));  // "JAMES"
```

---

# We Do: Debugging Practice

**This code has a bug. Can you spot it?**

```javascript
function combineNames(first, last) {
    return first + last;
}

console.log(combineNames("Maria", "Santos"));
// Output: "MariaSantos" — Where's the space?
```

**How would you fix it?**

<!--
Let students suggest the fix before showing it.
This mirrors a real pattern from assignment Q13.
-->

---

# We Do: Debugging Practice — Fix

```javascript
function combineNames(first, last) {
    return first + " " + last;
}

console.log(combineNames("Maria", "Santos"));
// Output: "Maria Santos"
```

---

<!--
Transition to You Do:
Pick one of the options on the next slide based on your group's comfort level.
Set a timer for 5-10 minutes and let them know you're available for questions.
Embrace the silence — it means they're working!
-->

# You Do: Independent Practice (5-10 min)

Pick **one** to try on your own:

**A)** Create variables for your name and a hobby. Use `console.log()` to print a sentence about yourself.

**B)** Write an `if/else` that checks a number and prints whether it's positive or negative.

**C)** Write a function called `addNumbers` that takes two numbers and returns their sum.

---

# You Do: Share Out

**Who wants to share what they tried?**

- What did you write?
- Did it work on the first try?
- If not, how did you debug it?

<!--
Celebrate attempts, not just correct answers. Debugging is learning!
-->

---

# Assignment Preview

This week's assignment has **15 questions**:

- **Q1-Q3:** Creating variables (strings, numbers, booleans)
- **Q4-Q5:** String concatenation and arithmetic
- **Q6:** String methods
- **Q7-Q9:** Conditionals
- **Q10-Q11:** Number methods and type conversion
- **Q12-Q15:** Writing functions

Plus: Create your first **GitHub repository**!

---

# Tips for the Assignment

1. **Read the instructions carefully** — each question tells you exactly what to do
2. **Uncomment the `console.log()` lines** — remove `//` to see output
3. **Use `console.log()` liberally** — check your work as you go
4. **Try the Stretch Goals** if you want an extra challenge (optional!)

> Stuck? Ask an AI tool for **hints**, not answers.

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel with variables and `console.log()`?

### Before next session:
- Work through the **lesson materials** (Odin Project or Scrimba)
- Complete the **coding assignment** (15 questions)
- Create your **GitHub repository**
- Reach out on **Slack** if you get stuck!

---

# Resources

- **Odin Project** Fundamentals 1-3 *or* **Scrimba** JS Deep Dive
- **MDN:** [JavaScript Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
- **W3Schools:** [JavaScript Tutorial](https://www.w3schools.com/js/)
- **Help:** Post in the `discussion` Slack channel

> **Next week:** Loops and Arrays!

---

<!-- _class: title-slide -->

# Great job this week!

## You've taken your first step into programming.

Questions? Reach out on Slack anytime.
