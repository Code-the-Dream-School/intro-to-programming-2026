# Week 4 Answer Key — JavaScript Algorithms

## Setup & submission

- **One JavaScript file**, worked top-to-bottom with `console.log` verification after each question. This week emphasizes **algorithmic thinking**: students write pseudocode (plain-language steps as comments) first, then fill code beneath — the tip calculator (Q3) is the worked example.
- Sample `console.log` lines are commented in the file — students uncomment them (and add their own test calls) to see output.
- Submission flow: run the code and self-check output → run the **AI Reviewer** → correct → submit the code.
- **GitHub task (non-coding):** this week completes the full collaborative Git cycle. Students merged their **lesson-3 branch into `main`**, then confirm `main` contains the Lesson 3 `index.html`. The **link to the repo's main branch** goes in the "second link"/URL2 field of the submission form. No code — just confirm the merge happened and the link points to `main`.

---

### Q1 — `convertTemp` (C→F) · Objective
```js
function convertTemp(celsius) {
  return celsius * 9 / 5 + 32;
}
console.log("Q1 convertTemp: ", 0, convertTemp(0));   // 0 32
console.log("Q1 convertTemp: ", 100, convertTemp(100)); // 100 212
console.log("Q1 convertTemp: ", 37, convertTemp(37));   // 37 98.6
```
Check the formula `C * 9/5 + 32`. `0 → 32`, `100 → 212`, `-40 → -40`. Must **return**, not log inside. Several test calls expected.

