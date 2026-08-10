# Week 9 — Fetch API

**Learning objective:** Use the Fetch API and asynchronous JavaScript to request data from the GitHub API, handle server responses and potential errors, and dynamically render that data as a styled list within the DOM of their portfolio website.

## Key concepts taught

- **APIs and JSON** — an API as a request/response interface (restaurant-menu analogy); JSON as the common transport format. The key point stressed: JSON travels as a **string**, and `response.json()` parses it into usable JavaScript data.
- **`fetch()`** — a built-in browser function that returns a **Promise**. URL is the required first argument; GET is the default method. Optional second argument (options object) can define `method`, `headers`, and `body`.
- **Promise chaining with `.then()`** — each `.then()` receives the result of the prior step. Standard two-step pattern: first `.then()` returns `response.json()`, second `.then()` works with the parsed data.
- **Error handling** — `.catch()` for network failures, and the crucial distinction that `.catch()` does **not** fire on HTTP error codes (e.g. 404). Students must check `response.ok` and manually `throw` to catch server-side errors.
- **`async` / `await`** — a cleaner equivalent to `.then()` chains; `await` pauses execution *inside* the async function only. Paired with `try...catch` for error handling.
- **Data to DOM** — rendering fetched data with `createElement`, `textContent`, and `appendChild` (reusing loops + DOM skills from Weeks 2 and 7).

Content is delivered via Odin Project (JSON, Working with APIs, Async and Await) *and* Scrimba (Async JS: fetch, Promises with async/await, Catch Errors) — note the lesson tells students to work through **both** tracks this week, not pick one. AI Learning Prompts include Retrieval Practice (explain fetch + the three options components), Predict-then-Check (the `A`/`C`/`B` execution-order exercise), Scaffold Removal ("ask me 3 questions" for debugging errors), and a rubric-comprehension prompt. Students are also directed to review the **Portfolio Final Project rubric** here.

## Brief overview of the assignment

Not numbered — a Git-workflow-driven task list that continues the portfolio site in `index.js` / `index.css`. Grouped as:

- **Git setup** — merge the open lesson-8 PR, `git checkout main`, `git pull origin main`, then `git checkout -b lesson-9`.
- **Creating the fetch** — build a GET request to `https://api.github.com/users/{GITHUB_USERNAME}/repos`; chain a `.then()` that returns the response JSON.
- **Handling JSON data** — chain a second `.then()` to store parsed data in a `repositories` variable and `console.log` it to verify.
- **Handling errors** — chain a `.catch()` so an empty/failed Projects section reports what happened.
- **Displaying repos** — select the projects section by id (`projectSection`), query within it for the `<ul>` (`projectList`), then a `for` loop over `repositories` creating an `<li>` per repo, setting its text to the repo `name`, and appending it.
- **Styling** — add CSS for the projects list including media queries. **Stretch goal:** use flexbox or grid for the list.
- **Git backup + submit** — `git add .`, `git commit -m "API fetch completed"`, `git push`, then open a PR and submit the PR link. Optional: request open-API-project review via the "questions" field.

## Likely trouble spots

- **`.catch()` won't catch a 404** — the single biggest concept. A bad username returns a valid response with `response.ok === false`; without a manual `throw` in the first `.then()`, the error passes silently. Directly tied to the "Handling errors" step.
- **Double-parsing the JSON** — parsing happens once, via `response.json()` in the first `.then()`; the second `.then()` receives already-parsed data. Watch for students reaching for `JSON.parse()` again on data that's already an object.
- **GitHub username is case-sensitive** in the API URL; a typo yields a 404. Suggest testing with `octocat` in the console first to isolate whether the problem is the code or the username.
- **`querySelector` returning `null`** — the two-step DOM selection (section by id, then `ul` within it) fails if the portfolio HTML lacks a `#projects` section or a `<ul>`. Produces "Cannot read properties of null" on `appendChild`. Check the HTML structure.
- **`createElement` alone shows nothing** — element exists in memory but isn't visible until `appendChild`. A common "my loop runs but nothing appears" report.
- **Only ~30 repos appear** — GitHub's API paginates at 30 by default. This is expected, not a bug.
- **Async execution-order intuition** — students expect fetched data to be available on the next line (the Predict-then-Check `A`/`C`/`B` exercise targets this). Watch for code that uses `repositories` before the Promise resolves.
- **Git workflow friction** — this week front-loads a full merge → checkout → pull → branch sequence. Students who never merged the lesson-8 PR, or who branch off an out-of-date main, will carry over stale work or hit conflicts. Verify they're on `lesson-9` branched from an updated `main`.
