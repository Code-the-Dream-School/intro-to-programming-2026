# Week 3 Answer Key — JavaScript Objects

## Setup & submission

- **One JavaScript file**, worked top-to-bottom. Students write each answer directly below the commented instructions and run after every question. Lessons 1–4 still run via the **Learns App "RUN" button** (no local environment yet).
- Sample `console.log` lines in the file are commented out — students must **uncomment them** (remove `//`) to see output.
- Submission flow: run the code and self-check output → run the **AI Reviewer** → correct → submit the code.
- **GitHub task (non-coding):** this week students make their first change via the terminal on a new branch. Confirm: (1) `README.md` updated to contain their full name, (2) a new `index.html` created at the **repo root** (same level as `README.md`), (3) both changes committed on the **`lesson-3` branch**, not `main`. The **`lesson-3` branch link** goes in the "second link to assignment"/URL2 field. No code to grade — just confirm the branch link (not the `main` link) is what's submitted, since a `main` link won't show this week's changes.

---

### Q1 — Create an object · Objective
```js
let myPet = {
  name: "Teddy",
  species: "ferret",
  color: "brown",
};
console.log("Q1 object: ", myPet);
console.log("Q1 name: ", myPet.name);
console.log("Q1 species: ", myPet.species);
console.log("Q1 color: ", myPet.color);
```
Expected: the full object prints, then each value. Check for three `key: value` pairs and dot-notation access. Values are personal.

### Q2 — Modify a property · Objective
```js
myPet.name = "Henry";
console.log("Q2 updated object", myPet);
```
Expected: `{ name: 'Henry', species: 'ferret', color: 'brown' }` — only `name` changed. Reassignment via `myPet.name = ...`, not a redeclaration.

> Mentor note: if `myPet` were `const`, this still works — mutating a property is allowed; only rebinding the variable errors. A common predict-then-check miss is expecting an error here.

### Q3 — `for...in` loop · Objective
```js
for (let key in myPet) {
  console.log("Q3: " + key + ":", myPet[key]);
}
```
Expected:
```
Q3: name: Henry
Q3: species: ferret
Q3: color: brown
```
> Mentor note: inside the loop the key is a variable, so it must be `myPet[key]` (bracket). `myPet.key` looks for a literal property named "key" and prints `undefined`.

### Q4 — Object method · Objective
```js
myPet.describe = function () {
  return `${myPet.name} is a ${myPet.color} ${myPet.species}.`;
};
console.log("Q4: ", myPet.describe());
```
Expected: `Q4:  Teddy is a brown ferret.` (order is name, color, species). The method takes no parameters and **returns** the sentence.

**Stretch — use `this`:**
```js
myPet.describe = function () {
  return `${this.name} is a ${this.color} ${this.species}.`;
};
```
> Mentor note: `this` refers to the object the method is called on, so `describe` keeps working even if `myPet` is renamed or copied. Hardcoding `myPet.name` breaks that reusability.

### Q5 — Delete a property · Objective
```js
delete myPet.color;
console.log("Q5", "Color property deleted:", !myPet.hasOwnProperty("color"));
```
Expected: `Q5 Color property deleted: true`.
> Mentor note: `hasOwnProperty('color')` returns `false` after deletion; the leading `!` flips it to `true`. Students often confuse which value is actually being printed.

### Q6 — Array of objects + `forEach` · Objective
```js
const pets = [
  { name: "WillBe", species: "bird", color: "gray" },
  { name: "Oshie", species: "cat", color: "multi" },
  { name: "Sunny", species: "dog", color: "black" },
];

function printPets(pets) {
  pets.forEach(function (pet) {
    console.log(pet);
  });
}

console.log("Q6:");
printPets(pets);
```
Expected: the three pet objects print, one per line. Check that the `console.log` is **inside** the `forEach` callback and the callback has a parameter. Values are student choice.

### Q7 — Constructor function · Objective
```js
function Dog(name, breed, age) {
  this.name = name;
  this.breed = breed;
  this.age = age;
}

let dog1 = new Dog("Kroger", "greyhound", 8);
let dog2 = new Dog("Destiny", "shepherd", 14);

console.log("Q7", dog1);
console.log("Q7", dog2);
```
Expected: `Dog { name: 'Kroger', breed: 'greyhound', age: 8 }` and the second instance. Check for capitalized name, `this.x = x` assignments, and calling with `new`.
> Mentor note: omitting `new` makes `this` attach to the wrong object and returns `undefined` — a silent failure worth pointing out.

### Q8 — Compare a property · Objective
```js
function isSameBreed(dog1, dog2) {
  return dog1.breed === dog2.breed;
}

let dog3 = new Dog("Rex", "greyhound", 3); // same breed as dog1, different name/age

console.log("Q8: Same breed - dog1 vs dog2:", isSameBreed(dog1, dog2));
console.log("Q8: Same breed - dog1 vs dog3:", isSameBreed(dog1, dog3));
```
Expected: `false`, then `true`. Must compare the **`breed` property**, not the whole objects with `===`. Confirm `dog3` is defined and reuses the `Dog` constructor with dog1's breed.

### Q9 — `Date` object · Objective
```js
let currentDate = new Date();
console.log("Q9: Current Date:", currentDate);
```
Expected: a full timestamp, e.g. `Q9: Current Date: 2025-09-13T23:47:23.858Z` — exact value differs by run. Check it's `new Date()` (with `new`), not a string.

### Q10 — Extract date parts · Objective
```js
let year = currentDate.getFullYear();
let month = currentDate.getMonth();
let day = currentDate.getDate();
console.log("Q10 Year:", year);
console.log("Q10 Month:", month);
console.log("Q10 Day:", day);
```
Expected: three labeled values from the same `currentDate`.
> Mentor note: `.getMonth()` is **zero-indexed** — September returns `8`, not `9`. The assignment's own sample (`Q10 Month: 9`) reflects October; grade the method used, not the literal, and confirm the student understands the offset.
