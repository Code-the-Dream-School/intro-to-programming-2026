---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 1: JavaScript Basics and Functions"
---

# Lesson 1: JavaScript Basics and Functions

**Mentor Session Slide Deck**

Topics: Variables, Data Types, Conditionals, Functions

---

# What is JavaScript?

- The programming language of the web
- Runs in every browser — you can open the console right now and try it
- Used to make websites **interactive** and **dynamic**

**This week**: We start with the building blocks — storing data, making decisions, and organizing code into reusable pieces.

---

# Variables: Storing Information

Variables are like **labeled boxes** that hold data.

```javascript
let city = "Durham";
const state = "NC";
let population = 300000;
```

- `let` — the value can change later
- `const` — the value stays the same

**Quick check**: What happens if you try to reassign a `const`?

---

# Data Types

JavaScript has several basic data types:

| Type | Example |
|------|---------|
| String | `"Hello"`, `'World'` |
| Number | `42`, `3.14`, `-7` |
| Boolean | `true`, `false` |

```javascript
let name = "Ada";        // String
let score = 95;           // Number
let isEnrolled = true;    // Boolean
```

---

# String Concatenation

Joining strings together:

```javascript
let firstName = "Grace";
let lastName = "Hopper";

// Using the + operator
let fullName = firstName + " " + lastName;

// Using template literals (backticks)
let greeting = `Hello, ${firstName} ${lastName}!`;
```

**Try it**: Which method do you find easier to read?

---

# Conditionals: Making Decisions

```javascript
let score = 85;

if (score >= 90) {
    console.log("Excellent work!");
} else if (score >= 70) {
    console.log("Good job, keep it up!");
} else {
    console.log("Let's review the material.");
}
```

**Predict**: What will this print? Why?

---

# Common Comparison Operators

| Operator | Meaning |
|----------|---------|
| `===` | Strict equality (value AND type) |
| `!==` | Strict inequality |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

**Important**: Use `===` not `==`. Strict equality prevents surprises!

---

# Functions: Reusable Code

A function is a **named block of code** you can call whenever you need it.

```javascript
function greetStudent(name) {
    return `Welcome to Code the Dream, ${name}!`;
}

console.log(greetStudent("Maria"));
// Output: Welcome to Code the Dream, Maria!

console.log(greetStudent("James"));
// Output: Welcome to Code the Dream, James!
```

---

# Functions with Multiple Parameters

```javascript
function calculateArea(length, width) {
    let area = length * width;
    return area;
}

console.log(calculateArea(5, 3));  // 15
console.log(calculateArea(10, 7)); // 70
```

**Key concepts**:
- **Parameters** = the placeholders (`length`, `width`)
- **Arguments** = the actual values you pass in (`5`, `3`)
- **Return** = what the function gives back

---

# Try This!

Write a function called `isEligible` that:
1. Takes a parameter `age`
2. Returns `true` if the age is 18 or older
3. Returns `false` otherwise

```javascript
// Your pseudocode first:
// 1. Define the function with an age parameter
// 2. Check if age is >= 18
// 3. Return true or false

// Then write the code!
```

**Bonus**: Can you add a second parameter for a `hasPermission` boolean?

---

# Key Takeaways

- **Variables** store data — use `let` for changing values, `const` for fixed ones
- **Data types**: strings, numbers, booleans are the basics
- **Conditionals** let your code make decisions with `if/else`
- **Functions** make code reusable — define once, call many times
- Always use `console.log()` to check your work!

**Next week**: Loops and Arrays — doing things repeatedly and working with lists of data
