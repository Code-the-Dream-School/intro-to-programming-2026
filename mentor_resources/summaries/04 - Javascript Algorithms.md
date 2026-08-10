# Week 4 — JavaScript Algorithms

**Learning objective:** Define and apply algorithmic thinking through pseudocode, implement flexible JavaScript logic using callback functions, and complete the collaborative Git workflow by creating and merging a pull request.

## Key concepts taught

- **Algorithms** — an algorithm as an explicit, ordered set of steps; framed with everyday analogies (recipes, GPS, ATM, making tea). Core insight: the computer follows every step literally and assumes nothing, so order and completeness matter.
- **Pseudocode** — planning steps in plain language before writing code. Course workflow: write the steps as comments first, then fill code beneath each; the pseudocode then survives as the comments. Demonstrated with the tip calculator (Q3).
- **Decomposition** — breaking a large problem into small single-purpose functions that combine into one orchestrating function (the Q8–Q11 grade calculator is the worked example: `calculateAverage` → `getLetterGrade` → `passed` → `printClassResult`). Each small function is independently testable.
- **Functions as values / callbacks** — a function is a value that can be stored, passed, and run later. Passing a function *without* parentheses (`sayHello`, not `sayHello()`) vs. calling it. Demonstrated with `setTimeout` and a `simulateButtonPush(callback)` pattern. Callbacks are previewed as the foundation for later event handling and async work.
- **Git — pull requests (full collaborative workflow completes here)** — creating a PR from the lesson-3 branch, submitting the PR link, merging into `main` on GitHub, then `git checkout main` + `git pull origin main` to sync local. The lesson includes a "Full Cycle" reference (checkout → pull → branch → add → commit → push → PR → merge → pull) that students reuse from Week 5 on.
- **Tracks** — content delivered via Odin Project *or* Scrimba (students pick one). Two **AI Learning Prompts**: retrieval practice (explain an algorithm and get feedback) and scaffold-removal ("ask me 3 questions" to debug a `git pull` merge conflict rather than get the answer).

## Brief overview of the assignment

A single JavaScript file with **14 numbered questions**, worked top-to-bottom with `console.log` verification, plus a GitHub task. Grouping:

- **Q1–Q5 — standalone algorithm functions:** `convertTemp` (C→F), `reverseString` (must use a `for` loop and handle empty string), `tipCalculator` (the pseudocode example), `multiplyThese`, `getAverage` (note about integer vs float division, suggests using `2.0`).
- **Q6–Q7 — primes:** `isPrime` (handle 0 and 1 as non-prime; check divisors up to √n), then `getPrimesUpTo` which *reuses* `isPrime` inside a loop and returns an array.
- **Q8–Q11 — grade calculator (the week's biggest task):** `calculateAverage` (ignore out-of-range scores, guard against divide-by-zero on empty array), `getLetterGrade` (A–F scale, optional `.toFixed()` rounding), `passed` (true for A/B/C, handle bad input), and `printClassResult` which composes all three into a formatted output string.
- **Q12–Q14 — callbacks:** `sayHello` passed to `setTimeout` (Q12), `buttonPushed` (Q13), and `simulateButtonPush` which takes and calls a function passed to it (Q14).
- **GitHub task:** confirm `main` contains the Lesson 3 `index.html` after merging the lesson-3 branch, then submit the link to the repo's main branch in the second assignment-link field. (No code.)

Stretch/edge-case testing is expected throughout (empty inputs, 0, 1, invalid values). Q6/isPrime is flagged as the extension challenge.

## Likely trouble spots

- **`return` vs `console.log`** — carries over from Week 1 and still bites. Every function Q1–Q11 must *return*; students who log inside instead will break the composition in Q11.
- **Q2 reverseString loop direction** — must start at `str.length - 1` and count down to `>= 0`. Off-by-one (starting at `.length`) yields `undefined` as the first character. Empty string must return `""` without crashing.
- **Q3 tipCalculator** — students sometimes return just the tip (`billTotal * tipPercentage`) instead of the *total* bill (`billTotal + billTotal * tipPercentage`). For `tipCalculator(20, .20)` the expected return is `24`, not `4`.
- **Q5 getAverage** — the integer/float note is a red herring in JS (division is always float); students may overthink the `2.0` suggestion.
- **Q6 isPrime** — the classic traps: forgetting that 0 and 1 are *not* prime, and looping all the way to `num` instead of `Math.sqrt(num)`. Watch for `num < 2` guard.
- **Q7 getPrimesUpTo** — depends entirely on a correct Q6; a subtle isPrime bug surfaces here as a wrong array. Also "up to and including" the input.
- **Q8 calculateAverage** — divide-by-zero on an empty array (or array with no valid scores) is the explicit edge case; students forget to guard the denominator after filtering out-of-range values.
- **Q11 printClassResult** — most students try to cram everything into one function instead of calling the three earlier ones; also matching the exact output string format (`Average: 75.5, Grade: C, Passed: yes`) and mapping the boolean to yes/no.
- **Q12/Q14 callbacks — parentheses** — the single biggest conceptual hurdle: passing `sayHello`/`buttonPushed` vs. calling `sayHello()`. Passing the *result* (undefined) instead of the function is the common error.
- **Git PR + merge + pull** — first time doing the full cycle. Watch for: opening a PR before pushing the branch, submitting the wrong link, "no upstream branch" needing `--set-upstream`, and forgetting the final `git pull origin main` on `main` (which leaves next week's starting point stale). The scaffold-removal AI prompt is aimed exactly at merge-conflict/pull errors.
