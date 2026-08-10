# Week 5 Answer Key — HTML Basics

## Setup & submission

- **Not numbered questions** — this week is a single build deliverable: an `index.html` portfolio page written from scratch, wrapped in a full Git workflow. Lessons 5+ run **locally in VS Code** (no more Learns App "RUN" button); students open `index.html` in a browser to view it.
- **Git workflow (from the assignment — walk through this, don't grade content in it):**
  1. Create the lesson branch: `git checkout -b lesson-5` (creates and switches to it).
  2. Open `README.md` and add full name; create `index.html` at the repo root (same level as `README.md`).
  3. After writing the page: `git status` → `git add .` → `git status` again (confirm staged) → `git commit -m "boilerplate and content added"` → `git push`.
  4. First push on a new branch triggers a `fatal: The current branch...` upstream error — the message prints the exact `git push --set-upstream origin lesson-5` command to run.
  5. On GitHub, click **Compare & pull request** → **Create pull request**.
  6. **Submission (non-coding):** paste the **pull request URL** (`https://github.com/user/name-classname/pull/#`) into the submission form — the PR link, not the repo link. Students may self-merge to continue before review.

Evaluate the `index.html` build against the checklist areas below.

---

### Page setup & boilerplate · Objective

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Maria Santiago's Portfolio</title>
    <meta charset="utf-8">
    <meta name="description" content="Maria Santiago's developer portfolio">
  </head>
  <body>
    <!-- visible content -->
  </body>
</html>
```

Check: `<!DOCTYPE html>` on line 1; one `<html>`, `<head>`, `<body>` each, properly nested and closed; `<title>` present inside `<head>`; **at least two** `<meta>` elements inside `<head>`.

**Mentor note:** The single biggest confusion — students put `h1`/visible content inside `<head>`. `<head>` is metadata only; everything users see lives in `<body>`.

### `<head>` metadata · Objective

```html
<title>Maria Santiago's Portfolio</title>
<meta charset="utf-8">
<meta name="description" content="A short description of the page">
<meta name="keywords" content="portfolio, web developer, HTML">
```

Check: `<title>` set to something meaningful (shows in the browser tab); two or more valid `<meta>` tags. Common miss: only one meta, or invalid/guessed meta tags — point to the W3Schools HTML Head resource. `<meta>` is self-closing (no separate closing tag).

### Body content & order · Objective

The `<body>` must contain, **in this exact order**:

```html
<body>
  <h1>Maria Santiago</h1>

  <h2>About</h2>
  <p>A short paragraph about me.</p>

  <h2>Experience</h2>
  <ul>
    <li>Intro to Programming — Code the Dream</li>
    <li>JavaScript, HTML, CSS</li>
    <li>Git &amp; GitHub</li>
  </ul>

  <h2>Connect</h2>
  <ul>
    <li><a href="https://github.com/mariasantiago">GitHub</a></li>
    <li><a href="https://www.linkedin.com/in/mariasantiago">LinkedIn</a></li>
  </ul>
</body>
```

Check: name in an `h1`; "About" `h2` + a `p`; "Experience" `h2` + a `ul` with `li` items; "Connect" `h2` + **at least two** `<a>` links (GitHub and LinkedIn). Content is personal — verify structure/tags, not wording.

**Mentor note:** Watch for `<p/>` (JSX/XML habit) instead of `</p>`; for `<link>` used to make a clickable link (that's `<a href>` — `<link>` is for stylesheets); and for Connect links missing `https://` (bare/relative URLs won't navigate to external profiles).

### Semantic structure (sections + ids) · Objective

Wrap About, Experience, and Connect each in a `<section>` with an `id` matching the section name:

```html
<section id="About">
  <h2>About</h2>
  <p>This is a paragraph about me.</p>
</section>

<section id="Experience">
  <h2>Experience</h2>
  <ul>
    <li>...</li>
  </ul>
</section>

<section id="Connect">
  <h2>Connect</h2>
  <ul>
    <li><a href="https://github.com/...">GitHub</a></li>
    <li><a href="https://www.linkedin.com/in/...">LinkedIn</a></li>
  </ul>
</section>
```

Check: three `<section>` elements; each `id` matches its section name. The assignment's example uses capitalized ids (`id="About"`).

**Mentor note:** `id` values must match exactly (including case) — a mismatch silently breaks next week's CSS styling and anchor-link navigation. Note the `h1` (name) is not required to be inside a section.

### Stretch — additional elements · Subjective

- Optional: images (`<img src alt>`), navigation menus (`<nav>`), or other elements beyond the required set.
- A correct image needs a real file in the same folder (or valid path) **and** an `alt` attribute — `alt` is an easy accessibility miss, and a wrong path shows the broken-image icon (the exact scenario from the lesson's AI-debugging prompt).
- Any well-formed, correctly nested addition counts; don't penalize scope, just correctness of the tags used.
