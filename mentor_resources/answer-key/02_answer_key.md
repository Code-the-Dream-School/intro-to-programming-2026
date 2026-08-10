# Week 2 Answer Key — JavaScript Loops and Arrays

## Setup & submission

- **One JavaScript file**, worked top-to-bottom, same as Week 1. Instructions live in comments; students write each answer directly below them and run after every question. Lessons 1–4 still run via the **Learns App "RUN" button** (no local execution yet).
- Convention restated in the header: if a question says **"return,"** use `return`; if it says **"print,"** use `console.log`. Test each function with several inputs. Most questions are called inside a `console.log("Q#: ", fn(...))`; **Q1 and Q13 are the exceptions** — they log inside the function and are called directly.
- Submission flow: run and self-check output → run the **AI Reviewer** → correct → submit the code.
- **GitHub task (non-coding):** this week students **clone** the Week 1 repo to their local machine (SSH, not HTTPS). Nothing to submit and no link — just confirm they followed the clone steps. Commit/push come in Weeks 3–4.

---

### Q1 — `repeat` (print inside loop) · Objective
```js
function repeat(num) {
  for (let i = 0; i < num; i++) {
    console.log("Hello World!");
  }
}
repeat(3);
```
Expected: `Hello World!` printed once per iteration (3 times for `repeat(3)`). The `console.log` must be **inside** the loop, and the function is called directly — not wrapped in a `console.log`.

### Q2 — `pyramidCounting` (inclusive sum 0..n) · Objective
```js
function pyramidCounting(num) {
  let total = 0;
  for (let i = 0; i <= num; i++) {
    total += i;
  }
  return total;
}
```
`pyramidCounting(4)` → `10` (0+1+2+3+4). Must **return**.
> Mentor note: off-by-one — the loop must use `<=` so `n` itself is included; `<` gives `6`.

### Q3 — `noVowels` (strip vowels via loop) · Objective
```js
function noVowels(str) {
  let result = "";
  const vowels = "aeiouAEIOU";
  for (let i = 0; i < str.length; i++) {
    if (!vowels.includes(str[i])) {
      result += str[i];
    }
  }
  return result;
}
```
`noVowels("adventurous")` → `dvntrs`. Assignment says assume lowercase; including uppercase in the vowel set (as above) earns the bonus.

### Q4 — `vowelCount` (count vowels, both cases) · Objective
```js
function vowelCount(str) {
  let count = 0;
  const vowels = "aeiouAEIOU";
  for (let i = 0; i < str.length; i++) {
    if (vowels.includes(str[i])) {
      count++;
    }
  }
  return count;
}
```
`vowelCount('I love to code.')` → `6` (I, o, e, o, o, e). Must count the capital `I`.

### Q5 — `numOfOdds` (modulo) · Objective
```js
function numOfOdds(num) {
  let count = 0;
  for (let i = 0; i <= num; i++) {
    if (i % 2 !== 0) {
      count++;
    }
  }
  return count;
}
```
`numOfOdds(15)` → `8` (1,3,5,7,9,11,13,15). Loop must be inclusive (`<=`) so an odd `n` is counted.

### Q6 — `arrayChecker` (empty test, real booleans) · Objective
```js
let empty = [];
let full = ["dream", 19, "code", 24, 180];

function arrayChecker(arr) {
  return arr.length === 0;
}
```
`arrayChecker(empty)` → `true`; `arrayChecker(full)` → `false`. Must return the boolean `true`/`false`, **not** the strings `"true"`/`"false"`. `full` can be any array of strings/numbers.

### Q7 — `getElementAt` (return `null`, not `undefined`) · Objective
```js
function getElementAt(arr, index) {
  if (index < 0 || index >= arr.length) {
    return null;
  }
  return arr[index];
}
```
With `full = ["dream", 19, "code", 24, 180]`: `getElementAt(full, 2)` → `code`; `getElementAt(full, 7)` → `null`.
> Mentor note: an out-of-range index returns `undefined` on its own — the bounds check is required to return an explicit `null`.

### Q8 — `insertInArray` (insert `0` at index 1, no mutation) · Objective
```js
function insertInArray(arr) {
  let newArray = arr.slice();
  newArray.splice(1, 0, 0);
  return newArray;
}
```
With `full = ["dream", 19, "code", 24, 180]`: returns `["dream", 0, 19, "code", 24, 180]`, and logging `full` afterward still shows the **original** `["dream", 19, "code", 24, 180]`.
> Mentor note: reference vs copy — `.slice()` (or spread) must come first; mutating `arr` directly changes the caller's array. `splice(1, 0, 0)` inserts without removing.

