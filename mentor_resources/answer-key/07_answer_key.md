# Week 7 Answer Key — The DOM API

## Setup & submission

- **Git workflow (start), taken from the assignment — verify each step happened:**
  1. Merge last week's open **lesson-6** PR on GitHub (Pull Requests tab → open PR → **Merge pull request** → confirm).
  2. In the terminal, be on `main`: `git checkout main`.
  3. Pull the merged work down: `git pull origin main`.
  4. Create this week's branch: `git checkout -b lesson-7`.
- **File setup:** a `js/` folder at the same level as `index.html`, `readme.md`, and the `css` folder, containing `js/index.js`. `index.html` must link it with a `<script src="js/index.js">` placed **before the closing `</body>` tag** (placement matters — see mentor note).
- **Git wrap-up (end):** `git status` → `git add .` → `git status` (confirm staged) → `git commit -m "js added, created footer and skills"` → `git push`.
- **Submission (non-coding):** open a **Compare & pull request** for `lesson-7` on GitHub and paste the **PR URL** (e.g. `https://github.com/user/repo/pull/#`) into the submission form. Common miss: submitting the repo URL instead of the PR URL. Do not grade these as tasks — just confirm they were done.

---

### Wire up the JavaScript file · Objective

`index.html`, just before `</body>`:
```html
<script src="js/index.js"></script>
```
Check: the `src` is the **relative path** `js/index.js` (not `index.js`), and the tag is at the bottom of `<body>` so elements exist in the DOM before the script runs. Quick diagnostic: a `console.log("JavaScript is connected!")` in `index.js` shows in the browser console.

**Mentor note:** A `<script>` in `<head>` or above the target elements runs before those elements are in the DOM — `querySelector` then returns `null`. Bottom-of-`<body>` placement is what makes the rest of the assignment work.

### Add a footer element · Objective

```js
const footer = document.createElement("footer");
document.body.appendChild(footer);
```
Check: a `<footer>` is created and attached to the page (any valid attach — `document.body.appendChild(footer)` or `document.body.append(footer)`). The assignment explicitly warns that `append`, `appendChild`, `lastChild`, etc. place things differently — watch for the footer landing in an unexpected spot or a `TypeError` from calling a method that doesn't exist on the target (e.g. treating `lastChild` as a method).

**Mentor note:** `appendChild`/`append` add the node as the **last child** of the parent; a common mistake is expecting it to replace or prepend content.

### Insert copyright text in the footer · Objective

```js
const today = new Date();
const thisYear = today.getFullYear();

const footer = document.querySelector("footer");
const copyright = document.createElement("p");
copyright.innerHTML = "Jane Doe " + thisYear;   // name is personal
footer.appendChild(copyright);
```
Expected result: a paragraph in the footer reading the student's name and the **current year** (e.g. `Jane Doe 2026`). Check the **year comes from `getFullYear()`**, not a hardcoded `2026`/`"2024"`. The name value is personal — check the operation, not the literal.

**Stretch — include the `©` symbol via `innerHTML`:**
```js
copyright.innerHTML = "&copy; Jane Doe " + thisYear;   // renders: © Jane Doe 2026
```

**Mentor note:** The `&copy;` entity only renders as `©` when set via `innerHTML`; `textContent` prints the literal string `&copy;`. This is the reason the stretch specifically uses `innerHTML`.

### Create the list of skills · Objective

```js
const skills = ["JavaScript", "HTML", "CSS", "Adobe Photoshop", "GitHub"];

const skillsSection = document.getElementById("skills");      // or querySelector("#skills")
const skillsList = skillsSection.querySelector("ul");         // scoped to the section, not document

for (let i = 0; i < skills.length; i++) {
  const skill = document.createElement("li");
  skill.textContent = skills[i];                              // bracket notation to read each element
  skillsList.appendChild(skill);
}
```
Expected result: an `<li>` per array element rendered under the "Skills" heading. The `skills` array contents are personal — check the pattern (array of strings → loop → create `<li>` → append), not the specific skills.

Check specifically:
- **Scoped query:** `skillsList` is obtained from `skillsSection.querySelector("ul")`, not `document.querySelector("ul")`. Querying the whole document works here by luck but misses the concept the assignment is testing.
- **Complete create→set→append pattern inside the loop:** every `<li>` must be both given content (`textContent`/`innerHTML`) and appended. `createElement` alone attaches nothing.
- Assumes the HTML already has a `<section id="skills">` containing a `<ul>` (built in an earlier week). If either is missing, the selects return `null`.

**Mentor note:** `querySelector` returning `null` is the single most common bug here — the target element doesn't exist yet, the selector is missing its `#`/`.`, or the script ran too early. Have the student `console.log(skillsSection)` / `console.log(skillsList)` to confirm neither is `null`.

### Style the skills list · Subjective

- Correct answers add a **flexbox or grid** layout to the skills list in `index.css` (e.g. `display: flex; flex-wrap: wrap; gap: ...;` on the `<ul>`, or `display: grid` with column tracks). Any layout that clearly uses flexbox or grid to arrange the skills satisfies the requirement.
- The styling target should be the skills `<ul>`/`<li>` (or its container) — check that the flex/grid rule is actually applied to the element holding the generated list, not an unrelated selector.
- Open-ended: spacing, wrapping, columns, bullet removal, and visual treatment are student design choices. A weak answer typically leaves the list as a default vertical bulleted list with no flex/grid applied.
