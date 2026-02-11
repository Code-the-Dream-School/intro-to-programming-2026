---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 2: Loops and Arrays"
---

# Lesson 2: Loops and Arrays

**Mentor Session Slide Deck**

Topics: `for` Loops, `while` Loops, Arrays, Array Methods, Scope

---

# Why Loops?

Computers are great at **repetition**. Instead of writing:

```javascript
console.log("Welcome, student 1!");
console.log("Welcome, student 2!");
console.log("Welcome, student 3!");
// ... 97 more times?
```

We use a **loop**:

```javascript
for (let i = 1; i <= 100; i++) {
    console.log(`Welcome, student ${i}!`);
}
```

---

# Anatomy of a `for` Loop

```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
// Output: 0, 1, 2, 3, 4
```

Three parts:
1. **Initialization**: `let i = 0` — where do we start?
2. **Condition**: `i < 5` — when do we stop?
3. **Increment**: `i++` — how do we move forward?

**Watch out**: `< 5` gives you 0-4 (5 items). `<= 5` gives you 0-5 (6 items).

---

# `while` Loops

Use `while` when you don't know how many times you'll loop:

```javascript
let guess = "";

while (guess !== "javascript") {
    guess = prompt("Guess the programming language:");
}

console.log("Correct!");
```

**Caution**: Always make sure the condition will eventually become `false`, or you'll get an **infinite loop**!

---

# Arrays: Lists of Data

An array holds **multiple values** in order:

```javascript
let colors = ["red", "blue", "green", "yellow"];

console.log(colors[0]);      // "red" (first item)
console.log(colors[2]);      // "green" (third item)
console.log(colors.length);  // 4
```

**Remember**: Arrays are **zero-indexed** — the first item is at index `0`, not `1`.

---

# Common Array Methods

```javascript
let fruits = ["apple", "banana"];

fruits.push("cherry");       // Add to end → ["apple", "banana", "cherry"]
fruits.pop();                // Remove from end → ["apple", "banana"]
fruits.includes("apple");   // Check if exists → true
fruits.indexOf("banana");   // Find position → 1
```

| Method | What it does |
|--------|-------------|
| `.push()` | Add to the end |
| `.pop()` | Remove from the end |
| `.includes()` | Check if value exists |
| `.length` | How many items |

---

# Looping Through Arrays

```javascript
let languages = ["JavaScript", "Python", "Java", "C++"];

for (let i = 0; i < languages.length; i++) {
    console.log(`${i + 1}. ${languages[i]}`);
}
```

**Output**:
```
1. JavaScript
2. Python
3. Java
4. C++
```

**Tip**: Use `languages.length` instead of a hardcoded number — it works even if the array changes.

---

# Building a New Array from a Loop

```javascript
let prices = [10, 25, 8, 42, 15];
let discounted = [];

for (let i = 0; i < prices.length; i++) {
    discounted.push(prices[i] * 0.8); // 20% off
}

console.log(discounted); // [8, 20, 6.4, 33.6, 12]
```

**Pattern**: Create an empty array → loop through the original → push transformed values into the new one.

---

# Scope: Where Variables Live

```javascript
let globalVar = "I'm everywhere";   // Global scope

function myFunction() {
    let functionVar = "I'm inside the function";  // Function scope

    if (true) {
        let blockVar = "I'm inside the if block";  // Block scope
        console.log(globalVar);    // ✅ Works
        console.log(functionVar);  // ✅ Works
        console.log(blockVar);     // ✅ Works
    }

    console.log(blockVar);  // ❌ Error! Out of scope
}

console.log(functionVar);  // ❌ Error! Out of scope
```

---

# Try This!

Write a function called `countDown` that:
1. Takes a number parameter `start`
2. Uses a loop to print numbers from `start` down to 1
3. Prints "Go!" after the loop ends

```javascript
// Expected: countDown(3) prints:
// 3
// 2
// 1
// Go!
```

**Bonus**: Write a function `filterLongWords` that takes an array of strings and returns a new array with only the words longer than 5 characters.

---

# Key Takeaways

- **`for` loops** are great when you know how many times to repeat
- **`while` loops** are great when you repeat until a condition changes
- **Arrays** store ordered lists of data, starting at index `0`
- **Array methods** like `.push()`, `.pop()`, `.includes()` are your toolkit
- **Scope** determines where a variable can be accessed

**Next week**: Objects — grouping related data together with key-value pairs