### Q2 — `reverseString` (for loop) · Objective
```js
function reverseString(str) {
  let reversed = "";
  for (let i = str.length - 1; i >= 0; i--) {
    reversed += str[i];
  }
  return reversed;
}
console.log("Q2 reverseString: ", "HelloWorld", reverseString("HelloWorld")); // dlroWolleH
console.log("Q2 reverseString: ", "", reverseString(""));                     // "" (empty)
```
Expected: `HelloWorld → dlroWolleH`, `"" → ""`. Must use a **for loop** (the assignment requires it, so `split().reverse().join()` doesn't satisfy the task even though it works).

**Mentor note:** loop must start at `str.length - 1` and count down to `>= 0`; starting at `str.length` prepends `undefined`.

### Q3 — `tipCalculator` · Objective
```js
function tipCalculator(billTotal, tipPercentage) {
  return billTotal + billTotal * tipPercentage;
}
console.log("Q3 tipCalculator: ", tipCalculator(20, 0.20)); // 24
```
Expected: `tipCalculator(20, .20) → 24`. This is the pseudocode example — comments describing the steps should remain above the code.

**Mentor note:** must return the **total bill** (`bill + bill * pct`), not just the tip (`bill * pct` would give `4`).

### Q4 — `multiplyThese` · Objective
```js
let num1 = 10;
let num2 = 10;
function multiplyThese(a, b) {
  return a * b;
}
console.log("Q4: ", num1, num2, multiplyThese(num1, num2)); // 10 10 100
```
Check the operation (`*`), not the literal values — `num1`/`num2` are student-chosen integers.

### Q5 — `getAverage` · Objective
```js
function getAverage(a, b) {
  return (a + b) / 2;
}
console.log("Q5 getAverage: ", 3, 6, getAverage(3, 6)); // 4.5
```
Expected: `getAverage(3, 6) → 4.5`.

**Mentor note:** the assignment's "use `2.0`" tip is a red herring in JS — division is always floating-point, so `/2` and `/2.0` behave identically. Don't dock for either.

### Q6 — `isPrime` · Objective
```js
function isPrime(num) {
  if (num < 2) return false;              // 0 and 1 are not prime
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}
console.log("Q6 isPrime: ", 12, isPrime(12)); // false
console.log("Q6 isPrime: ", 13, isPrime(13)); // true
```
Expected: `12 → false`, `13 → true`, `0 → false`, `1 → false`, `2 → true`. Test cases should include 0 and 1.

**Mentor note:** two classic bugs — forgetting the `num < 2` guard (0/1 wrongly report prime), and looping to `num` instead of `√num` (correct result, just slow — acceptable but worth mentioning).

### Q7 — `getPrimesUpTo` · Objective
```js
function getPrimesUpTo(number) {
  let primes = [];
  for (let i = 2; i <= number; i++) {
    if (isPrime(i)) primes.push(i);
  }
  return primes;
}
console.log("Q7 getPrimesUpTo: ", 13, getPrimesUpTo(13)); // [2, 3, 5, 7, 11, 13]
```
Expected: `getPrimesUpTo(13) → [2, 3, 5, 7, 11, 13]`. Must **reuse `isPrime`** from Q6 and be inclusive of the input ("up to and including"). A wrong array here usually means a Q6 bug.

### Q8 — `calculateAverage` · Objective
```js
function calculateAverage(scores) {
  let sum = 0;
  let count = 0;
  for (let i = 0; i < scores.length; i++) {
    if (scores[i] >= 0 && scores[i] <= 100) {
      sum += scores[i];
      count++;
    }
  }
  if (count === 0) return 0;   // guard against divide-by-zero
  return sum / count;
}
console.log("Q8 calculateAverage: ", calculateAverage([90, 80, 85])); // 85
```
Expected: `[90, 80, 85] → 85`. Must **ignore out-of-range values** (below 0 or above 100) and **not error** on an empty array or an array with no valid scores.

**Mentor note:** the key edge case — after filtering, the denominator can be 0. Students who divide by `scores.length` (unfiltered) or skip the guard get `NaN`.

### Q9 — `getLetterGrade` · Objective
```js
function getLetterGrade(average) {
  if (average >= 90) return "A";
  if (average >= 80) return "B";
  if (average >= 70) return "C";
  if (average >= 60) return "D";
  return "F";
}
console.log("Q9 getLetterGrade: ", getLetterGrade(95)); // A
```
Expected: `95 → A`, `85 → B`, `75 → C`, `65 → D`, `59 → F`. Boundaries: `90 → A`, `80 → B`, `70 → C`, `60 → D`.

### Q10 — `passed` · Objective
```js
function passed(letterGrade) {
  return letterGrade === "A" || letterGrade === "B" || letterGrade === "C";
}
console.log("Q10 passed('A'): ", passed("A")); // true
```
Expected: `A/B/C → true`, `D/F → false`. Any unexpected input (e.g. `"Z"`, `undefined`) should return `false` — the equality checks handle this naturally, so no separate error branch is required.

### Q11 — `printClassResult` · Objective
```js
function printClassResult(className, student, scores) {
  let average = calculateAverage(scores);
  let letterGrade = getLetterGrade(average);
  let didPass = passed(letterGrade) ? "yes" : "no";
  return `${className} - Student: ${student}, Average: ${average}, Grade: ${letterGrade}, Passed: ${didPass}`;
}
console.log("Q11: ", printClassResult("History 101", "Yuki Kawamura", [60, 70, 85, 87]));
// History 101 - Student: Yuki Kawamura, Average: 75.5, Grade: C, Passed: yes
```
Expected: `History 101 - Student: Yuki Kawamura, Average: 75.5, Grade: C, Passed: yes`.

**Mentor note:** must **compose the three earlier functions**, not re-implement the logic inline. Map the boolean to `yes`/`no`. If an average comes out as a long decimal (e.g. `97.6666…`), `average.toFixed(1)` is the intended optional cleanup — `[60,70,85,87]` averages to exactly `75.5`, so no rounding is needed for the sample.

### Q12 — `sayHello` passed to `setTimeout` · Objective
```js
function sayHello() {
  console.log("Q12: Hello!");
}
setTimeout(sayHello, 1000); // logs after ~1 second
```
Expected (after ~1s): `Q12: Hello!`. Must pass the function **by name without parentheses** (`sayHello`), not `sayHello()`.

**Mentor note:** the core lesson — `sayHello()` runs immediately and passes its return value (`undefined`) to `setTimeout`; `sayHello` passes the function itself to be run later.

### Q13 — `buttonPushed` · Objective
```js
function buttonPushed() {
  console.log("Q13, Q14: The button was pushed!");
}
buttonPushed();
```
Expected: `Q13, Q14: The button was pushed!`. Simple function that logs inside itself.

### Q14 — `simulateButtonPush` (callback) · Objective
```js
function simulateButtonPush(callback) {
  callback();
}
simulateButtonPush(buttonPushed); // Q13, Q14: The button was pushed!
```
Expected: `Q13, Q14: The button was pushed!`. `simulateButtonPush` receives a function and **calls it** (`callback()` with parentheses, inside). It's passed `buttonPushed` **without** parentheses. Same pattern as Q12 with `setTimeout`.
