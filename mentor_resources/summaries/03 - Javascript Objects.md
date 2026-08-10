# Week 3 — JavaScript Objects

**Learning objective:** Create, manipulate, and iterate over JavaScript objects and Date instances, while demonstrating the ability to manage project versions using a local Git branching and pushing workflow.

## Key concepts taught

- **Objects vs primitives** — objects group related data as key-value pairs; primitives hold a single value. Reinforced with the "profile card" analogy.
- **Keys and values** — keys are string labels; values can be any type, including functions. Comma-separated pairs (trailing comma is tolerated in modern JS).
- **Accessing properties** — dot notation (`myPet.name`) as the default; bracket notation (`myPet[key]`) for when the key lives in a variable.
- **Modifying / adding / deleting** — reassigning a property, adding a new one, `delete`, and verifying with `hasOwnProperty()`. Note: a `const` object's properties *can* still be mutated (only rebinding the variable is blocked — a common surprise).
- **`for...in` loops** — iterate over every property; inside the loop the key is a variable, so bracket notation is required.
- **Object methods and `this`** — a function stored as a property; `this` refers to the object the method belongs to.
- **Arrays of objects + `forEach`** — a very common pattern; each element is a full object.
- **Constructor functions** — a reusable blueprint invoked with `new`; capitalized-name convention (`Dog`).
- **Built-in `Date` object** — `new Date()`, `.getFullYear()`, `.getMonth()` (zero-indexed), `.getDate()`.
- **Git workflow (new this week)** — branch, stage, commit, push: `git checkout -b`, `git add .`, `git commit -m`, `git push origin lesson-3`. Introduces the untracked / modified / staged file states.

Content is delivered via Odin Project *or* Scrimba (JS Deep Dive: objects, primitive vs object types, get/modify object data) — students pick one track. Two **AI Learning Prompts** appear in the lesson: a *retrieval practice* prompt (explain primitive vs object in your own words) and a *predict-then-check* prompt (predict the output of a property reassignment before running it).

## Brief overview of the assignment

A single JavaScript file with **10 numbered questions** built around a `myPet` object, worked top-to-bottom and verified with `console.log()`, plus a separate **GitHub task**. Rough breakdown:

- **Q1–Q2** — create the `myPet` object with `name`/`species`/`color`; then modify the `name` property.
- **Q3** — iterate properties with a `for...in` loop, printing `key: value`.
- **Q4** — add a `describe()` method returning a template-literal sentence. Stretch: use `this` instead of referencing `myPet` directly.
- **Q5** — `delete` the `color` property and verify with `!myPet.hasOwnProperty('color')`.
- **Q6** — build a `pets` array of three objects and a `printPets` function that loops with `forEach`.
- **Q7** — write a `Dog` constructor function and create two instances with `new`.
- **Q8** — write `isSameBreed(dog1, dog2)` comparing the `breed` property; also create a `dog3` matching dog1's breed. (Flagged in slides as the hardest question.)
- **Q9–Q10** — the built-in `Date` object: create `currentDate`, then extract year, month, and day.
- **GitHub task (no code)** — confirm the README has the student's full name and a new `index.html` exists, both committed on the `lesson-3` branch; paste the `lesson-3` branch link in the "second link to assignment" field.

## Likely trouble spots

- **`const` object mutation (Q2, predict-then-check prompt)** — students expect reassigning a property on a `const` object to error. It doesn't; only rebinding the variable does. Slide CFU targets exactly this misconception (common wrong answer: "error").
- **Bracket vs dot notation in `for...in` (Q3)** — writing `myPet.key` instead of `myPet[key]`. `myPet.key` looks for a literal property named "key" and returns `undefined`. This is the moment bracket notation should click.
- **`this` vs direct reference (Q4 stretch)** — students may hardcode `myPet.name`; the stretch wants `this.name`. Worth showing why `this` survives an object rename.
- **The `!` in the Q5 verification** — `hasOwnProperty` returns `false` after deletion; the `!` flips it to `true` to match expected output. Students get confused about which value they're actually printing.
- **`forEach` callback shape (Q6)** — forgetting the callback parameter, or `console.log`-ing outside the loop instead of inside it.
- **Constructor mechanics (Q7)** — omitting `new` (properties silently attach to the wrong `this`), lowercase constructor name, or forgetting `this.x = x` assignments in the body.
- **Q8 logic** — comparing whole objects with `===` instead of comparing the `breed` property; also must remember to define `dog3`. The extension slide shows a deeper `Object.keys`-based equality check — heavier than what Q8 strictly requires, so don't over-scope it.
- **Zero-indexed months (Q10)** — `.getMonth()` returns `8` for September. Reliably trips students up.
- **Git: wrong branch (GitHub task)** — students push/submit the `main` branch link instead of `lesson-3`, so their changes don't show. The `fatal: The current branch...` error on first push includes the exact fix command — tell them to read it. Also watch for `index.html` created in the wrong directory (must be at repo root, same level as `README.md`).
