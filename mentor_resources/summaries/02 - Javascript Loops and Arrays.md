# Week 2 — JavaScript Loops and Arrays

**Learning objective:** Manage complex data and automate repetitive tasks by implementing JavaScript arrays and loops, while establishing a local development environment through Git and GitHub version control workflows.

## Key concepts taught

- **Loops** — `for` loops (known iteration count) vs `while` loops (loop until a condition changes). The three parts of a `for` header (initialize / condition / update) and the risk of infinite loops when the update step is missing.
- **Arrays** — ordered collections, zero-based index access, and the property/method distinction (`.length` is a property, no parentheses; methods need `()`).
- **Array methods** — `push`, `pop`, `includes`, and `slice`. `slice()` is emphasized specifically as the way to make a true copy, since assigning an array to a new variable only copies the reference.
- **Loops + arrays together** — the foundational `for (let i = 0; i < arr.length; i++)` pattern for processing each element (sum, filter, transform).
- **Modulo (`%`)** — reintroduced as the tool for even/odd and divisibility checks.
- **Scope** — global vs function vs block scope, and why a variable declared inside a function or `{}` block is not accessible outside it (`let` over `var`).
- **Git & version control** — the distinction between Git (local) and GitHub (remote), installing/setting up Git, SSH keys, and cloning a repo to the local machine. This week covers only the clone portion of the workflow; commit/push come in Weeks 3–4.
- **AI Learning Prompts** — three this week: Retrieval Practice (explain for vs while), Predict-then-Check (array "holes" from out-of-range index assignment), and Scaffold Removal ("ask me 3 questions" hint-seeking for errors).

Content is delivered via Odin Project (Setting Up Git) plus MDN/JavaScript.info for loops and W3Schools/Scrimba for arrays — students work from whichever track they chose in Week 1.

## Brief overview of the assignment

A single JavaScript file with **15 questions**, worked top-to-bottom, plus a GitHub clone task. The header restates the convention: if a question says "return," use `return`; if it says "print," use `console.log`. Rough breakdown:

- **Q1–Q5** — loop-based functions: `repeat` (print inside the loop), `pyramidCounting` (sum 0..n inclusive), `noVowels` (strip vowels via loop), `vowelCount`, `numOfOdds` (modulo). Bonus in Q3 is handling uppercase.
- **Q6–Q9** — array operations: `arrayChecker` (empty test, return real booleans), `getElementAt` (return `null`, not `undefined`, when out of range), `insertInArray` (insert `0` at index 1 into a NEW array without mutating the original), `compareArrays` (element-by-element with `===`, length check first).
- **Q10–Q12** — arrays + loops: `calculateTotal` (running sum), `findEvens` / `findOdds` (new filtered arrays), `makeSquares` (new mapped array).
- **Q13** — `displaySkills`: iterate and print each skill (prints, does not return).
- **Q14** — `fizzBuzz` (no parameters, loop 1–15, return the array). Check divisible-by-both first.
- **Q15** — `testScope`: declare global/function/block variables in the correct place, log each where accessible, and include two commented-out lines that would throw if uncommented. The "answer" is the code structure itself, not an output.
- **GitHub task** — clone the Week 1 repo to the local machine via SSH. Nothing to submit; no commit/push expected yet.

There is no separate stretch-goals section this week; optional extras are the small bonuses noted inline (e.g., Q3 uppercase handling).

## Likely trouble spots

- **`return` vs `console.log` (carries over from Week 1)** — Q1 is deliberately the exception: the `console.log` goes *inside* the loop and the function is called directly, not wrapped in a log. Most other questions want `return`. Q13 is the other print-not-return case. Expect confusion about which is which.
- **Reference vs copy / mutation (Q8, Q11, Q12)** — the biggest array gotcha. Students who skip the comment instructions modify the original array and can't explain why `full` changed. `.slice()` before modifying is the fix; the assignment warns about it explicitly.
- **Off-by-one and inclusive ranges** — Q2 (`pyramidCounting`) must include `n` itself; Q5 (`numOfOdds`) must include the number if odd. Loop bounds (`<` vs `<=`) are the usual culprit. Same theme underlies Q7's index handling.
- **`null` vs `undefined` (Q7)** — an out-of-range index naturally yields `undefined`; the question requires an explicit `null` return, so a bounds check is needed.
- **Strict vs loose equality (Q9)** — the assignment calls out `1 === '1'` is false but `1 == '1'` is true. Students must use `===` and also handle the length-mismatch case before comparing elements.
- **FizzBuzz condition order (Q14)** — checking `% 3` or `% 5` before the divisible-by-both case makes 15 come out as `"fizz"` instead of `"fizzbuzz"`. Code may look right but produce wrong output for 15.
- **Scope demonstration (Q15)** — students often can't tell where to *declare* each variable so its name matches its scope, and struggle to produce the two intentionally-erroring commented lines. Reassure them there is no sample output — the structure is the answer.
- **Git setup / cloning** — first real terminal + Git experience for many. Watch for: choosing HTTPS instead of SSH, unconfigured or missing SSH keys, running `git clone` from the wrong directory, and Windows students needing the separate installer link (the Odin page omits it). Emphasize this is not optional — they need local files to submit work from here on.
