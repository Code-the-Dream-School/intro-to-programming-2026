# Week 1 — JavaScript Basics and Functions

**Learning objective:** Demonstrate a foundational understanding of JavaScript syntax by practicing problem-solving techniques, manipulating data types and strings, implementing conditional logic, and encapsulating code within reusable functions.

## Key concepts taught

- **Problem-solving process** — the three-step framing (understand → plan → divide) that the course returns to throughout.
- **Variables and declaration** — `let` vs `const` (and why `var` is avoided). Course convention is camelCase; meaningful names are emphasized as a readability/debugging habit.
- **Primitive data types** — strings, numbers (integers, floats, negatives), and booleans. `NaN` is introduced as the result of invalid math, and students see that JS returns it silently rather than throwing.
- **Strings** — concatenation with `+` and with template literals; common string methods (`.length`, index access, `.toUpperCase()`, etc.).
- **Numbers/Math** — arithmetic operators plus `Number` methods (`.toFixed()`) and `Math.random()` / `Math.floor()`.
- **Conditionals** — `if / else if / else`, evaluated top-to-bottom, first-true-block-wins. Comparison operators and `typeof`.
- **Functions** — declaration, `return`, calling, and passing information in via parameters (parameter vs argument distinction).
- **Running & debugging code** — using the Learns App RUN button / VS Code, and `console.log()` as the primary debugging tool. Students are told explicitly that the AI Reviewer *reads* but does not *run* code.
- **GitHub (intro only)** — creating a first public repo with a README. This is just repo creation; the full Git workflow starts in Week 2.

Content is delivered via Odin Project (Foundations, Fundamentals Parts 1–3) *or* Scrimba (JS Deep Dive: Variables/Strings, Types/Conditionals, Functions) — students pick one track. There are also AI Learning Prompts (retrieval practice, predict-then-check, and "ask me 3 questions" style hint-seeking) that model good AI-as-tutor habits rather than answer-generation.

## Brief overview of the assignment

A single JavaScript file with **15 questions**, worked top-to-bottom, plus a GitHub task. Students write code beneath commented instructions and verify with `console.log()`. Rough breakdown:

- **Q1–Q3** — declare string, number, and boolean variables.
- **Q4–Q5** — string concatenation (both `+` and template literals) and basic math, reusing earlier variables.
- **Q6** — string methods (length, first/last letter, uppercase). Stretch: build "weird initials" from last letters of first + last name.
- **Q7–Q8** — conditional logic assigning/logging values; stretches add an `else if` chain and template-literal output.
- **Q9** — round a float to 2 decimals with `.toFixed()`.
- **Q10–Q13** — write functions: no-param return, concatenation, a one-parameter function, and comparing two string lengths.
- **Q14–Q15** — a random-number generator (1–3) feeding a Magic 8 Ball function that returns different strings per value.
- **GitHub task** — create a public `firstname-lastname-classname` repo with a README and submit the link in the URL2 field.

Stretch goals appear throughout and are optional.

## Likely trouble spots

- **`return` vs `console.log()`** — the most common conceptual gap. Students expect a function to print, or they `console.log` *inside* the function instead of returning. Q10–Q15 depend on getting this right.
- **`.toFixed()` returns a string** (Q9) — worth flagging if a later comparison or math step behaves oddly; the rounded value is no longer a number.
- **Parameter vs argument** (Q12–Q13) — students conflate the placeholder with the value passed in. Q13 also invites the empty-string edge case as a stretch.
- **Off-by-one on the random range** (Q14) — `Math.floor(Math.random() * 3)` gives 0–2; they must add 1 to get 1–3. The assignment hints at this but many still miss the shift.
- **Missing space in concatenation** (Q4) — `first + last` → `"JaneDoe"`. Classic, and used deliberately as a debugging teaching moment.
- **String vs number** — e.g. `"42"` is still a string; relevant anywhere math meets quoted values. `NaN` surprises students because there's no error.
- **camelCase / naming** — graded as convention; expect casual capitalization slips.
- **Forgetting to uncomment the sample `console.log` lines** — output looks empty and students think their code is broken.
- **GitHub repo** — some students have never used GitHub; watch for private-instead-of-public repos, missing README, or the wrong link submitted. No Git CLI is expected yet.
