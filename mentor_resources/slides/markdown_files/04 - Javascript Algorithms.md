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
  One mentor leads the Explore section (slides 3–15).
  The other leads the Apply section (slides 16–26).
  Both mentors stay on screen throughout. The second mentor can support questions during Explore.

Speaker notes appear in comment blocks on each slide.
In Marp presenter mode, notes display in your presenter panel.
-->

<!-- _class: title -->

# Lesson 4: JavaScript Algorithms

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Define an algorithm and give a real-world example
- Write pseudocode before writing real code
- Solve problems by breaking them into smaller functions
- Pass a function as a callback to another function
- Create and submit a pull request on GitHub

<!--
Welcome students. Let them know there are two big themes today:
problem-solving strategy (algorithms and pseudocode) and a new code pattern (callbacks).
The Git section covers pull requests — students will submit one this week.
-->

---

<!-- _class: section-break -->

# Explore

---

# What Is an Algorithm?

An **algorithm** is a set of steps you write to solve a problem.

You already follow algorithms every day:

- Following a recipe
- Using GPS navigation
- Withdrawing cash from an ATM

> In programming, the computer follows your steps exactly — every step must be spelled out.

<!--
Ask students: "Can you think of another everyday algorithm?"
Take 2–3 answers. Emphasize that computers can't guess or assume — every detail matters.
-->

---

# Algorithms Need Every Step

**Making tea — as an algorithm:**

1. Check that you have tea, water, a cup, and a kettle
2. If anything is missing — stop
3. Fill the kettle and heat the water
4. Place tea in the cup
5. Pour hot water into the cup
6. Wait 3–5 minutes
7. Remove the tea bag
8. Serve

> Skip a step and the result is wrong. Computers work the same way.

<!--
Point out that "pour hot water" assumes the water is already hot — because step 3 handled it first.
Order matters. This is the key insight before introducing pseudocode.
-->

---

# Pseudocode: Plan Before You Code

**Pseudocode** is writing your steps in plain language before writing real code.

It helps you think clearly — even experienced developers do this.

```
function tipCalculator(billTotal, tipPercentage)
  // Check that the inputs are valid
  // Multiply billTotal by tipPercentage to get the tip
  // Add the tip to billTotal to get the final amount
  // Return the final amount
```

> Once you write the real code, pseudocode becomes your comments.

<!--
Read the pseudocode out loud together. Ask: "Does this make sense without any JavaScript?"
Reinforce: planning in plain language before touching syntax reduces errors and frustration.
-->

---

# Pseudocode Becomes Real Code

```javascript
function tipCalculator(billTotal, tipPercentage) {
  // Multiply billTotal by tipPercentage to get the tip
  let tip = billTotal * tipPercentage;
  // Add the tip to billTotal to get the final amount
  let total = billTotal + tip;
  // Return the final amount
  return total;
}

console.log(tipCalculator(50, 0.2));  // 60
```

> The comments stayed — they explain the code to anyone who reads it later.

<!--
This is Q3 in the assignment. Walk through each line slowly.
Ask: "What would happen if we forgot to return total?"
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What is the main purpose of pseudocode?**

A) To run your program faster

B) To plan your steps in plain language before writing code

C) To replace `console.log()` in your program

D) To make your code look professional

<!--
Answer: B.
Teaching note: pseudocode never runs — it is purely for thinking and planning.
If students pick D, point out that well-named functions and comments do that job.
-->

---

# Breaking a Big Problem into Small Functions

Some problems have many steps. The trick: **one function per step**.

```javascript
function calculateAverage(scores) { /* step 1 */ }
function getLetterGrade(average) { /* step 2 */ }
function passed(letterGrade)     { /* step 3 */ }
```

Then combine them in one final function:

```javascript
function printClassResult(className, student, scores) {
  let avg   = calculateAverage(scores);
  let grade = getLetterGrade(avg);
  let didPass = passed(grade);
  // ...
}
```

<!--
This is Q8–Q11 in the assignment. Students often try to put everything in one function.
Show them how each small function is easy to test individually.
Say: "If calculateAverage is wrong, you fix only that function — not the whole thing."
-->

---

# What Is a Callback?

A **callback** is a function that you pass to another function.

```javascript
function buttonPushed() {
  console.log("The button was pushed!");
}

function simulateButtonPush(callback) {
  callback();
}

simulateButtonPush(buttonPushed);
// "The button was pushed!"
```

> We pass `buttonPushed` without parentheses — we are passing the function itself, not calling it.

