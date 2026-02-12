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

# Lesson 2: Loops and Arrays

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

**Share in the Zoom chat:**

What's one thing from last week's lesson that "clicked" for you?

Or: What's something you're still thinking about?

<!--
This is a good temperature check on how the first week went.
If many students mention struggling with functions, you may want
to do a quick review before diving into new content.
-->

---

# What You'll Learn This Week

- **Loops** — making the computer repeat tasks
- **Arrays** — storing collections of data
- **Scope** — where variables are accessible
- **Git basics** — cloning a repository

---

# I Do: Why Loops?

Imagine printing "Hello World!" 100 times.

Without a loop:
```javascript
console.log("Hello World!");
console.log("Hello World!");
console.log("Hello World!");
// ... 97 more times 😩
```

Computers are great at repetition. Loops let us harness that.

---

# I Do: The `for` Loop

The most common loop in JavaScript:

```javascript
for (let i = 0; i < 5; i++) {
    console.log("Count:", i);
}
```

Three parts:
- **Initialize:** `let i = 0` — starting point
- **Condition:** `i < 5` — keep going?
- **Update:** `i++` — move forward

---

# I Do: The `for` Loop — What Happens?

```javascript
for (let i = 0; i < 5; i++) {
    console.log("Count:", i);
}
```

Output:
```
Count: 0
Count: 1
Count: 2
Count: 3
Count: 4
```

**Zoom chat:** Why does it stop at 4, not 5?

---

# I Do: The `while` Loop

Use `while` when you don't know how many times to loop:

```javascript
let count = 0;

while (count < 3) {
    console.log("Count:", count);
    count++;
}
```

The loop keeps running **as long as** the condition is `true`.

> Careful: forgetting `count++` creates an infinite loop!

---

# I Do: Arrays

An array is an **ordered list** of items.

```javascript
let fruits = ["apple", "banana", "cherry"];
```

Access items by their **index** (starting at 0):

```javascript
console.log(fruits[0]);  // "apple"
console.log(fruits[1]);  // "banana"
console.log(fruits[2]);  // "cherry"
```

---

# I Do: Array Basics

```javascript
let fruits = ["apple", "banana", "cherry"];
```

**Length:** how many items?
```javascript
console.log(fruits.length);  // 3
```

**Change** an item:
```javascript
fruits[1] = "mango";
// ["apple", "mango", "cherry"]
```

---

# I Do: Useful Array Methods

```javascript
let colors = ["red", "blue"];
```

**Add** to the end:
```javascript
colors.push("green");
// ["red", "blue", "green"]
```

**Remove** from the end:
```javascript
colors.pop();
// ["red", "blue"]
```

**Check** if something exists:
```javascript
colors.includes("red");  // true
```

---

# I Do: Loops + Arrays

Loops and arrays are a natural pair:

```javascript
let fruits = ["apple", "banana", "cherry"];

for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```

Output:
```
apple
banana
cherry
```

---

# I Do: Scope (Quick Intro)

**Scope** = where a variable is accessible.

```javascript
let globalVar = "I'm everywhere!";

function myFunction() {
    let functionVar = "I'm only in here";
    console.log(globalVar);    // ✅ works
    console.log(functionVar);  // ✅ works
}

console.log(globalVar);    // ✅ works
console.log(functionVar);  // ❌ error!
```

Variables declared inside a function **stay** inside that function.

---

<!--
Transition to We Do:
- Ask: "What questions do you have so far?"
- Remind students they'll get more practice with the assignment.
-->

# We Do: Let's Code Together! (15-20 min)

Open your browser console or [replit.com](https://replit.com).

**I'll type, you tell me what to write!**

---

# We Do: Build a Loop

**Challenge:** Print the numbers 1 through 5.

**Ask the group:** What are the three parts of our `for` loop?

```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

**Follow-up:** How would we change this to count from 1 to 100?

---

# We Do: Loop Through a String

**Challenge:** Count the vowels in a word.

Let's plan first (pseudocode!):
1. Start with a counter at 0
2. Loop through each character
3. If it's a vowel, add 1 to the counter
4. Return the counter

---

# We Do: Loop Through a String

```javascript
function vowelCount(str) {
    let count = 0;
    let vowels = "aeiouAEIOU";

    for (let i = 0; i < str.length; i++) {
        if (vowels.includes(str[i])) {
            count++;
        }
    }
    return count;
}

console.log(vowelCount("hello"));  // 2
```

<!--
Walk through this step by step. Ask students to predict
the output before running it. Try different strings.
-->

---

# We Do: Working with Arrays

**Challenge:** Write a function that adds up all numbers in an array.

```javascript
function calculateTotal(numbers) {
    let sum = 0;

    for (let i = 0; i < numbers.length; i++) {
        sum += numbers[i];
    }
    return sum;
}

console.log(calculateTotal([3, 4, 2, 8]));  // 17
```

**Ask the group:** What does `sum += numbers[i]` do?

---

# We Do: Filtering an Array

**Challenge:** Get only the even numbers from an array.

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

console.log(findEvens([10, 3, 7, 6, 19, 2]));
```

**Zoom chat:** What do you think `%` (modulo) does?

---

<!--
Transition to You Do:
Set a timer for 5-10 minutes. Let students pick their challenge.
Circulate and help as needed.
-->

# You Do: Independent Practice (5-10 min)

Pick **one** to try on your own:

**A)** Write a loop that prints every even number from 0 to 20.

**B)** Create an array of 5 of your favorite foods. Use a loop to print each one.

**C)** Write a function called `repeat` that takes a number and prints "Hello World!" that many times.

---

# You Do: Share Out

**Who wants to share what they tried?**

- What approach did you take?
- Did anything surprise you?

---

# Assignment Preview

This week's assignment has **15 questions**:

- **Q1-Q5:** Loop-based functions (repeat, sum, vowels, odds)
- **Q6-Q9:** Array operations (check empty, get element, insert, compare)
- **Q10-Q12:** Arrays + loops (sum, filter evens/odds, squares)
- **Q13:** Display skills from an array
- **Q14:** FizzBuzz!
- **Q15:** Scope demonstration

---

# Assignment Preview: FizzBuzz (Q14)

A classic coding challenge! Loop 1 to 15:
- Divisible by 3 → "fizz"
- Divisible by 5 → "buzz"
- Divisible by both → "fizzbuzz"
- Otherwise → the number

> Hint: check "both" **first** — why does order matter?

---

# Git This Week: Cloning a Repo

You'll also **clone** your GitHub repository to your computer.

This copies your remote repo to your local machine so you can work on files locally.

```
git clone git@github.com:yourUsername/repo-name.git
```

> The lesson video walks you through every step!

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel with loops?

### Before next session:
- Work through the **lesson materials** (loops, arrays, scope)
- Complete the **coding assignment** (15 questions)
- **Clone** your GitHub repo to your local machine
- Reach out on **Slack** if you get stuck!

---

# Resources

- **MDN:** [Looping Code](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code)
- **W3Schools:** [Arrays](https://www.w3schools.com/js/js_arrays.asp) | [Array Methods](https://www.w3schools.com/js/js_array_methods.asp)
- **JavaScript.info:** [While and For](https://javascript.info/while-for)

> **Next week:** JavaScript Objects!

---

<!-- _class: title-slide -->

# Great work this week!

## Loops and arrays unlock a whole new level of programming.

Questions? Reach out on Slack anytime.
