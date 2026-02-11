---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 3: JavaScript Objects"
---

# Lesson 3: JavaScript Objects

**Mentor Session Slide Deck**

Topics: Object Basics, Properties, Methods, `for...in`, Constructors, `this`

---

# What is an Object?

An object groups **related data** using key-value pairs:

```javascript
let book = {
    title: "The Great Gatsby",
    author: "F. Scott Fitzgerald",
    pages: 180,
    isAvailable: true
};
```

Think of it like a **profile card** — each piece of information has a label (key) and a value.

---

# Accessing Object Properties

**Dot notation** (most common):
```javascript
console.log(book.title);   // "The Great Gatsby"
console.log(book.pages);   // 180
```

**Bracket notation** (useful when the key is stored in a variable):
```javascript
let field = "author";
console.log(book[field]);  // "F. Scott Fitzgerald"
```

---

# Modifying Objects

```javascript
let book = {
    title: "The Great Gatsby",
    author: "F. Scott Fitzgerald",
    pages: 180
};

// Change a property
book.pages = 182;

// Add a new property
book.genre = "Classic Fiction";

// Remove a property
delete book.pages;

console.log(book);
// { title: "The Great Gatsby", author: "F. Scott Fitzgerald", genre: "Classic Fiction" }
```

---

# Looping Through Objects with `for...in`

```javascript
let movie = {
    title: "Inception",
    director: "Christopher Nolan",
    year: 2010
};

for (let key in movie) {
    console.log(`${key}: ${movie[key]}`);
}
```

**Output**:
```
title: Inception
director: Christopher Nolan
year: 2010
```

**Note**: `key` is the property **name** (a string). Use `movie[key]` to get the **value**.

---

# Object Methods

Objects can contain **functions** too — we call them **methods**:

```javascript
let calculator = {
    brand: "Casio",
    add: function(a, b) {
        return a + b;
    },
    subtract: function(a, b) {
        return a - b;
    }
};

console.log(calculator.add(10, 4));      // 14
console.log(calculator.subtract(10, 4)); // 6
```

---

# The `this` Keyword

Inside a method, `this` refers to **the object the method belongs to**:

```javascript
let student = {
    name: "Elena",
    course: "Intro to Programming",
    introduce: function() {
        return `Hi, I'm ${this.name} and I'm taking ${this.course}.`;
    }
};

console.log(student.introduce());
// "Hi, I'm Elena and I'm taking Intro to Programming."
```

**Why `this`?** It makes methods flexible — they always refer to their own object's data.

---

# Constructor Functions

When you need **multiple objects** with the same structure:

```javascript
function Movie(title, director, year) {
    this.title = title;
    this.director = director;
    this.year = year;
}

let movie1 = new Movie("Coco", "Adrian Molina", 2017);
let movie2 = new Movie("Parasite", "Bong Joon-ho", 2019);

console.log(movie1.title); // "Coco"
console.log(movie2.year);  // 2019
```

The `new` keyword creates a **new instance** from the blueprint.

---

# Arrays vs. Objects

| Feature | Array | Object |
|---------|-------|--------|
| Access by | Index (number) | Key (string) |
| Ordered? | Yes | Not guaranteed |
| Best for | Lists of similar items | Grouped related data |
| Syntax | `["a", "b", "c"]` | `{ name: "a", type: "b" }` |

**Often used together**: an array of objects!

```javascript
let students = [
    { name: "Alex", grade: 92 },
    { name: "Sam", grade: 87 }
];
```

---

# Try This!

Create a constructor function called `Song` with properties `title`, `artist`, and `durationMinutes`. Then:

1. Create two `Song` instances
2. Add a method called `describe` that returns a string like: `"'Imagine' by John Lennon (3 min)"`
3. Loop through an array of your songs and log each description

```javascript
// Starter:
function Song(title, artist, durationMinutes) {
    // your code here
}
```

---

# Key Takeaways

- **Objects** store data as key-value pairs — great for grouping related info
- Access properties with **dot notation** or **bracket notation**
- **`for...in`** loops through an object's keys
- **Methods** are functions inside objects — use `this` to access the object's data
- **Constructor functions** create multiple objects from the same blueprint

**Next week**: Algorithms, Pseudocode, and Callbacks — planning your code before writing it
