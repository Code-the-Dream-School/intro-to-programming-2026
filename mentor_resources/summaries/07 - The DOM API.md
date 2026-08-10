# Week 7 — The DOM API

**Learning objective:** Manipulate the Document Object Model (DOM) by selecting, creating, and appending HTML elements with JavaScript to dynamically update a web page's content and structure.

## Key concepts taught

- **What the DOM is** — the page represented as a hierarchical tree of nodes (elements, text, comments). Taught with the "family tree" analogy (parents, children, siblings). Emphasis that the DOM is *live* and enables interactivity without a full page reload.
- **Selecting elements** — `querySelector` (returns the **first** match) using CSS selector syntax: `#` for id, `.` for class, bare tag name for elements. `querySelectorAll` (returns all matches) is flagged for awareness but the assignment only needs `querySelector`. Also introduces **scoped querying** — calling `.querySelector()` on an already-selected element (e.g. `skillsSection.querySelector("ul")`) rather than searching the whole document.
- **Creating & inserting elements** — the three-step pattern: `createElement` (in memory) → set content → `appendChild` to attach to the page. Stressed that `createElement` alone does not put anything on the page.
- **Setting content** — `textContent` (plain text) vs `innerHTML` (renders HTML/entities like `&copy;`).
- **Building a list from an array** — `for` loop over an array, creating an `<li>` per element and appending it to a `<ul>`. First time arrays + loops connect to visible page output.
- **Dynamic dates** — `new Date()` and `.getFullYear()` to avoid hardcoding the copyright year.
- **Linking JS to HTML** — `<script src="js/index.js">` placed before the closing `</body>` tag; using the browser console and Live Server extension to verify.
- **(Extension, optional)** event listeners via `addEventListener` and `forEach`, and setting `.style` properties dynamically.

Content is delivered via **Odin Project** (DOM Manipulation and Events; Form Basics) *or* **Scrimba** (What is the DOM, Get Single/Multiple Elements, Creating/Modifying Elements, Dynamically Adding Styles, Events) — students pick one track. A dev-tools video is included. There is one **AI Learning Prompt** (retrieval practice: explain the DOM hierarchy in your own words and have the AI critique your understanding of nodes vs. elements).

## Brief overview of the assignment

Unlike the early weeks, this assignment is **not numbered** — it is a sequence of checkbox tasks that add JavaScript to the student's existing portfolio site. There is a full **Git workflow** wrapped around the coding work.

- **Git setup (start):** merge last week's open lesson-6 PR, `git checkout main`, `git pull origin main`, then `git checkout -b lesson-7`.
- **Wire up JS:** create a `js/` folder and `js/index.js`, and add a `<script src="js/index.js">` tag before `</body>`.
- **Footer via DOM:** append a `<footer>` element to the page (warning given that `append`/`appendChild`/`lastChild` place things differently). Then create `today` (`new Date()`), `thisYear` (`getFullYear`), select the footer (`querySelector`), create a `<p>` (`createElement`), set its content to name + year, and `appendChild` it. **Stretch goal:** include the `&copy;` symbol via `innerHTML`.
- **Skills list:** define a `skills` array of strings, select the skills section by id, scope-query its `<ul>`, then loop over the array creating and appending an `<li>` per skill (bracket notation to read each element).
- **CSS styling:** use flexbox or grid to lay out the skills list.
- **Git wrap-up:** `git status` → `git add .` → `git commit -m "..."` → `git push`, then open a **Compare & pull request** and submit the PR URL in the submission form. Students may self-merge to continue, or review 1:1 with a mentor before merging.

## Likely trouble spots

- **`querySelector` returning `null`** — the single most common bug. Usually the target element doesn't exist in the HTML yet, the selector syntax is wrong (missing `#`/`.`), or the `<script>` runs before the element is in the DOM (wrong script placement). Have students `console.log` the selected variable to check for `null`.
- **`createElement` without `appendChild`** — students create the element but nothing appears because it was never attached. Reinforce the create → set content → append pattern; every skills-loop line maps to one step.
- **Footer placement / choosing the wrong DOM method** — the assignment explicitly warns that `append`, `appendChild`, `lastChild`, etc. behave differently. Watch for the footer landing in an unexpected spot or a runtime error from calling a non-existent method.
- **Scoped query on the skills `<ul>`** — the assignment requires querying `skillsSection` (not `document`) for the `<ul>`. Students commonly query the whole document instead; works here by luck but misses the concept.
- **Script tag path / placement** — `src="index.js"` instead of `js/index.js`, or the script placed before the elements it manipulates. The "JavaScript is connected!" console check is the quick diagnostic.
- **Hardcoding the year** — some will type `2026` or the literal year instead of using `getFullYear()`. The assignment calls this out directly.
- **`innerHTML` vs `textContent` for the `©` symbol** — the copyright stretch needs `innerHTML` for `&copy;` to render; `textContent` would print the literal string `&copy;`.
- **Git workflow friction** — first time doing a full branch → commit → push → PR loop on their own. Watch for students still on `lesson-6`, forgetting to pull main first, forgetting `git add .`, or submitting the repo URL instead of the PR URL.
- **Live reload confusion** — without Live Server, students forget to save/refresh and think their code is broken. Recommend Live Server early.
