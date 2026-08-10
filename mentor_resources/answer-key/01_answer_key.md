# Week 1 Answer Key — JavaScript Basics and Functions

## Setup & submission

- **One JavaScript file**, worked top-to-bottom. Students write each answer directly below the commented instructions and run after every question. Lessons 1–4 run via the **Learns App "RUN" button** (no local environment yet).
- Sample `console.log` lines in the file are commented out — students must **uncomment them** (remove `//`) to see output.
- Submission flow: run the code and self-check output → run the **AI Reviewer** → correct → submit the code.
- **GitHub task (non-coding):** a public repo named `firstname-lastname-classname`, initialized with a README. The repo **link** goes in the "second link"/URL2 field of the submission form. No code; just confirm it exists, is public, and has a README.

---

### Q1 — String variables · Objective
```js
let firstName = "Jane";
let lastName = "Doe";
let country = "Canada";
```
Check: three variables, correct names, **string** values, camelCase. Values are personal.

### Q2 — Number variables · Objective
```js
let floatingPoint = 3.14;
let integer = 5;
let negative = -6;
```
Check: a decimal, a whole number, and a negative.

**Stretch — `bigNumber` (16+ digits):**
```js
let bigNumber = 12345678901234567890;
console.log(bigNumber); // 12345678901234567000  ← does NOT match what was typed
```
The teaching point: JS numbers lose precision beyond ~15–16 significant digits. A correct student notices the logged value differs from what they typed.

### Q3 — Boolean variables · Objective
```js
let myTrueVariable = true;
let myFalseVariable = false;
```
Check: one `true`, one `false`; names are student choice but should be meaningful.

### Q4 — String concatenation · Objective
```js
let firstHelloString = "Hello, my name is " + firstName + " " + lastName + " and I was born in " + country + ".";
let secondHelloString = `Hello, my name is ${firstName} ${lastName} and I was born in ${country}.`;
```
Expected output (both identical): `Hello, my name is Jane Doe and I was born in Canada.`
Common miss: no spaces around the `+` variables → `JaneDoe`.

### Q5 — JavaScript math · Objective
```js
let subtractionVariable = floatingPoint - integer; // 3.14 - 5  = -1.86
let additionVariable = integer + negative;         // 5 + (-6)  = -1
```
Check the **operation**, not the literal number — results depend on the student's Q2 values. (Note: the assignment's printed sample output `2.87 / 5` doesn't correspond to Q2's sample values; students' own numbers will differ.)

### Q6 — String methods · Objective
```js
let nameLength = firstName.length;                  // 4
let firstInitial = firstName[0];                    // "J"   (charAt(0) also fine)
let lastInitial = firstName[firstName.length - 1];  // "e"
let capitalize = firstName.toUpperCase();           // "JANE"
```

**Stretch — `weirdInitials`** (last letters of first + last name, capitalized):
```js
let weirdInitials = (firstName[firstName.length - 1] + lastName[lastName.length - 1]).toUpperCase();
```
"Sally Smith" → `YH`; "Jose Rodriguez" → `EZ`.

### Q7 — Conditional (boolean result) · Objective
```js
let answer;
if (integer > 10) {
  answer = true;
} else {
  answer = false;
}
```
`typeof answer` → `boolean`. Result depends on their Q2 `integer`.

**Stretch — `stretchAnswer`:**
```js
let stretchAnswer;
if (integer < 10) {
  stretchAnswer = "less than";
} else if (integer === 10) {
  stretchAnswer = "equal to";
} else {
  stretchAnswer = "greater than";
}
```
`typeof stretchAnswer` → `string`.

### Q8 — Conditional (logging) · Objective
```js
let age = 25;
if (age <= 30) {
  console.log("Q8: ", "Age is just a number!");
} else {
  console.log("Q8: ", "Young at heart!");
}
```
Exactly one line should log. Boundary: `age === 30` → "Age is just a number!".

**Stretch (template literal with name):**
```js
if (age <= 30) {
  console.log(`Q8: ${firstName}, age is just a number!`);
} else {
  console.log(`Q8: ${firstName}, you're young at heart!`);
}
```

### Q9 — `toFixed()` rounding · Objective
```js
let exampleNum = 21.4572;
exampleNum = exampleNum.toFixed(2); // "21.46"
```
Expected: `21.46`. **Important:** `toFixed()` returns a **string**, not a number — worth flagging even though it prints correctly.

### Q10 — Function returning a string · Objective
```js
function assignMessageString() {
  let message = "Welcome to Code the Dream!";
  return message;
}
```
`assignMessageString()` → `Welcome to Code the Dream!`. Must **return**, not `console.log` inside.

### Q11 — Function combining strings · Objective
```js
function combineStrings() {
  let string1 = "Good";
  let string2 = "Evening";
  return string1 + " " + string2;
}
```
`combineStrings()` → `Good Evening`. Watch for the missing space.

### Q12 — Function with a parameter · Objective
```js
function useParams(str) {
  return str.toUpperCase();
}
```
`useParams("hello")` → `HELLO`.

### Q13 — Compare two string lengths · Objective
```js
let word1 = "Code";
let word2 = "Dream";
function biggestStringLength(word1, word2) {
  if (word1.length >= word2.length) {
    return word1.length;
  } else {
    return word2.length;
  }
}
```
`biggestStringLength("Code", "Dream")` → `5`. Equal lengths return that length.
**Stretch (empty string):** `biggestStringLength("", "Dream")` → `5`; both empty → `0`. No error — a valid result.

### Q14 — Random number 1–3 · Objective
```js
function returnRandomNum() {
  return Math.floor(Math.random() * 3) + 1;
}
```
Returns `1`, `2`, or `3`. Common error: omitting `+ 1` (yields 0–2), or misplacing it as `Math.floor(Math.random() * 3 + 1)` — that one actually still works, but `* 4` or `Math.ceil` would not.

### Q15 — Magic 8 Ball · Objective
```js
function shakeMagic8Ball() {
  let num = returnRandomNum();
  if (num === 1) return "It is certain";
  if (num === 2) return "Perhaps";
  return "Absolutely not"; // num === 3
}
```
Must **reuse** `returnRandomNum()` from Q14. Each of the three strings should be reachable across multiple calls.