<!--
This is Q12–Q13 in the assignment — the simplest possible callback example.
The key point: no parentheses when passing a function as an argument.
Write buttonPushed() vs buttonPushed on the board or in the console to show the difference.
-->

---

# Why Use Callbacks?

Without callbacks — a separate function for every action:

```javascript
function printDouble(num) { console.log(num * 2); }
function printTriple(num) { console.log(num * 3); }
```

With a callback — one flexible function:

```javascript
function processNumber(num, action) {
  action(num);
}

processNumber(5, (n) => console.log(n * 2));  // 10
processNumber(5, (n) => console.log(n * 3));  // 15
```

> Callbacks make functions **flexible and reusable**.

<!--
Don't dwell too long on arrow functions if students aren't familiar with them yet.
The takeaway is the concept: passing behavior as a parameter.
You can use regular function syntax if it is clearer for your group.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What does this code print?**

```javascript
function sayHi() {
  console.log("Hi there!");
}
function run(fn) {
  fn();
}
run(sayHi);
```

A) Nothing — `sayHi` was never called

B) An error — you cannot pass a function as an argument

C) `"Hi there!"`

D) `fn`

<!--
Answer: C.
Common wrong answer: A — students think sayHi was only passed, not called.
Walk through it: run receives sayHi, then calls it with fn().
Emphasize: fn() inside run IS calling sayHi.
-->

---

# Git This Week: Pull Requests

A **pull request (PR)** asks to merge your branch into `main`.

This is how real development teams review code:

1. Push your branch to GitHub
2. Open a pull request
3. A reviewer looks at your changes
4. The code gets merged

> You will create and submit your first PR this week.

<!--
Keep this brief. Students will follow step-by-step instructions in the lesson materials.
The key concept: a PR is a formal way to say "my work is ready — please review it."
-->

---

<!-- _class: cfu -->

# Check for Understanding

**You finished your work on `lesson-4` branch. What is the correct order of steps?**

A) Merge → Push → Commit → PR

B) Commit → Push → Open a PR → Merge after review

C) Push → Commit → Merge → PR

D) PR → Push → Commit → Merge

<!--
Answer: B.
Walk through each step: commit saves locally, push sends to GitHub, PR opens the review, merge combines.
Students often confuse the order of commit and push — or try to open a PR before pushing.
-->

---

<!-- _class: section-break -->

# Apply

<!--
Second mentor leads from here (suggested).
Open a browser console or the class coding environment before this slide.
  Chrome/Edge: Right-click anywhere → Inspect → Console
  Firefox: Right-click anywhere → Inspect → Console
You'll live-code the Core Activity with students directing you.
-->

---

# Core Activity: Let's Code Together

**We'll build something step by step — you tell me what to type.**

Open your browser console:
- **Chrome / Edge:** Right-click anywhere → Inspect → Console
- **Firefox:** Right-click anywhere → Inspect → Console