### Q9 — `compareArrays` (element-by-element, `===`) · Objective
```js
function compareArrays(arr1, arr2) {
  if (arr1.length !== arr2.length) {
    return false;
  }
  for (let i = 0; i < arr1.length; i++) {
    if (arr1[i] !== arr2[i]) {
      return false;
    }
  }
  return true;
}
```
`compareArrays(full, compare)` → `true` (identical contents); `compareArrays(full, empty)` → `false`; `compareArrays(full, part)` → `false` (partial copy, different length).
> Mentor note: length check must come first, and comparison must use `===` — `1 == '1'` is `true` but the strict compare correctly distinguishes type.

### Q10 — `calculateTotal` (running sum) · Objective
```js
let numbers = [3, 4, 2, 8];

function calculateTotal(arr) {
  let total = 0;
  for (let i = 0; i < arr.length; i++) {
    total += arr[i];
  }
  return total;
}
```
`calculateTotal([3, 4, 2, 8])` → `17`. `numbers` just needs at least 3 numeric elements; check the loop/sum, not the literal.

### Q11 — `findEvens` / `findOdds` (new filtered arrays) · Objective
```js
function findEvens(arr) {
  let evens = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] % 2 === 0) {
      evens.push(arr[i]);
    }
  }
  return evens;
}

function findOdds(arr) {
  let odds = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] % 2 !== 0) {
      odds.push(arr[i]);
    }
  }
  return odds;
}
```
`findEvens([10,2,3,19,7,6,93])` → `[10, 2, 6]`; `findOdds(...)` → `[3, 19, 7, 93]`. Building a new array with `push` satisfies the "NEW array, no mutation" requirement (the original is never touched here).

### Q12 — `makeSquares` (new mapped array) · Objective
```js
function makeSquares(arr) {
  let squares = [];
  for (let i = 0; i < arr.length; i++) {
    squares.push(arr[i] * arr[i]);
  }
  return squares;
}
```
`makeSquares([2, 5, 8])` → `[4, 25, 64]`. Returns a new array; original is unchanged.

### Q13 — `displaySkills` (print each, no return) · Objective
```js
function displaySkills(skills) {
  for (let i = 0; i < skills.length; i++) {
    console.log(skills[i]);
  }
}
const skills = ["JavaScript", "HTML", "CSS", "Adobe Photoshop", "GitHub"];
displaySkills(skills);
```
Prints each skill on its own line. Must **print, not return** — and be called directly, not inside a `console.log`.

### Q14 — `fizzBuzz` (loop 1–15, return array) · Objective
```js
function fizzBuzz() {
  let result = [];
  for (let i = 1; i <= 15; i++) {
    if (i % 3 === 0 && i % 5 === 0) {
      result.push("fizzbuzz");
    } else if (i % 3 === 0) {
      result.push("fizz");
    } else if (i % 5 === 0) {
      result.push("buzz");
    } else {
      result.push(i);
    }
  }
  return result;
}
```
`fizzBuzz()` → `[1, 2, 'fizz', 4, 'buzz', 'fizz', 7, 8, 'fizz', 'buzz', 11, 'fizz', 13, 14, 'fizzbuzz']`.
> Mentor note: the divisible-by-both check must come first — testing `% 3` or `% 5` before it makes `15` come out `"fizz"` instead of `"fizzbuzz"`.

### Q15 — `testScope` (global / function / block) · Subjective
No single output — the structure of the code is the answer. Evaluate:
- **`globalVar`** declared at the top level (outside any function), **`functionVar`** declared inside `testScope`, **`blockVar`** declared inside a `{}` block (e.g. an `if` or loop) within the function. Each is logged from a place where it *is* in scope (all three reachable from inside the block).
- Two **commented-out** log statements that would throw `ReferenceError` if uncommented — e.g. logging `functionVar` from outside the function, and logging `blockVar` from outside its block. These demonstrate the errors without breaking the run.
- Common miss: declaring all three at the top (so nothing is actually out of scope), or using names that don't match where they're declared. Reassure students there is no expected console output here.

Reference structure:
```js
let globalVar = "globalVar";

function testScope() {
  let functionVar = "functionVar";
  if (true) {
    let blockVar = "blockVar";
    console.log(globalVar);
    console.log(functionVar);
    console.log(blockVar);
  }
  // console.log(blockVar);   // ReferenceError — blockVar is block-scoped
}
testScope();
// console.log(functionVar);  // ReferenceError — functionVar is function-scoped
```
