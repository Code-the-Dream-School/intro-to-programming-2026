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
  One mentor leads the Explore section (slides 3–17).
  The other leads the Apply section (slides 18–28).
  Both mentors stay on screen throughout. The second mentor can support
  questions and help students in the chat during Explore.

Speaker notes (mentor-only guidance) appear in comment blocks like this one.
In Marp presenter mode, notes display in your presenter panel.
-->

<!-- _class: title -->

# Lesson 2: JavaScript Loops and Arrays

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Explain what a loop is and write a `for` loop and a `while` loop
- Create an array and access items by index
- Use common array methods (`push`, `pop`, `includes`, `slice`)
- Loop through an array to process its items
- Describe what scope means and why it matters

---

<!-- _class: section-break -->

# Explore

<!--
First mentor leads from here through the Explore section.
Goal: build understanding before students touch the assignment.
Keep explanations short — show code, ask questions, move on.
-->

---

# Why Loops?

Imagine printing "Hello World!" 100 times.

```javascript
console.log("Hello World!");
console.log("Hello World!");
// ... 98 more lines
```

That is slow and hard to maintain. A **loop** lets us do this in 3 lines.

> Computers never get tired. Loops let us take advantage of that.

<!--
Keep this brief — the point is just to set up the "why" before showing syntax.
Ask the group: "Has anyone written repetitive code before and wished there was a better way?"
-->

---

# The `for` Loop

The most common loop in JavaScript:

```javascript
for (let i = 0; i < 5; i++) {
    console.log("Hello World!");
}
```

Three parts in the parentheses:

| Part | Code | Meaning |
|------|------|---------|
| Initialize | `let i = 0` | start here |
| Condition | `i < 5` | keep going while true |
| Update | `i++` | move to the next step |

<!--
Walk through the three parts slowly. Students often struggle most with the condition.
A helpful analogy: "i is like a counter on a scoreboard."
-->

---

# The `for` Loop — Step by Step

```javascript
for (let i = 0; i < 3; i++) {
    console.log("Count:", i);
}
// Count: 0
// Count: 1
// Count: 2
```

**Zoom chat:** Why does the output stop at 2, not 3?

<!--
Answer: when i reaches 3, the condition i < 3 becomes false and the loop stops.
Common mistake: expecting i < 3 to print 3. Walk through the check: "Is 3 < 3? No — stop."
This connects directly to Q1 (repeat) and Q2 (pyramidCounting) in the assignment.
-->

---

# The `while` Loop

Use `while` when you don't know the exact number of repetitions up front.

```javascript
let count = 0;

while (count < 3) {
    console.log("Count:", count);
    count++;
}
```

The loop keeps running **as long as** the condition is `true`.

> Forgetting `count++` causes an **infinite loop** — the tab freezes!

<!--
Warn students about infinite loops — it's the most common while-loop mistake.
Rule of thumb: "If you know exactly how many times, use for. If not, consider while."
Students can use either for the assignment — both work for Q1 and Q2.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What will this code print?**

```javascript
for (let i = 1; i <= 4; i++) {
    console.log(i);
}
```

A) `0 1 2 3`

B) `1 2 3 4`

C) `1 2 3 4 5`

D) Nothing — there is an error

<!--
Answer: B.
Key teaching point: the loop starts at 1 (not 0), and <= 4 means it includes 4.
If students pick A, they are thinking of the typical i = 0 pattern — reinforce that
the starting value is whatever we set it to.
If students pick C, they misread <= as <.
-->

---

# Arrays

An array is an **ordered list** of items.

```javascript
let fruits = ["apple", "banana", "cherry"];
```

Access items by their **index** — counting starts at **0**:

```javascript
console.log(fruits[0]);  // "apple"
console.log(fruits[1]);  // "banana"
console.log(fruits[2]);  // "cherry"
```

**Zoom chat:** What index would you use to get `"cherry"`?