Or use [replit.com](https://replit.com) if you prefer.

<!--
You type; students direct you. If a student suggests wrong code, type it anyway.
Seeing an error and fixing it together is more valuable than showing perfect code.
Start by asking: "What are the steps — in plain English — before we write anything?"
-->

---

# Step 1 — Plan First: Temperature Converter

**Goal:** Convert a temperature from Celsius to Fahrenheit.

**Ask the group:** What are the steps in plain English?

```
// Take a celsius temperature as input
// Multiply by 9/5
// Add 32
// Return the result
```

**Formula:** `F = C × 9/5 + 32`

<!--
Don't show the formula until students have had a chance to think about it.
Ask: "Has anyone converted temperatures before? What is 0°C in Fahrenheit?"
This is Q1 in the assignment.
-->

---

# Step 2 — Code It

```javascript
function convertTemp(celsius) {
  let fahrenheit = celsius * 9 / 5 + 32;
  return fahrenheit;
}

console.log("0°C:", convertTemp(0));    // 32
console.log("100°C:", convertTemp(100)); // 212
console.log("37°C:", convertTemp(37));   // 98.6
```

**Ask the group:** What is 37°C in real life?

<!--
98.6°F — normal body temperature. Students enjoy recognizing this.
Ask: "What happens if we pass a string instead of a number?" Type convertTemp("hot") to show NaN.
-->

---

# Step 3 — Plan: Reverse a String

**Goal:** Return a string with its characters in reverse order.

**Ask the group:** What are the steps?

```
// Start with an empty result string
// Loop through the input string from the last character to the first
// Add each character to the result
// Return the result
```

> This is Q2 in the assignment. Try writing the pseudocode before the code.

<!--
Let students talk through the loop direction before showing any code.
Key question: "If the string has 5 characters, what index is the last one?"
-->

---

# Step 4 — Code It

```javascript
function reverseString(str) {
  let result = "";
  for (let i = str.length - 1; i >= 0; i--) {
    result += str[i];
  }
  return result;
}

console.log(reverseString("hello"));  // "olleh"
console.log(reverseString(""));       // ""
```

**Ask the group:** Why do we start at `str.length - 1`?

<!--
Answer: string indexes start at 0, so the last index is length - 1.
Also test an empty string — the loop never runs and result stays "".
Ask: "Why is it important that an empty string doesn't crash our code?"
-->

---

# Step 5 — Grade Calculator Preview

**Q8–Q11 build three small functions that work together.**

```javascript
// Q8: Average of an array of scores
function calculateAverage(scores) { /* ... */ }

// Q9: Letter grade from a number average
function getLetterGrade(average) { /* ... */ }

// Q10: true if passing, false otherwise
function passed(letterGrade) { /* ... */ }
```

**Demo:** What does `getLetterGrade(75)` return?

<!--
You don't need to live-code the full solution — show the structure and one example.
Ask: "If calculateAverage returns 75, what letter grade should getLetterGrade return?"
This prepares students for Q11: printClassResult, which calls all three.
-->

---

<!-- _class: section-break -->

# Extension Activity

*Only if students are ready and time allows.*

---

# Extension — isPrime

**Challenge:** Write a function that returns `true` if a number is prime.

A prime number is only divisible by 1 and itself (e.g., 2, 3, 5, 7, 11).

```javascript
function isPrime(num) {
  if (num < 2) return false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}
```

**Try it:** `isPrime(7)`, `isPrime(12)`, `isPrime(1)`, `isPrime(0)`

<!--
This is Q6 in the assignment — one of the harder questions.
The key hint: you only need to check divisors up to the square root of the number.
If students are confused, ask: "What does the % operator give us?"
Q7 builds on this: getPrimesUpTo uses isPrime inside a loop.
-->

---

# Assignment Preview

**13 questions** this week — from simple functions to a full grade calculator:

| Questions | Topic |
|-----------|-------|
| Q1–Q5 | Algorithm functions (temp, reverse, tip, multiply, average) |
| Q6–Q7 | Prime numbers (`isPrime`, `getPrimesUpTo`) |
| Q8–Q11 | Grade calculator (four functions that work together) |
| Q12–Q13 | Callbacks (`buttonPushed`, `simulateButtonPush`) |

Also: **Create and submit your first pull request.**

<!--
Don't walk through every question. Highlight the grade calculator (Q8–Q11) as the biggest challenge.
Remind students to write pseudocode before each function — it saves time.
-->

---

# Tips for the Assignment

1. **Write pseudocode first** — plan your steps before writing JavaScript
2. **Test each function on its own** — don't wait until Q11 to run anything
3. **Watch out for edge cases** — empty arrays, 0, and 1 are common traps
4. **For Q6–Q7**, check that `isPrime(0)` and `isPrime(1)` both return `false`
5. **Stuck?** Ask an AI for hints, not answers:

> "Give me 3 hints for this problem without showing me the solution."

<!--
Edge cases that trip students up:
  - calculateAverage with an empty array → dividing by zero
  - isPrime with 0 or 1 → should return false
  - reverseString with an empty string → should return "" without crashing
-->

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel breaking a problem into smaller functions?

### Before next session:
- Work through the **lesson materials** (algorithms, pseudocode, callbacks, pull requests)
- Complete the **13-question assignment**
- **Create and submit** your first pull request on GitHub
- Post questions in the **Slack** `#discussion` channel anytime

<!--
End with energy. Acknowledge that this lesson introduced a lot of new ideas.
Remind students that writing small functions and planning with pseudocode are skills
that professional developers use every single day.
-->

---

# Resources

| Resource | What it's for |
|----------|---------------|
| [Algorithms in Everyday Life](https://www.learning.com/blog/7-examples-of-algorithms-in-everyday-life-for-students/) | Real-world algorithm examples |
| [W3Schools: Callbacks](https://www.w3schools.com/js/js_callback.asp) | Callback reference and examples |
| [GitHub Docs: About Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) | PR documentation |
| [List of Prime Numbers — Wikipedia](https://en.wikipedia.org/wiki/List_of_prime_numbers) | Useful for testing Q6–Q7 |
| Slack `#discussion` channel | Questions between sessions |

> **Next week:** HTML Basics — time to build web pages!

---

<!-- _class: title -->

# Great work today!

## You've leveled up your problem-solving skills.

Questions? Reach out on Slack anytime.
