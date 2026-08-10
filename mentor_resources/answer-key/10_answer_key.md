# Week 10 Answer Key — Open API

## Setup & submission

- **This is a build-to-rubric project, not numbered questions.** Students build a new page — `openapi.html`, `openapi.css`, and `openapi.js` (they can live alongside the existing portfolio files) — that makes **two distinct fetch calls** to a public API of their choice and renders both results to the page. The specific API is student-chosen (Open-Meteo, Swapi.Tech, ARTIC, TheDogAPI/TheCatAPI, API-Sports Soccer), so the data shape and most styling are open-ended; the **two-fetch + navigation + error-handling** requirements are the concrete checks.
- **Runs in the browser** — open `openapi.html` directly or via the **Live Server** VS Code extension. No Learns App "RUN" button.
- **Git workflow (start), taken from the assignment — verify each step happened:**
  1. Merge last week's open **lesson-9** PR on GitHub (Pull Requests tab → open PR → **Merge pull request** → confirm).
  2. In the terminal, be on `main`: `git checkout main`.
  3. Pull the merged work down: `git pull origin main`.
  4. Create this week's branch: `git checkout -b lesson-10` (branches off an up-to-date main).
- **Git wrap-up (end):** `git status` → `git add .` → `git status` (confirm staged) → `git commit -m "added open api page"` → `git push`.
- **Submission (non-coding):** open a **Compare & pull request** for `lesson-10` on GitHub and paste the **PR URL** (e.g. `https://github.com/user/repo/pull/#`) into the submission form. Common miss: submitting the repo URL instead of the PR URL. Do not grade these as tasks — just confirm they were done.

**Mentor note:** The single most common rubric miss is faking the "two calls" — students do one fetch and show/hide two parts of the response, or hit the same URL twice. Confirm **two different endpoints/URLs, two real `fetch()` calls.**

> Note on the assignment file: the assignment's Git text says the merged PR "will update your main branch with the work you did on your **lesson-10** branch" and that `git pull` brings down "your **lesson-10** work" — those should read **lesson-9** (last week's branch). The step being performed is merging the previous PR; treat it as lesson-9. The reference solution below follows the lesson's stated requirements (two endpoints, nav both directions, `.catch()` handling), since the rubric itself lives on an external wiki.

---

### Link the new page from the portfolio · Objective

In the existing `index.html` nav, add a link to the new page:
```html
<nav>
  <ul>
    <li><a href="index.html">Home</a></li>
    <li><a href="openapi.html">Open API</a></li>
  </ul>
</nav>
```
Check: the portfolio's nav gains an `<a href="openapi.html">` pointing at the new file with a correct **relative path** (same folder → bare filename; a subfolder changes the path). The link text is the student's choice.

**Mentor note:** The assignment's own snippet uses `<a href="openapi.html">About</a>` — the "About" label is a copy artifact; any sensible label is fine. What matters is the `href`.

### Nav on the new page (back to home) · Objective

In `openapi.html`:
```html
<nav>
  <ul>
    <li><a href="index.html">Home</a></li>
  </ul>
</nav>
```
Check: the new page has its **own** nav with a working link back to the portfolio home. This is an explicit assignment requirement ("Make sure there is an option to get back to your home page from there!"). Verify the link actually resolves — relative-path typos in either direction are common.

### HTML structure & script wiring · Objective

`openapi.html` — a complete document that links the CSS and JS and provides the containers the JS targets:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Open API</title>
  <link rel="stylesheet" href="openapi.css" />
</head>
<body>
  <nav>
    <ul><li><a href="index.html">Home</a></li></ul>
  </nav>

  <main>
    <div id="view-one"></div>
    <div id="view-two"></div>
    <p id="error"></p>
  </main>

  <script src="openapi.js"></script>
</body>
</html>
```
Check: `<link>` to the CSS, `<script src="openapi.js">` placed **before `</body>`** so the target elements exist when the script runs, and at least one container element per data view that the JS can select.

**Mentor note:** A `<script>` in `<head>` (or above its target elements) runs before those elements are in the DOM, so `getElementById`/`querySelector` returns `null`. Bottom-of-`<body>` placement is what makes the fetch-render code work.

### First fetch call · Objective

One real `fetch()` to a chosen endpoint, drilling into the JSON to a **string** property before rendering. Example using TheDogAPI:
```js
const viewOne = document.getElementById("view-one");

fetch("https://api.thedogapi.com/v1/breeds/1")
  .then((response) => {
    if (!response.ok) {
      throw new Error(`Request failed: ${response.status}`);
    }
    return response.json();
  })
  .then((data) => {
    viewOne.innerHTML = `<h2>${data.name}</h2><p>${data.temperament}</p>`;
  })
  .catch((error) => {
    document.getElementById("error").textContent = "Could not load breed data.";
    console.error(error);
  });
