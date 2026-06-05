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
  The other leads the Apply section (slides 16–27).
  Both mentors stay on screen throughout. The second mentor can support questions during Explore.

Speaker notes (mentor-only guidance) appear in comment blocks like this one.
In Marp presenter mode, notes display in your presenter panel.
-->

<!-- _class: title -->

# Lesson 3: JavaScript Objects

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Describe what an object is and why we use one
- Create an object with properties and access its values
- Modify, add, and delete object properties
- Write a method inside an object using `this`
- Loop through object properties with `for...in`
- Build and use an array of objects
- Create objects from a constructor function
- Commit and push changes to GitHub

<!--
Welcome students and take a quick attendance or emoji check-in.
Let them know today has two main parts: learning objects (Explore), then applying them in live code (Apply).
The Git material is brief — most of the focus is on objects.
-->

---

<!-- _class: section-break -->

# Explore

---

# What Is an Object?

A **primitive** stores one value. An **object** groups many values together.

```javascript
// Primitive — one value
let petName = "Teddy";

// Object — many related values grouped together
let myPet = {
  name: "Teddy",
  species: "ferret",
  color: "brown"
};
```

> Think of an object like a profile card — each piece of info has a label.

<!--
Ask students: "What would you put on a profile card for a person?"
Let them suggest a few properties, then connect those suggestions to key-value pairs.
This helps them see that objects model real-world things.
-->

---

# Keys and Values

Every item inside an object has two parts: a **key** and a **value**.

```javascript
let myPet = {
  name: "Teddy",    // key: "name",    value: "Teddy"
  species: "ferret" // key: "species", value: "ferret"
};
```

- The **key** is the label (always a string)
- The **value** can be any data type — string, number, boolean, even a function

> Separate key-value pairs with a comma. No comma after the last one (though JavaScript is forgiving).

<!--
Students often forget commas between properties or add one after the last property.
Mention both mistakes and note that a trailing comma actually works in modern JS —
but it's good practice to be consistent.
-->

---

# Accessing Properties

Two ways to read a property from an object:

**Dot notation** — most common:
```javascript
console.log(myPet.name);     // "Teddy"
console.log(myPet.species);  // "ferret"
```

**Bracket notation** — useful when the key is stored in a variable:
```javascript
let key = "color";
console.log(myPet[key]);     // "brown"
```

<!--
Most students will only need dot notation for the assignment.
Mention bracket notation briefly so they aren't confused when they see it.
The for...in loop (coming up) uses bracket notation — connect back to this slide when you get there.
-->

---

# Modifying and Deleting Properties

**Update** an existing property:
```javascript
myPet.name = "Henry";
console.log(myPet.name);  // "Henry"
```

**Add** a new property:
```javascript
myPet.age = 3;
```

**Delete** a property:
```javascript
delete myPet.color;
console.log(myPet.hasOwnProperty("color")); // false
```

<!--
Q2 and Q5 in the assignment map directly to this slide.
For Q5, students use hasOwnProperty() to verify the deletion — point that out here.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What does this code print?**

```javascript
const user = { name: "Alex", score: 10 };
user.score = 25;
console.log(user.score);
```

A) `10` — the original value

B) `25` — the updated value

C) `undefined` — `score` was deleted

D) An error — you cannot change a `const`

<!--
Answer: B.
Common wrong answer: D. Clarify that const prevents reassigning the variable itself
(you cannot do user = {something else}), but you CAN still change the properties inside the object.
This is a concept students often find surprising — worth slowing down for.
-->

---

# Looping Through an Object

Use a `for...in` loop to visit every property:

```javascript
for (let key in myPet) {
  console.log(key + ":", myPet[key]);
}
// name: Henry
// species: ferret
// age: 3
```

> Inside the loop, `key` is a variable — so you must use **bracket notation**: `myPet[key]`.

<!--
Q3 in the assignment asks students to write exactly this pattern.
Pause here and ask: "Why can't we use myPet.key instead of myPet[key]?"
Answer: because key is a variable, not the literal property name "key".
This is the moment bracket notation clicks for most students.
-->

---

# Object Methods

A **method** is a function stored as a property of an object.

```javascript
let myPet = {
  name: "Teddy",
  species: "ferret",
  describe: function() {
    return `${this.name} is a ${this.species}.`;
  }
};

console.log(myPet.describe());
// "Teddy is a ferret."
```

`this` refers to **the object the method belongs to**.

<!--
Q4 in the assignment asks students to add a describe method.
The stretch goal is to use "this" instead of referencing myPet directly.
Explain that using "this" is better practice — if you rename the object, the method still works.
Keep the explanation of "this" simple for now. Deep dives come later in the course.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What does `this` refer to inside a method?**

```javascript
let car = {
  brand: "Toyota",
  describe: function() {
    return "This car is a " + this.brand;
  }
};
```

A) The `describe` function itself

B) The `car` object

C) The global window object

D) The word "this" — it is just a string

<!--
Answer: B.
"this" inside a method refers to the object the method is called on.
If students ask about arrow functions and "this" — acknowledge it's a great question
and tell them it behaves differently in arrow functions, which they'll explore later.
-->

