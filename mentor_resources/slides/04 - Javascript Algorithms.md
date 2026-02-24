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
3. Command Palette > "Marp: Open Preview to the Side"
4. Export as PDF/PPTX: Command Palette > "Marp: Export Slide Deck"

IN THE BROWSER:
1. Go to https://web.marp.app/
2. Paste or upload this file
3. Present directly or export

Speaker notes are inside HTML comments — invisible during presentation.
-->

<!-- _class: title-slide -->

# Lesson 4: JavaScript Algorithms

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

How would you explain — step by step — how to make a peanut butter and jelly sandwich to someone who has never made one?

<!--
This is a direct lead-in to algorithms. Students often forget steps
like "open the jar" or "pick up the knife." That's the point —
computers need every single step spelled out!
-->

---

# What You'll Learn This Week

- **Algorithms** — step-by-step problem solving
- **Pseudocode** — planning in plain language before coding
- **Callbacks** — passing functions to other functions
- **Git: Pull Requests** — submitting your work for review

---

# I Do: What Is an Algorithm?

An algorithm is just a **set of steps** to solve a problem.

You already use them every day:
- Following a recipe
- Using GPS navigation
- Withdrawing cash from an ATM

> In programming, we write algorithms as code.

---

# I Do: Algorithms in Everyday Life

**Making a PB&J sandwich:**
1. Check if you have bread, peanut butter, and jelly
2. If anything is missing — stop!
3. Take out two slices of bread
4. Spread peanut butter on one slice
5. Spread jelly on the other
6. Put the slices together
7. Serve

**Notice:** the order matters, and every step is explicit.

---

# I Do: Pseudocode

Pseudocode = writing your plan in **plain language** before coding.

**Example: Tip calculator**

```
function tipCalculator(billTotal, tipPercentage)
  // Check the parameters are valid
  // Multiply bill by tip percentage to get the tip
  // Add the tip to the bill total
  // Return the final amount
```

> Pseudocode becomes your comments once you write the real code!

---

# I Do: Pseudocode → Real Code

```javascript
function tipCalculator(billTotal, tipPercentage) {
    // Multiply bill by tip percentage to get the tip
    let tip = billTotal * tipPercentage;
    // Add the tip to the bill total
    let total = billTotal + tip;
    // Return the final amount
    return total;
}

console.log(tipCalculator(50, 0.2));  // 60
```

---

# I Do: Callbacks

A callback is a **function you pass to another function**.

```javascript
function processNumber(num, action) {
    action(num);
}

processNumber(5, function(n) {
    console.log(n * 2);
});
// Output: 10
```

The function `action` is the callback — we decide **later** what it does.

---

# I Do: Why Callbacks?

Without callbacks — a separate function for everything:
```javascript
function printDouble(num) { console.log(num * 2); }
function printTriple(num) { console.log(num * 3); }
function printSquare(num) { console.log(num * num); }
```

With callbacks — one flexible function:
```javascript
function processNumber(num, action) {
    action(num);
}
processNumber(5, (n) => console.log(n * 2));
processNumber(5, (n) => console.log(n * n));
```

> Callbacks make code **flexible and reusable**.

---

# I Do: Building Functions on Functions

This week you'll build functions that **use other functions**:

```javascript
function calculateAverage(scores) { /* ... */ }
function getLetterGrade(average) { /* ... */ }
function passed(letterGrade) { /* ... */ }
```

Then combine them:
```javascript
function printClassResult(className, student, scores) {
    let avg = calculateAverage(scores);
    let grade = getLetterGrade(avg);
    let didPass = passed(grade);
    // ...
}
```

> Breaking problems into small functions = divide and conquer!

---

<!--
Transition to We Do:
- Ask: "What questions do you have so far?"
- Emphasize that the hard part isn't coding — it's planning the steps.
-->

# We Do: Let's Code Together! (15-20 min)

