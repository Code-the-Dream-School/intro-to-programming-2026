---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 4: JavaScript Algorithms"
---

# Lesson 4: JavaScript Algorithms

**Mentor Session Slide Deck**

Topics: Algorithms, Pseudocode, Problem-Solving Strategies, Callbacks

---

# What is an Algorithm?

An algorithm is a **set of step-by-step instructions** to solve a problem.

You follow algorithms every day:
- **Getting ready in the morning**: wake up → brush teeth → get dressed → eat breakfast
- **Checking out at a store**: scan items → calculate total → accept payment → give receipt

Programming is writing algorithms in a language a computer understands.

---

# Pseudocode: Plan Before You Code

Write the **steps in plain English** before writing JavaScript:

**Problem**: Calculate the final price after applying a discount.

```
// 1. Take the original price and discount percentage as inputs
// 2. Calculate the discount amount (price × percentage)
// 3. Subtract the discount from the original price
// 4. Return the final price
```

Then translate to code:

```javascript
function applyDiscount(price, discountPercent) {
    let discountAmount = price * discountPercent;
    let finalPrice = price - discountAmount;
    return finalPrice;
}
```

---

# Why Pseudocode Matters

Without planning:
- You stare at a blank screen
- You write code, hit errors, delete, start over
- You lose track of what you're trying to do

With pseudocode:
- You **understand the problem** first
- Each step becomes a **line of code**
- Your pseudocode becomes your **comments**

---

# Walkthrough: Counting Characters

**Problem**: Count how many times a specific letter appears in a word.

```javascript
// Pseudocode:
// 1. Start a counter at 0
// 2. Loop through each character in the word
// 3. If the character matches the target letter, add 1 to counter
// 4. Return the counter

function countChar(word, targetLetter) {
    let count = 0;
    for (let i = 0; i < word.length; i++) {
        if (word[i] === targetLetter) {
            count++;
        }
    }
    return count;
}

console.log(countChar("banana", "a")); // 3
```

---

# Walkthrough: Finding the Largest Number

**Problem**: Given an array, find the largest number.

```javascript
function findMax(numbers) {
    // Start by assuming the first number is the largest
    let max = numbers[0];

    // Loop through the rest of the array
    for (let i = 1; i < numbers.length; i++) {
        // If we find something bigger, update max
        if (numbers[i] > max) {
            max = numbers[i];
        }
    }

    return max;
}

console.log(findMax([14, 7, 23, 3, 42, 18])); // 42
```

---

# Building Functions That Call Functions

Functions can **work together**:

```javascript
function celsiusToFahrenheit(celsius) {
    return (celsius * 9/5) + 32;
}

function getWeatherMessage(celsius) {
    let fahrenheit = celsiusToFahrenheit(celsius);

    if (fahrenheit >= 80) {
        return `${fahrenheit}°F — It's hot outside!`;
    } else if (fahrenheit >= 60) {
        return `${fahrenheit}°F — Nice weather!`;
    } else {
        return `${fahrenheit}°F — Bundle up!`;
    }
}

console.log(getWeatherMessage(30)); // "86°F — It's hot outside!"
```

---

# What is a Callback?

A **callback** is a function you **pass into another function** to be called later:

```javascript
function doMath(a, b, operation) {
    return operation(a, b);
}

function add(x, y) {
    return x + y;
}

function multiply(x, y) {
    return x * y;
}

console.log(doMath(4, 5, add));      // 9
console.log(doMath(4, 5, multiply)); // 20
```

**Notice**: We pass `add` and `multiply` **without parentheses** — we're passing the function itself, not calling it.

---

# Why Callbacks are Powerful

One flexible function instead of many specific ones:

```javascript
function transformArray(arr, action) {
    let result = [];
    for (let i = 0; i < arr.length; i++) {
        result.push(action(arr[i]));
    }
    return result;
}

let numbers = [1, 2, 3, 4, 5];

let doubled = transformArray(numbers, function(n) { return n * 2; });
let squared = transformArray(numbers, function(n) { return n * n; });

console.log(doubled); // [2, 4, 6, 8, 10]
console.log(squared); // [1, 4, 9, 16, 25]
```

---

# Try This!

Write a function called `rankScore` that:
1. Takes an array of scores
2. Calculates the average
3. Returns a rank: "Gold" (90+), "Silver" (75-89), "Bronze" (60-74), or "No rank" (below 60)

**Start with pseudocode!**

```
// 1. Calculate the sum of all scores
// 2. Divide by the number of scores to get the average
// 3. Use conditionals to determine the rank
// 4. Return the rank
```

**Bonus**: What should happen if the array is empty?

---

# Key Takeaways

- An **algorithm** is a step-by-step plan to solve a problem
- **Pseudocode** helps you plan before you code — write steps in plain English
- Complex problems are easier when you **break them into smaller functions**
- **Callbacks** pass functions as arguments — making your code flexible and reusable
- Pass functions **without parentheses** to use them as callbacks

**Next week**: HTML Basics — you'll start building real web pages!
