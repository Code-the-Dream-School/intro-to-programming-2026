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
  One mentor leads the Explore section (slides 3–16).
  The other leads the Apply section (slides 17–28).
  Both mentors stay on screen throughout. The second mentor can support questions during Explore.

Speaker notes (mentor-only guidance) appear in comment blocks like this one.
In Marp presenter mode, notes display in your presenter panel.
-->

<!-- _class: title -->

# Lesson 1: JavaScript Basics and Functions

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Describe the three steps of the problem-solving process
- Create variables and identify common data types
- Write a basic conditional statement
- Write and call a function
- Use `console.log()` to check your code

---

<!-- _class: section-break -->

# Explore

---

# The Three Steps of Problem-Solving

1. **Understand** — Rewrite the problem in your own words
2. **Plan** — What are the inputs? What is the output?
3. **Divide** — Break the problem into smaller steps

> Don't jump straight into code. Plan first!

<!--
Give a non-coding example: planning a trip.
  Understand: Where am I going and why?
  Plan: What route? What do I pack?
  Divide: Book flights first, then hotel, then activities.
Then connect it to the assignment: 15 questions — tackle one at a time.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**Which step comes first when you get a new coding problem?**

A) Start typing code right away

B) Rewrite the problem in your own words

C) Search for the answer online

D) Ask a classmate to solve it

<!--
Answer: B.
Goal: students see "think before you code" as a professional skill, not just a classroom rule.
Give students a moment to think before calling on someone.
-->

---

# Variables

A variable is a **container that stores a value**.

```javascript
let firstName = "Maria";   // text — can change later
const birthYear = 1995;    // number — cannot change
```

- `let` — the value **can be reassigned**
- `const` — the value **stays the same**

> We avoid `var` in modern JavaScript.

<!--
Students often wonder which to use. A practical rule: use const by default.
Switch to let only if you know the value will change (like a counter).
Note: the assignment uses let throughout, and that's fine for now.
-->

---

# Data Types — Text and Numbers

**String** — text, wrapped in quotes

```javascript
let city = "Chicago";
let greeting = 'Hello!';
```

**Number** — integers, decimals, and negatives

```javascript
let age = 28;
let price = 9.99;
let debt = -50;
```

---

# Data Types — Booleans and NaN

**Boolean** — only two possible values

```javascript
let isStudent = true;
let hasGraduated = false;
```

**NaN** — "Not a Number" — what you get from invalid math

```javascript
let result = 4 * "hello";   // NaN
```

<!--
NaN shows up in Q2 of the assignment. Students are often surprised JavaScript
doesn't throw an error — it just returns NaN.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What data type is `"42"`?**

A) Number — it looks like a number

B) String — it has quotes around it

C) Boolean — it is either true or false

D) NaN — it cannot be used as a number

<!--
Answer: B. The quotes make it a string even though the content looks like a number.
This is directly relevant to Q11 in the assignment, where students must convert
a string to a number to do math with it.
-->

---

# Conditionals

Conditionals let your code **make decisions**.

```javascript
let temperature = 75;

if (temperature > 80) {
    console.log("It's hot!");
} else if (temperature > 60) {
    console.log("Nice weather!");
} else {
    console.log("It's cold!");
}
```

JavaScript checks conditions **top to bottom** and runs the **first** block that is `true`.

---

<!-- _class: cfu -->

# Check for Understanding

**What does this code print?**

```javascript
let score = 85;
if (score >= 90) {
    console.log("A");
} else if (score >= 80) {
    console.log("B");
} else {
    console.log("C");
}
```

**A)** `A` &nbsp;&nbsp; **B)** `B` &nbsp;&nbsp; **C)** `C` &nbsp;&nbsp; **D)** Nothing — there's an error

<!--
Answer: B.
Walk through it: 85 >= 90? No. 85 >= 80? Yes → print "B" and stop.
Emphasize that once a condition is true, the rest of the chain is skipped.
-->

---

# Functions

A function is a **reusable block of code**.

```javascript
function greet() {
    return "Welcome to Code the Dream!";
}

console.log(greet());
// "Welcome to Code the Dream!"
```

Write it once — use it as many times as you need.

---

# Functions with Parameters

Parameters let you **pass information into** a function.

```javascript
function greetStudent(name) {
    return "Hello, " + name + "!";
}

console.log(greetStudent("Maria"));   // "Hello, Maria!"
console.log(greetStudent("James"));   // "Hello, James!"
```

- `name` is the **parameter** — a placeholder inside the function
- `"Maria"` is the **argument** — the actual value passed in

<!--
A useful analogy: a parameter is a blank on a form; an argument is what you write in the blank.
Students confuse these terms often — it's fine to just use "input" informally for now.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What will this code print?**

```javascript
function double(num) {
    return num * 2;
}
console.log(double(5));
```

**A)** `5` &nbsp;&nbsp; **B)** `10` &nbsp;&nbsp; **C)** `"10"` &nbsp;&nbsp; **D)** Nothing — `return` doesn't print

<!--
Answer: B.
Common wrong answer: D. Clarify that console.log() prints the value the function returns.
If students pick D, that's a great teachable moment about return vs. console.log().
-->

---

# Naming Conventions — camelCase

JavaScript uses **camelCase** for variables and functions.

```javascript
// Descriptive and readable
let totalPrice = 29.99;
let firstName = "Maria";
function calculateSum(a, b) { return a + b; }
```

```javascript
// Hard to read
let tp = 29.99;
let fn = "Maria";
function cs(a, b) { return a + b; }
```

> Good names make your code easier to read — and easier to debug.

---

# Debugging Basics

When something goes wrong, use `console.log()` to investigate.

