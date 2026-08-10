# Week 9 Answer Key — Fetch API

## Setup & submission

- **Git setup (do first):** merge the open **lesson-8** PR on GitHub (Pull Requests tab → open PR → "Merge pull request" → confirm), then in the terminal: `git checkout main` → `git pull origin main` → `git checkout -b lesson-9`. This branches lesson-9 off an up-to-date main so no stale work carries over.
- **Git backup + submit (do last):** `git status` → `git add .` → `git status` → `git commit -m "API fetch completed"` → `git push`. Then on GitHub click "Compare & pull request" → "Create pull request", copy the PR URL, and paste it into the submission form. **Non-coding — just confirm the PR link exists and targets the lesson-9 branch.** Open-API-project work-in-progress can optionally be flagged in the "questions" field for the reviewer.
- **Runs in the browser now** (not the Learns App) — the fetch and DOM work must be viewed via a live server / browser refresh with the console open.

---

### Creating the fetch · Objective
```js
fetch(`https://api.github.com/users/octocat/repos`)
  .then((response) => {
    if (!response.ok) {
      throw new Error(`Request failed: ${response.status}`);
    }
    return response.json();
  })
```
Check: `fetch` called with the GitHub repos URL using **their own** username (case-sensitive), no options object (GET is the default), and a first `.then()` that **returns** `response.json()`. The `response.ok` check + `throw` is not required by the assignment's wording but is the correct pattern taught in the lesson — credit it, and see the mentor note below.

Mentor note: `.catch()` does **not** fire on a 404 (bad username) — the response comes back with `response.ok === false`; only a manual `throw` in the first `.then()` routes it to `.catch()`.

### Handle your JSON data · Objective
```js
  .then((repositories) => {
    console.log(repositories);
    // ... DOM rendering happens here (see below)
  })
```
Check: the second `.then()` receives the **already-parsed** data and stores it as `repositories` (the callback parameter itself is the variable). Then `console.log(repositories)` to verify an array of repo objects appears in the console.

Mentor note: the data is already parsed by `response.json()` in the first `.then()` — calling `JSON.parse()` on it again is the classic double-parse error and will throw.

### Handling errors · Objective
```js
  .catch((error) => {
    console.error("Could not load repositories:", error);
  });
```
Check: a `.catch()` chained to the end that receives the error and reports it (console message, or ideally a visible message in the empty Projects section). Any reasonable handling of the error argument is fine.

### Display Repositories in List · Objective
```js
const projectSection = document.getElementById("projects");
const projectList = projectSection.querySelector("ul");

for (let i = 0; i < repositories.length; i++) {
  const project = document.createElement("li");
  project.textContent = repositories[i].name;
  projectList.appendChild(project);
}
```
Check: `projectSection` selects the projects section **by id**; `projectList` queries **within `projectSection`** (not `document`) for the `<ul>`; a `for` loop from index 0 creates an `<li>` per repo, sets its text to `repositories[i].name` (bracket notation + `.name`), and appends it. This block lives inside the second `.then()` so `repositories` is defined when it runs.

Mentor note: `createElement` alone renders nothing — the `<li>` is only visible after `appendChild`. If `querySelector` returns `null` ("Cannot read properties of null"), the portfolio HTML is missing a `#projects` section or its `<ul>`.

### Style your Repository List · Subjective
- A correct answer adds real CSS targeting the projects list/items in `index.css`, with at least one **media query** adjusting the layout at a breakpoint.
- Styling choices (spacing, colors, list layout) are open — evaluate that it's applied and responsive, not the specific aesthetic.
- Common miss: styling only the desktop view with no media query, or targeting a selector that doesn't match the generated `<li>` elements.

**Stretch — flexbox or grid:**
```css
#projects ul {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  list-style: none;
  padding: 0;
}
/* or: display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); */
```
Check: the list uses `display: flex` (with `flex-wrap`) or `display: grid` to lay repos out as a multi-column/wrapping layout rather than a plain vertical list.

---

**Async/await note (context, not required):** the lesson teaches `async`/`await` + `try...catch` as an equivalent to the `.then()` chain. The assignment explicitly asks for the `.then()`/`.catch()` form, so that's the expected solution — but a student who correctly implements the whole flow with `async`/`await` should get full credit.