```
Check:
- A genuine `fetch()` to a real endpoint, `.then(res => res.json())`, then the data written to the DOM.
- The rendered value is a **string property**, not a whole object (see mentor note).
- The correct nesting depth for the chosen API (e.g. ARTIC results live under `data.data[...]`; the CFU tested `data.dog.name`). Every API differs, so verify against that API's actual response.

**Mentor note:** `[object Object]` on the page means the student put a nested object into `innerHTML` instead of drilling to a string. Have them `console.log(data)` first to see the shape, then reach the exact field.

### Second fetch call (a DIFFERENT endpoint) · Objective

A second real `fetch()` to a **different** URL/endpoint, rendering into a **different** container:
```js
const viewTwo = document.getElementById("view-two");

fetch("https://api.thedogapi.com/v1/breeds/2")
  .then((response) => {
    if (!response.ok) throw new Error(`Request failed: ${response.status}`);
    return response.json();
  })
  .then((data) => {
    viewTwo.innerHTML = `<h2>${data.name}</h2><p>Bred for: ${data.bred_for || "Unknown"}</p>`;
  })
  .catch((error) => {
    document.getElementById("error").textContent = "Could not load the second view.";
    console.error(error);
  });
```
Check: the URL is **not** the same as the first call, and the data displayed is genuinely different content. Two calls to the same endpoint, or one response split into two `<div>`s, does **not** satisfy the rubric.

**Mentor note (async ordering):** Both calls are asynchronous — the DOM stays empty until each promise resolves, and the two views may populate in either order. Students should not assume view-one is filled before view-two's code runs; each render belongs inside its own `.then()`.

### Error handling · Objective

Every fetch chain must end in a `.catch()` (or `try/catch` with `async/await`) that handles failure, plus a status check so a non-200 response is treated as an error rather than parsed as data:
```js
.then((response) => {
  if (!response.ok) throw new Error(`Request failed: ${response.status}`);
  return response.json();
})
// ...
.catch((error) => {
  document.getElementById("error").textContent = "Something went wrong fetching the data.";
  console.error(error);
});
```
Check: a `.catch()` is present on both chains, and failures surface to the user or console rather than failing silently. A `response.ok` / `response.status` check is what distinguishes this from code that only catches network errors.

**Mentor note:** A keyless or bad-key request (e.g. Marvel) returns a **401/403 with a 200-shaped promise** — `fetch` does not reject on HTTP error status. Without the `response.ok` check, `res.json()` runs on the error body and the student wrongly concludes their parsing is broken. This is exactly the Predict-then-Check exercise from the lesson.

### API key handling (only if the chosen API needs one) · Subjective

- Most listed APIs (Open-Meteo, Swapi.Tech, ARTIC, TheDog/CatAPI) need **no key** — nothing to check. Marvel does.
- If a key is used, for this class it may live as a `const` in `openapi.js`; a correct answer includes it in the request (URL query param or header). A missing key is what produces the 401/403 above.
- Weak answer: hardcodes the key but forgets to actually attach it to the request, then blames the parsing code. (Worth mentioning to students that in real jobs keys go in environment variables, never committed — but that is not required here.)

### Styling the page · Subjective

- A correct answer applies real CSS in `openapi.css` — layout for the two views (e.g. flexbox/grid), and styling consistent enough that the page reads as part of the portfolio.
- The styling should target the actual containers holding the fetched data, not unrelated selectors.
- Open-ended: card layout, spacing, colors, and typography are student choices. A weak answer leaves the two views as unstyled default text stacked on the page.

### Stretch — rich data cards with fallbacks and an image

Instead of plain text, render a card with several fields and `|| "Unknown"` fallbacks, plus an image. Example using ARTIC (whose image URL is built from an `image_id`):
```js
fetch("https://api.artic.edu/api/v1/artworks/27992")
  .then((response) => {
    if (!response.ok) throw new Error(`Request failed: ${response.status}`);
    return response.json();
  })
  .then((body) => {
    const art = body.data;                                  // ARTIC nests under data
    const imgBase = body.config.iiif_url;                   // e.g. https://www.artic.edu/iiif/2
    const imgSrc = art.image_id
      ? `${imgBase}/${art.image_id}/full/400,/0/default.jpg`
      : "";
    viewOne.innerHTML = `
      <article class="card">
        <h2>${art.title || "Untitled"}</h2>
        <p>${art.artist_display || "Unknown artist"}</p>
        <p>${art.date_display || "Date unknown"}</p>
        ${imgSrc ? `<img src="${imgSrc}" alt="${art.title || "artwork"}" />` : ""}
      </article>`;
  })
  .catch((error) => console.error(error));
```
Check: multiple fields displayed with sensible fallbacks for missing data, and the image URL correctly assembled from the API's own fields (ARTIC's IIIF pattern `{iiif_url}/{image_id}/full/{width},/0/default.jpg`). The exact API/fields are the student's — verify the fallbacks and the URL construction against that API's docs.