Open your browser console or [replit.com](https://replit.com).

**Let's plan first, then code!**

---

# We Do: Temperature Converter

**Challenge:** Convert Celsius to Fahrenheit.

**Ask the group:** What's the formula?

> Formula: `F = C × 9/5 + 32`

Let's write pseudocode first:
```
// Take a celsius temperature
// Multiply by 9/5
// Add 32
// Return the result
```

---

# We Do: Temperature Converter

```javascript
function convertTemp(celsius) {
    let fahrenheit = celsius * 9 / 5 + 32;
    return fahrenheit;
}

console.log(convertTemp(0));    // 32
console.log(convertTemp(100));  // 212
console.log(convertTemp(37));   // 98.6
```

**Follow-up:** What everyday temperatures can we test?

---

# We Do: Reverse a String

**Challenge:** Reverse the characters in a string.

**Let's plan it out together.** What steps do we need?

1. Start with an empty result string
2. Loop through the original string **backward**
3. Add each character to the result
4. Return the result

---

# We Do: Reverse a String

```javascript
function reverseString(str) {
    let result = "";

    for (let i = str.length - 1; i >= 0; i--) {
        result += str[i];
    }
    return result;
}

console.log(reverseString("hello"));  // "olleh"
console.log(reverseString("Code"));   // "edoC"
```

**Zoom chat:** Why do we start at `str.length - 1`?

---

# We Do: Using a Callback

**Challenge:** Simulate pushing a button with a callback.

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

**Ask the group:** What is `callback` in this example?

<!--
Emphasize that we pass buttonPushed WITHOUT parentheses — we're
passing the function itself, not calling it.
-->

---

<!--
Transition to You Do:
Set a timer for 5-10 minutes. Encourage pseudocode first.
-->

# You Do: Independent Practice (5-10 min)

Pick **one** to try on your own:

**A)** Write a function `multiplyThese` that takes two numbers and returns their product.

**B)** Write a function `getAverage` that takes two numbers and returns their average.

**C)** Write pseudocode for a function that checks if a number is prime. (You don't have to code it — just plan the steps!)

---

# You Do: Share Out

**Who wants to share?**

- Did you write pseudocode first?
- How did planning help (or not)?

---

# Assignment Preview

This week's assignment has **13 questions**:

- **Q1-Q5:** Algorithm functions (temperature, reverse string, tip calculator, multiply, average)
- **Q6-Q7:** Prime numbers (`isPrime`, `getPrimesUpTo`)
- **Q8-Q11:** Grade calculator (building functions on functions!)
- **Q12-Q13:** Callbacks

---

# Assignment Highlight: Grade Calculator

You'll build **three small functions** that work together:

1. `calculateAverage(scores)` — average of an array
2. `getLetterGrade(average)` — A, B, C, D, or F
3. `passed(letterGrade)` — true or false

Then combine them in `printClassResult`.

> This is divide and conquer in action!

---

# Git This Week: Pull Requests

A **pull request** (PR) asks to merge your branch into `main`.

This is how real development teams review code:
1. You push your branch to GitHub
2. You open a PR
3. A reviewer looks at your changes
4. The code gets merged

> The lesson video walks through creating your first PR!

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel breaking a problem into steps?

### Before next session:
- Work through the **lesson materials** (algorithms, pseudocode, callbacks)
- Complete the **coding assignment** (13 questions)
- **Create and submit** your first pull request
- Reach out on **Slack** if you get stuck!

---

# Resources

- **Lesson:** [Algorithms in Everyday Life](https://www.learning.com/blog/7-examples-of-algorithms-in-everyday-life-for-students/)
- **W3Schools:** [Callbacks](https://www.w3schools.com/js/js_callback.asp)
- **GitHub Docs:** [About Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

> **Next week:** HTML Basics — time to build web pages!

---

<!-- _class: title-slide -->

# Great work this week!

## You've completed the JavaScript foundations.

Questions? Reach out on Slack anytime.