<!--
"Index starts at 0" is the single biggest source of off-by-one errors.
Repeat it here, and again when you show arrays + loops.
This concept is tested directly in Q7 (getElementAt).
-->

---

# Array Properties and Methods

```javascript
let colors = ["red", "blue", "green"];

colors.length;         // 3 — how many items
colors[1] = "yellow";  // change an item
colors.push("purple"); // add to the end
colors.pop();          // remove from the end
colors.includes("red"); // true — is "red" in there?
```

> `length` is a property (no parentheses). Methods need `()`.

<!--
Students mix up properties vs. methods early on. The parentheses rule is a reliable
shortcut. Briefly demo one or two in the console if time allows.
These methods appear in Q6 (arrayChecker), Q7 (getElementAt), and Q8 (insertInArray).
-->

---

# Copying an Array with `slice()`

Assigning an array to a new variable does **not** make a copy.

```javascript
let original = [1, 2, 3];
let copy = original;        // same array, not a copy!
copy.push(4);
console.log(original);      // [1, 2, 3, 4] — changed!
```

Use `slice()` to make a true copy:

```javascript
let safeCopy = original.slice();
```

<!--
This is a genuine gotcha and is explicitly called out in Q8 and Q11 of the assignment.
The assignment comments even warn students about it. Point this out — students who skip
the instruction comments will be confused when their original array changes unexpectedly.
-->

---

# Loops + Arrays

Loops and arrays work together naturally.

```javascript
let fruits = ["apple", "banana", "cherry"];

for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
// apple
// banana
// cherry
```

> Using `fruits.length` in the condition means the loop always fits the array — even if the array grows.

<!--
The pattern "loop from 0 to array.length" is the foundation for Q10 through Q12
and Q13 in the assignment. Make sure students understand why fruits[i] gives each item.
Trace through it: when i = 0, fruits[0] = "apple"; when i = 1, fruits[1] = "banana", etc.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What does this code print?**

```javascript
let nums = [10, 20, 30];
let total = 0;

for (let i = 0; i < nums.length; i++) {
    total += nums[i];
}
console.log(total);
```

A) `[10, 20, 30]`

B) `0`

C) `60`

D) `30`

<!--
Answer: C.
Walk through it: total starts at 0. After i=0: 0+10=10. After i=1: 10+20=30. After i=2: 30+30=60.
This is exactly the pattern for Q10 (calculateTotal) in the assignment.
If students pick D, they may think total only captures the last value.
-->

---

# Scope

**Scope** controls where a variable can be used.

```javascript
let globalVar = "available everywhere";

function myFunction() {
    let localVar = "only inside here";
    console.log(globalVar);   // works
    console.log(localVar);    // works
}

console.log(globalVar);       // works
console.log(localVar);        // ERROR — not in scope
```

<!--
Keep this brief. Students will explore scope more deeply in Q15 of the assignment.
The key takeaway: a variable declared inside a function cannot be used outside it.
Block scope (let/const inside {}) is similar — covered in Q15.
-->

---

# Block Scope

Variables declared with `let` inside a block `{}` stay inside that block.

```javascript
if (true) {
    let blockVar = "I live in this block";
    console.log(blockVar);   // works
}

console.log(blockVar);       // ERROR — blockVar is gone
```

> This is why `let` is safer than `var` — `var` leaks outside blocks.

<!--
Q15 in the assignment asks students to demonstrate all three scope types: global,
function, and block. This slide gives them enough context to approach that question.
Don't go deep on var vs. let here — just mention that let is the modern standard.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**Which line will cause an error?**

```javascript
function greet() {
    let message = "Hello!";
    console.log(message);    // Line A
}
greet();
console.log(message);        // Line B
```

A) Line A — `message` doesn't exist yet

B) Line B — `message` is out of scope

C) Both lines — `let` cannot be used inside functions

D) Neither — both lines work fine

<!--
Answer: B.
Line A is inside the function where message was declared — it works fine.
Line B is outside the function — message is out of scope and throws a ReferenceError.
This directly mirrors what students need to do in Q15 of the assignment, which asks
them to write commented-out lines that would error if uncommented.
-->