---

# Arrays of Objects

You can put objects inside an array. This is very common.

```javascript
let pets = [
  { name: "Teddy", species: "ferret", color: "brown" },
  { name: "Oshie", species: "cat",    color: "orange" },
  { name: "Sunny", species: "dog",    color: "black" }
];
```

Loop through them with `forEach`:

```javascript
pets.forEach(function(pet) {
  console.log(pet.name, "the", pet.species);
});
```

<!--
Q6 in the assignment asks students to create a pets array and write a printPets function using forEach.
The pattern here maps exactly to what they need to do.
Point out that each element in the array is itself a full object.
-->

---

# Constructor Functions

A constructor function is a **blueprint** for making many similar objects.

```javascript
function Dog(name, breed, age) {
  this.name  = name;
  this.breed = breed;
  this.age   = age;
}

let dog1 = new Dog("Kroger", "greyhound", 8);
let dog2 = new Dog("Destiny", "shepherd", 14);
console.log(dog1);
// Dog { name: 'Kroger', breed: 'greyhound', age: 8 }
```

> The `new` keyword creates a fresh object each time.

<!--
Q7 and Q8 in the assignment use constructor functions.
Analogy: a constructor is like a cookie cutter — the cutter (constructor) stays the same,
but each cookie (object) has its own values.
Note the capital D in "Dog" — naming constructors with a capital letter is a convention.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What does the `new` keyword do?**

```javascript
let dog1 = new Dog("Rex", "labrador", 4);
```

A) Runs the function and prints the result

B) Creates a new object using `Dog` as a blueprint

C) Creates a copy of an existing `Dog` object

D) Deletes the previous `Dog` object

<!--
Answer: B.
Students sometimes think "new" copies an existing object. Clarify: it creates a brand new one
from the constructor blueprint, with whatever values you pass as arguments.
-->

---

# The Built-In Date Object

JavaScript has built-in objects. `Date` is one of them.

```javascript
let currentDate = new Date();
console.log(currentDate);
// 2025-09-13T23:47:23.858Z

let year  = currentDate.getFullYear(); // 2025
let month = currentDate.getMonth();    // 8 (zero-indexed!)
let day   = currentDate.getDate();     // 13
```

> Months are **zero-indexed**: January = 0, December = 11.

<!--
Q9 and Q10 in the assignment cover this.
The zero-indexed months always catch students off guard — make sure to pause on that.
Ask: "If getMonth() returns 8, what month is it?" (September).
-->

---

<!-- _class: section-break -->

# Apply

<!--
Second mentor leads from here (suggested).
Open a browser console or the class coding environment before this slide.
  Chrome / Edge: Right-click anywhere → Inspect → Console
  Firefox: Right-click anywhere → Inspect → Console
You'll drive the typing. Students tell you what to type — that's the goal.
-->

---

# Core Activity: Let's Code Together

We'll build a pet profile step by step — **you tell me what to type.**

Open your browser console:
- **Chrome / Edge:** Right-click anywhere → Inspect → Console
- **Firefox:** Right-click anywhere → Inspect → Console

This mirrors what you'll do in the assignment.

<!--
Type in the browser console so students see output immediately.
If a student suggests something wrong, type it anyway and let the error teach the lesson.
Narrate your thinking out loud: "I'm not sure about that — let's try it and see."
-->

---

# Step 1 — Create the Object

**Ask the group:** What three properties should our pet have?

```javascript
let myPet = {
  name: "Mochi",
  species: "rabbit",
  color: "white"
};

console.log("Q1 object:", myPet);
console.log("Q1 name:", myPet.name);
```

**Follow-up:** How do we read just the species?

<!--
This maps to Q1 in the assignment. Let students decide the property values.
The goal is to practice creating an object and reading properties with dot notation.
-->

---

# Step 2 — Modify a Property

**Ask the group:** How do we change the pet's name?

```javascript
myPet.name = "Coco";
console.log("Q2 updated object:", myPet);
```

**Ask the group:** What will the output look like now?

<!--
This maps to Q2. Have students predict the output before you run the code.
Ask: "Did the other properties change?" (No — only the one we assigned.)
-->

---

# Step 3 — Loop Through Properties

**Ask the group:** How do we print every property automatically?

```javascript
for (let key in myPet) {
  console.log("Q3: " + key + ":", myPet[key]);
}
```

**Ask the group:** Why do we write `myPet[key]` instead of `myPet.key`?

<!--
This maps to Q3. Pause before running the code and ask students to predict each line of output.
Reinforce the bracket notation point from the Explore section.
-->

---

# Step 4 — Add a Method

**Challenge:** Add a `describe` method that returns a full sentence.

```javascript
myPet.describe = function() {
  return `${this.name} is a ${this.color} ${this.species}.`;
};

console.log("Q4:", myPet.describe());
```

**Ask the group:** What does `this.name` refer to here?

<!--
This maps to Q4. Start by writing the method without "this" (using myPet.name directly),
then swap in "this" and ask students what changed — and why "this" is more flexible.
-->

---

# Step 5 — Delete a Property

**Challenge:** Remove the `color` property and verify it is gone.