```javascript
let firstName = "Maria";
let lastName = "Santos";
let fullName = firstName + lastName;

console.log("Full name:", fullName);
// Output: "Full name: MariaSantos" — missing space!
```

**Common error types:** syntax, reference, type, and logical.

> Bugs are normal. Every developer debugs constantly.

<!--
The missing space is the exact bug students hit in Q13 of the assignment.
Ask: "How would you fix this?" Let students answer before moving on.
-->

---

<!-- _class: section-break -->

# Apply

<!--
Second mentor leads from here (suggested).
You'll run a live coding demo (Core Activity) followed by an optional extension.
Before this slide: open a browser console, or the class coding environment.
  Chrome/Edge: Right-click anywhere → Inspect → Console
  Firefox: Right-click anywhere → Inspect → Console
-->

---

# Core Activity: Let's Code Together

We'll build something step by step — **tell me what to type!**

Open your browser console:
- **Chrome / Edge:** Right-click → Inspect → Console
- **Firefox:** Right-click → Inspect → Console

<!--
You type; students direct you. If a student suggests something wrong, type it anyway
and let them see the result. Real debugging is more valuable than showing perfect code.
-->

---

# Step 1 — Create Variables

**Let's introduce a fictional class member.**

```javascript
let firstName = "Amara";
let lastName = "Osei";
let country = "Ghana";
```

**Ask the group:** How do we combine these into one sentence?

<!--
Take answers before moving to the next slide.
If no one answers, prompt: "We learned two ways to combine strings — what were they?"
-->

---

# Step 2 — String Concatenation

### Using `+`
```javascript
let intro = "Hi! I'm " + firstName + " " + lastName
            + " from " + country + ".";
```

### Using template literals
```javascript
let intro = `Hi! I'm ${firstName} ${lastName} from ${country}.`;
```

**Which do you find easier to read?**

---

# Step 3 — Write a Function

**Challenge:** Write a function that greets someone by name.

```javascript
function greetStudent(name) {
    return "Welcome, " + name + "!";
}

console.log(greetStudent("Amara"));
console.log(greetStudent("James"));
```

**Follow-up:** What if we want the name in all capitals?

<!--
Let the group suggest the solution before showing .toUpperCase().
This connects directly to Q14 in the assignment.
-->

---

# Step 4 — Find the Bug

**This code has a bug. Can you spot it?**

```javascript
function combineNames(first, last) {
    return first + last;
}

console.log(combineNames("Amara", "Osei"));
// Output: "AmaraOsei" — something is missing!
```

**What would you change?**

<!--
Give students a moment to look before calling on anyone.
This mirrors the exact bug pattern from Q13 in the assignment.
Celebrate any answer — even wrong guesses show real engagement.
-->

---

# Step 4 — Bug Fixed

```javascript
function combineNames(first, last) {
    return first + " " + last;
}

console.log(combineNames("Amara", "Osei"));
// Output: "Amara Osei"
```

> Adding a `" "` between variables is one of the most common fixes in JavaScript.

---

<!-- _class: section-break -->

# Extension Activity

*Only if students are ready and time allows.*

---

# Extension — Magic 8 Ball

**Build a function that returns a random response.**

```javascript
function magic8Ball() {
    let num = Math.floor(Math.random() * 3) + 1;
    if (num === 1) return "It is certain.";
    if (num === 2) return "Perhaps.";
    return "Absolutely not.";
}
console.log(magic8Ball());
```

**Try it:** Call the function 5 times. Do you get different answers?

<!--
This is Q9 from the assignment — a stretch goal for most students.
Don't feel pressure to finish if time is short.
If students seem confident, let them try writing it on their own first.
-->

---

# Assignment Preview

**15 questions** this week:

| Questions | Topic |
|-----------|-------|
| Q1–Q3 | Variables (strings, numbers, booleans) |
| Q4–Q5 | String concatenation and math |
| Q6 | String methods |
| Q7–Q9 | Conditionals |
| Q10–Q11 | Number methods and type conversion |
| Q12–Q15 | Writing functions |

Also: Create your first **GitHub repository!**

<!--
Don't walk through every question — this is just an overview.
Point students to Q12–Q15 especially: functions feel like a big jump for some.
-->

---

# Tips for the Assignment

1. **Read each question carefully** before writing any code
2. **Uncomment the `console.log()` lines** — remove the `//` to activate them
3. **Run your code often** — check output as you go, not just at the end
4. **Stuck?** Ask an AI for hints, not answers:

> "Can you give me 3 hints without showing me the solution?"

---

# Your GitHub Task This Week

Create a repository to store your code:

- [ ] GitHub → Repositories → click **New**
- [ ] Name it: `yourname-classname` (e.g. `maria-santos-jupiter`)
- [ ] Set to **Public**, check "Add a README file"
- [ ] Click **Create Repository**
- [ ] Paste the link in the "second link" field when submitting

<!--
Some students have never used GitHub. Keep this brief — they don't need to
understand git yet, just how to create a repo. The full workflow comes in Lessons 2–4.
-->

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel with variables and `console.log()`?

### Before next session:
- Complete the **lesson materials** (Odin Project or Scrimba)
- Finish the **15-question assignment**
- Create your **GitHub repository**
- Post questions in the **Slack** `#discussion` channel anytime

---

# Resources

| Resource | What it's for |
|----------|---------------|
| Odin Project Fundamentals 1–3 | Written lessons |
| Scrimba JS Deep Dive | Video lessons |
| MDN JavaScript Basics | Reference |
| W3Schools JavaScript | Quick lookups |
| Slack `#discussion` channel | Questions between sessions |

> **Next week:** Loops and Arrays!

---

<!-- _class: title -->

# Great work today!

## You've taken your first step into programming.

Questions? Reach out on Slack anytime.