---

<!-- _class: section-break -->

# Apply

<!--
Second mentor leads from here (suggested).
You'll run a live coding demo (Core Activity) followed by an optional Extension Activity.
Before this slide: open a browser console or the class coding environment.
  Chrome/Edge: Right-click anywhere → Inspect → Console
  Firefox: Right-click anywhere → Inspect → Console
Goal: students watch you build functions similar to the assignment, then try on their own.
-->

---

# Core Activity: Let's Code Together

We will build functions similar to the assignment — **you tell me what to type!**

Open your browser console:
- **Chrome / Edge:** Right-click anywhere → Inspect → Console
- **Firefox:** Right-click anywhere → Inspect → Console

<!--
You type, students direct. If a student suggests something that doesn't work, type it
anyway and debug together. Real debugging in front of students is more valuable than
showing perfect code from the start.
Plan to build three things: a loop function, an array loop, and a filter function.
These mirror Q1, Q10, and Q11 in the assignment.
-->

---

# Step 1 — Repeat with a Loop

**Challenge:** Write a function that prints "Hello World!" a given number of times.

```javascript
function repeat(times) {
    for (let i = 0; i < times; i++) {
        console.log("Hello World!");
    }
}

repeat(3);
```

**Ask the group:** Why is the `console.log` inside the function here instead of outside?

<!--
This is Q1 in the assignment. The question's instructions specifically note that
students should call the function directly rather than wrapping it in console.log,
because the logging happens inside the function.
If time allows, ask: "How would we change this to say something other than 'Hello World!'?"
-->

---

# Step 2 — Sum an Array

**Challenge:** Write a function that adds up all numbers in an array.

```javascript
function calculateTotal(numbers) {
    let sum = 0;
    for (let i = 0; i < numbers.length; i++) {
        sum += numbers[i];
    }
    return sum;
}

console.log("Q10:", calculateTotal([3, 4, 2, 8]));
// Q10: 17
```

**Ask:** What does `sum += numbers[i]` do on each step of the loop?

<!--
This is Q10 in the assignment. Walk through it step by step if students look uncertain:
i=0: sum = 0+3 = 3. i=1: sum = 3+4 = 7. i=2: sum = 7+2 = 9. i=3: sum = 9+8 = 17.
The "Q10:" label in console.log mirrors exactly how the assignment expects output.
-->

---

# Step 3 — Filter an Array

**Challenge:** Write a function that returns only the even numbers from an array.

```javascript
function findEvens(numbers) {
    let evens = [];
    for (let i = 0; i < numbers.length; i++) {
        if (numbers[i] % 2 === 0) {
            evens.push(numbers[i]);
        }
    }
    return evens;
}

console.log(findEvens([10, 3, 7, 6, 2]));
// [10, 6, 2]
```

**Zoom chat:** What does `%` (modulo) do?

<!--
This is Q11 (findEvens) in the assignment. Students also need findOdds — ask them
how they would change this function to find odds instead (numbers[i] % 2 !== 0).
Modulo is also used in Q5 (numOfOdds) and Q14 (FizzBuzz), so it's worth a moment here.
-->

---

# Step 4 — Try It Yourself

**Pick one to try on your own (5 minutes):**

**A)** Write a function called `pyramidCounting` that takes a number and returns the sum of all numbers from 0 up to that number. `pyramidCounting(4)` should return `10`.

**B)** Write a function called `displaySkills` that takes an array of strings and prints each one. Test it with `["JavaScript", "HTML", "CSS"]`.

**C)** Write a function called `makeSquares` that takes an array of numbers and returns a new array with each number squared. `makeSquares([2, 5, 8])` should return `[4, 25, 64]`.

<!--
A = Q2, B = Q13, C = Q12 in the assignment.
Give students 5 minutes. Circulate and help. Ask for a volunteer to share at the end.
If no one volunteers, walk through one together.
-->