```javascript
delete myPet.color;
console.log("Q5 Color deleted:", !myPet.hasOwnProperty("color"));
```

**Ask the group:** What do you expect `hasOwnProperty` to return after deleting?

<!--
This maps to Q5. The ! (not) operator flips false to true, which is what the expected output shows.
Walk through the logic: hasOwnProperty returns false (property is gone) → ! flips it to true.
-->

---

# Step 6 — Array of Objects + forEach

**Challenge:** Build a pets array and print each one.

```javascript
let pets = [
  { name: "Mochi",  species: "rabbit", color: "white" },
  { name: "Shadow", species: "cat",    color: "black" },
  { name: "Pebble", species: "dog",    color: "tan"   }
];

function printPets(arr) {
  arr.forEach(function(pet) {
    console.log(pet);
  });
}
printPets(pets);
```

<!--
This maps to Q6. Ask students to explain what forEach is doing before running the code.
Optionally ask: "How could we change this to print just the name of each pet?"
-->

---

<!-- _class: section-break -->

# Extension Activity

*Only if time allows and students are ready.*

---

# Extension — Compare Two Objects

**Challenge:** Write a function that checks whether two objects have the same keys and values.

```javascript
function areObjectsEqual(obj1, obj2) {
  let keys1 = Object.keys(obj1);
  let keys2 = Object.keys(obj2);
  if (keys1.length !== keys2.length) return false;
  for (let key of keys1) {
    if (obj1[key] !== obj2[key]) return false;
  }
  return true;
}
```

This is Q8 in the assignment — the hardest question.

<!--
Walk through the logic step by step:
  1. Check if both objects have the same number of keys.
  2. Loop through each key and compare values.
  3. If any value differs, return false immediately. If all match, return true.
Object.keys() is worth explaining — it returns an array of an object's keys.
Let students try it with dog1 and dog3 (same values) vs dog1 and dog2 (different values).
Only go here if you have 10+ minutes remaining.
-->

---

# Assignment Preview

**10 questions** this week — all about objects:

| Questions | Topic |
|-----------|-------|
| Q1–Q2 | Create an object and modify a property |
| Q3 | Loop through properties with `for...in` |
| Q4 | Add a `describe` method (use `this` for the stretch goal) |
| Q5 | Delete a property and verify with `hasOwnProperty` |
| Q6 | Array of objects with `forEach` |
| Q7 | Constructor function — create two `Dog` instances |
| Q8 | Compare two objects for equal keys and values |
| Q9–Q10 | Built-in `Date` object — get year, month, and day |

<!--
Don't walk through every question in detail — this is just an overview.
Tell students that Q1–Q6 follow exactly what we just built together.
Flag Q8 as the most challenging and encourage them to tackle it last.
-->

---

# Git This Week: Commit and Push

This week you save your work to GitHub for the first time.

```
git checkout -b lesson-3
git add .
git commit -m "add index.html and update README with my name"
git push origin lesson-3
```

- `checkout -b` — creates a new branch
- `add .` — stages all your changes
- `commit -m` — saves a snapshot with a message
- `push` — sends it to GitHub

> Paste your `lesson-3` branch link in the "second link" field when you submit.

<!--
Keep this brief — there is a lesson video that walks through the full workflow.
The key thing students need to know: they must be on the lesson-3 branch before they push.
If they get a "fatal: The current branch" error, the message itself contains the fix command — tell them to read it carefully.
-->

---

# Tips for the Assignment

1. **Read the comment above each question** before writing any code
2. **Use `console.log()` on everything** — don't guess, verify
3. **Work through Q1–Q6 first** — they connect directly to what we just coded
4. **Stuck on Q8?** Ask an AI for hints, not the answer:

> "My areObjectsEqual function returns the wrong result for objects with different numbers of keys. Give me 3 hints without showing me the solution."

<!--
Tip 4 models how to use AI productively. Encourage students to describe the specific problem
they are stuck on rather than pasting the whole question.
-->

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel creating and working with objects?

### Before next session:
- Read the **lesson materials** (JavaScript.info Objects, MDN Object Basics)
- Complete the **10-question assignment**
- **Commit and push** your work to your `lesson-3` branch on GitHub
- Post questions in **Slack** anytime — we check it between sessions

<!--
If confidence is low (lots of 1s and 2s), reassure students that objects take time to click.
The assignment is designed to build up gradually — Q1 is simple; they'll gain confidence as they go.
-->

---

# Resources

| Resource | What it covers |
|----------|----------------|
| [JavaScript.info — Objects](https://javascript.info/object) | Full written explanation |
| [MDN — Object Basics](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Object_basics) | Reference and examples |
| [W3Schools — for...in Loop](https://www.w3schools.com/js/js_loop_forin.asp) | Loop reference (Q3) |
| [W3Schools — JavaScript Dates](https://www.w3schools.com/js/js_dates.asp) | Date object reference (Q9–Q10) |
| Slack `#discussion` channel | Questions between sessions |

> **Next week:** JavaScript Algorithms!

---

<!-- _class: title -->

# Great work today!

## Objects help you organize your data like a pro.

Questions? Reach out on Slack anytime.
