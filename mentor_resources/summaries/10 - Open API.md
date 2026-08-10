# Week 10 — Open API

**Learning objective:** Integrate external data into a web application by performing at least two distinct fetch calls to an open-source (public) API and dynamically displaying the retrieved information on a new, linked HTML page.

## Key concepts taught

- **Open vs. open source** — the distinction between an "open"/public API (free to call, no payment) and open-source code (source publicly available). This week uses free public APIs.
- **Choosing and reading API docs** — students pick one API from a provided list (Open-Meteo, Swapi.Tech, ARTIC, TheDogAPI/TheCatAPI, API-Sports Soccer; slides also mention Marvel). The docs skill: locate the base URL, an endpoint, parameters, and the response format. TheDogAPI/TheCatAPI include ready-to-use fetch examples.
- **Two distinct fetch calls** — the central rubric requirement. Two separate `fetch()` calls to two different endpoints/URLs, each displaying different data. Splitting one response into two views does not count.
- **Reading nested JSON** — digging into the response object (e.g. `data.data[0].title`) to reach the field you want; recognizing `[object Object]` as a signal to go one level deeper.
- **API keys and security** — what a key is, treating it like a password, and (only for this class) storing it as a `const` in the JS file. Reinforced that in real jobs keys live in environment variables, never committed. Most listed APIs need no key; Marvel does.
- **HTTP status on failure** — 401 (no key) / 403 (bad key) vs. 200; check `response.status` when data isn't coming back. Error handling with `.catch()`.
- **Linking the new page** — adding a nav link from the portfolio (`index.html`) to the new page, and a nav link back home.
- **AI Learning Prompts** — a Predict-then-Check prompt (predict the server's response to a keyless request, then verify) and a Scaffold-Removal prompt (ask the AI for 3 guiding questions or high-level hints rather than answers, e.g. for the `[object Object]` problem or file-path/nav structure).

Delivered as a single build-your-own-page project rather than a track split; the Odin/Scrimba track choice is not a factor this week. This lesson is part of the two-part final project (paired with the portfolio), so mentors should point students to the Open API Rubric.

## Brief overview of the assignment

Unlike earlier weeks, this assignment has **no numbered questions** — it is a build-to-rubric project plus a full Git workflow. Students create a new `openapi.html`, `openapi.css`, and `openapi.js` (can live alongside existing portfolio files) that makes two distinct API calls and displays both results.

- **Git setup (start of assignment)** — merge the still-open lesson-9 PR into main, `git checkout main`, `git pull origin main`, then `git checkout -b lesson-10` to branch for this week's work.
- **Build task** — review the Open API Rubric and build a page meeting it: two fetch calls to two endpoints, both results rendered to the DOM, `.catch()` error handling, a nav link from the portfolio to the new page and a nav link back home.
- **Git submit workflow** — `git status` → `git add .` → `git status` → `git commit -m "added open api page"` → `git push`, then open a "Compare & pull request", create the PR, and paste the PR URL into the submission form.
- **Stretch/extension (from slides)** — display rich data cards (multiple fields with `|| "Unknown"` fallbacks) instead of plain text, and add an image (e.g. the ARTIC IIIF image-URL format built from an `image_id` field).

## Likely trouble spots

- **The two-endpoint requirement** — the single most common rubric miss. Students do one fetch and show/hide parts of the response, or hit the same endpoint twice. Confirm two different URLs, two real calls.
- **`[object Object]` on the page** — students insert a nested object into `innerHTML` instead of drilling to a string property. Direct them to `console.log(data)` first and to the array-vs-object structure (e.g. ARTIC's results live under `data.data`).
- **Wrong nesting depth in the JSON** — the CFU (`data.dog.name`, answer B) exists because students skip an object layer or treat an object like an array. Every API's shape differs, so this recurs per student.
- **API key confusion** — students choosing Marvel must sign up for a key; forgetting it yields a 401/403, not data. Watch for students who don't check `response.status` and assume their code is broken.
- **Script tag placement / element IDs** — `getElementById` returning null because the `<script>` runs before the elements exist, or an ID typo between the HTML button and the JS listener.
- **File paths in nav links** — relative-path mistakes in the `<a href>` between `index.html` and `openapi.html` (both directions), especially if CSS/JS are in subfolders.
- **CORS / rate limits** — less likely with ARTIC/Open-Meteo, but some APIs will reject browser calls or throttle; have students test a fetch in the browser console before wiring up the page.
- **Git workflow friction** — this week front-loads a merge + pull + new branch and ends with the full add/commit/push/PR cycle. Watch for students who never merged the lesson-9 PR, who branch off an out-of-date main, or who commit on the wrong branch.