---

<!-- _class: section-break -->

# Extension Activity

*Only if students are ready and time allows.*

<!--
This is optional. Skip it if the group is still working through the core activity
or if questions are running long. Do not rush the core content to fit this in.
-->

---

# Extension — FizzBuzz

A classic interview challenge! Loop from 1 to 15 and build an array:

```javascript
function fizzBuzz() {
    let result = [];
    for (let i = 1; i <= 15; i++) {
        if (i % 3 === 0 && i % 5 === 0) {
            result.push("fizzbuzz");
        } else if (i % 3 === 0) {
            result.push("fizz");
        } else if (i % 5 === 0) {
            result.push("buzz");
        } else {
            result.push(i);
        }
    }
    return result;
}
```

**Ask:** Why must we check "divisible by both" first?

<!--
This is Q14 in the assignment. The order of conditions is the key insight:
if you check % 3 first and it's true, you never get to check both.
Let students explain the answer before showing or confirming it.
Expected output: [1, 2, "fizz", 4, "buzz", "fizz", 7, 8, "fizz", "buzz", 11, "fizz", 13, 14, "fizzbuzz"]
-->

---

# Assignment Preview

**15 questions** this week, grouped by topic:

| Questions | Topic |
|-----------|-------|
| Q1–Q5 | Loop-based functions (repeat, sum, vowels, odds) |
| Q6–Q9 | Array operations (check, access, insert, compare) |
| Q10–Q12 | Arrays + loops (sum, filter, square) |
| Q13 | Display skills from an array |
| Q14 | FizzBuzz |
| Q15 | Scope demonstration |

Also this week: **clone your GitHub repo** to your local machine.

<!--
Don't walk through every question — just give students the map.
Point out that Q1–Q5 build directly on what we just coded together.
Mention that Q14 (FizzBuzz) is a famous interview question — it's worth the extra effort.
-->

---

# Tips for the Assignment

1. **Read the comment above each question** before writing any code
2. **Use `console.log()` often** — check output as you go, not just at the end
3. **For Q8, Q11, Q12:** use `.slice()` to copy arrays before modifying them
4. **For Q14 (FizzBuzz):** check divisible-by-both first — order matters!
5. **Stuck?** Ask an AI for hints, not answers:

> "Can you give me 3 hints for this problem without showing me the solution?"

<!--
Tip 3 is specific to a very common mistake. Students who skip the assignment comments
on Q8 and Q11 often modify the original array by accident and can't figure out why.
Tip 4 is the key insight for FizzBuzz — the assignment will pass even with the wrong
order in some cases, but the output will be wrong (15 becomes "fizz" instead of "fizzbuzz").
-->

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel with loops and arrays?

### Before next session:
- Read through the **lesson materials** (loops, arrays, scope, Git)
- Complete the **15-question assignment**
- **Clone** your GitHub repo to your local machine (lesson video walks you through it)
- Post questions in **Slack** anytime — we are here to help!

<!--
If many students rate 1–2, note which topics to revisit at the start of next session.
Reinforce that cloning the repo is not optional — they need local files to submit work
starting this week.
-->

---

# Resources

| Resource | What it's for |
|----------|---------------|
| MDN — [Looping Code](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code) | Loops reference + active learning |
| JavaScript.info — [While and For](https://javascript.info/while-for) | Loop practice with tasks |
| W3Schools — [Arrays](https://www.w3schools.com/js/js_arrays.asp) | Array basics |
| W3Schools — [Array Methods](https://www.w3schools.com/js/js_array_methods.asp) | push, pop, slice, and more |
| W3Schools — [Scope](https://www.w3schools.com/js/js_scope.asp) | Scope explained simply |
| Slack `#discussion` channel | Questions between sessions |

> **Next week:** JavaScript Objects!

---

<!-- _class: title -->

# Great work today!

## Loops and arrays unlock a whole new level of programming.

Questions? Reach out on Slack anytime.
