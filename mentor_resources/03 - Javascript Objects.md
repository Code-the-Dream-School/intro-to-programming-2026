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

# Lesson 3: JavaScript Objects

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

Think about a pet, a car, or your phone. If you had to describe it using **properties**, what would they be?

Example: A dog might have `name`, `breed`, `age`, `color`.

<!--
This is a natural lead-in to objects as key-value pairs.
Let a few students share and connect their answers to the concept.
-->

---

# What You'll Learn This Week

- **Objects** — storing related data together
- **Properties** — accessing and changing values
- **Methods** — functions that belong to objects
- **for...in loops** — looping through object properties
- **Git: commit & push** — saving your work to GitHub

---

# I Do: What Is an Object?

An object stores **related data** as key-value pairs.

```javascript
let myPet = {
    name: "Teddy",
    species: "ferret",
    color: "brown"
};
```

Think of it like a **profile card** — each piece of info has a label.

---

# I Do: Accessing Properties

Two ways to read a property:

**Dot notation** (most common):
```javascript
console.log(myPet.name);     // "Teddy"
console.log(myPet.species);  // "ferret"
```

**Bracket notation** (useful with variables):
```javascript
let key = "color";
console.log(myPet[key]);     // "brown"
```

---

# I Do: Changing Properties

Update an existing property:
```javascript
myPet.name = "Henry";
console.log(myPet.name);  // "Henry"
```

Add a new property:
```javascript
myPet.age = 3;
```

Delete a property:
```javascript
delete myPet.color;
```

---

# I Do: Looping Through Objects

Use a `for...in` loop to visit every property:

```javascript
for (let key in myPet) {
    console.log(key + ":", myPet[key]);
}
```

Output:
```
name: Henry
species: ferret
age: 3
```

> Notice: we use **bracket notation** with the variable `key`.

---

# I Do: Object Methods

A method is a **function inside an object**.

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

`this` refers to **the object itself**.

---

# I Do: Arrays of Objects

Objects and arrays work great together:

```javascript
let pets = [
    { name: "Teddy", species: "ferret" },
    { name: "Oshie", species: "cat" },
    { name: "Sunny", species: "dog" }
];

console.log(pets[0].name);  // "Teddy"
console.log(pets[2].species);  // "dog"
```

You can loop through with a regular `for` loop or `forEach`.

---

# I Do: Constructor Functions

A **blueprint** for creating multiple similar objects:

```javascript
function Dog(name, breed, age) {
    this.name = name;
    this.breed = breed;
    this.age = age;
}

let dog1 = new Dog("Kroger", "greyhound", 8);
let dog2 = new Dog("Destiny", "shepherd", 14);
```

> The `new` keyword creates a fresh object each time.

---

<!--
Transition to We Do:
- Ask: "What questions do you have so far?"
- Reinforce that objects are just a way to group related data.
-->

# We Do: Let's Code Together! (15-20 min)

Open your browser console or [replit.com](https://replit.com).

**Let's build something together!**

---

# We Do: Create an Object

**Challenge:** Build a student profile object.

**Ask the group:** What properties should a student have?

```javascript
let student = {
    name: "Maria",
    course: "Intro to Programming",
    week: 3
};
```

**Follow-up:** How do we access the student's name?

---

# We Do: Add a Method

**Challenge:** Add a `describe` method to our student.

```javascript
student.describe = function() {
    return `${this.name} is in ${this.course}, week ${this.week}.`;
};

console.log(student.describe());
// "Maria is in Intro to Programming, week 3."
```

**Ask the group:** What does `this` refer to here?

---

# We Do: Loop Through Properties

**Challenge:** Print every property of our student object.

```javascript
for (let key in student) {
    console.log(key + ": " + student[key]);
}
```

**Ask the group:** What will this output? (Predict first!)

<!--
Remind students that the describe function will also show up
since it's a property. This is a good teaching moment about
typeof checks if it comes up.
-->

---

# We Do: Array of Objects

**Challenge:** Create a list of pets and print each one.

```javascript
let pets = [
    { name: "Teddy", species: "ferret", color: "brown" },
    { name: "Oshie", species: "cat", color: "orange" },
    { name: "Sunny", species: "dog", color: "black" }
];

pets.forEach(function(pet) {
    console.log(pet.name + " the " + pet.species);
});
```

**Zoom chat:** How is `forEach` different from a `for` loop?

---

<!--
Transition to You Do:
Set a timer for 5-10 minutes.
-->

# You Do: Independent Practice (5-10 min)

Pick **one** to try on your own:

**A)** Create an object for your favorite book or movie with at least 3 properties. Log each property.

**B)** Add a `describe` method to your object that returns a sentence about it.

**C)** Create an array of 3 objects (books, movies, or foods). Use a loop to print each one.

---

# You Do: Share Out

**Who wants to share their object?**

- What properties did you choose?
- Did you try adding a method?

---

# Assignment Preview

This week's assignment has **10 questions**:

- **Q1-Q2:** Create and modify an object
- **Q3:** Loop through properties with `for...in`
- **Q4:** Add a `describe` method (uses `this`)
- **Q5:** Delete a property
- **Q6:** Array of objects with `forEach`
- **Q7-Q8:** Constructor functions and comparing objects
- **Q9-Q10:** The built-in `Date` object

---

# Git This Week: Commit & Push

This week you'll learn to **save and upload** your changes:

```
git add .
git commit -m "my first commit"
git push origin lesson-3
```

- `add` — stage your changes
- `commit` — save a snapshot with a message
- `push` — send it to GitHub

> The lesson video walks through each step!

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel creating and using objects?

### Before next session:
- Work through the **lesson materials** (objects, Git commit/push)
- Complete the **coding assignment** (10 questions)
- **Commit and push** changes to your GitHub repo
- Reach out on **Slack** if you get stuck!

---

# Resources

- **JavaScript.info:** [Objects](https://javascript.info/object)
- **MDN:** [Object Basics](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Object_basics)
- **W3Schools:** [for...in Loop](https://www.w3schools.com/js/js_loop_forin.asp)

> **Next week:** JavaScript Algorithms!

---

<!-- _class: title-slide -->

# Great work this week!

## Objects let you organize your data like a pro.

Questions? Reach out on Slack anytime.
