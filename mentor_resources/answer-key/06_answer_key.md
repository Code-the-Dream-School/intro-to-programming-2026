# Week 6 Answer Key — CSS Basics

## Setup & submission

- **This is an HTML/CSS assignment, not JavaScript.** It builds on the portfolio `index.html` started in Week 5 — students add an external stylesheet, style the page, add navigation, and add two new (empty) sections.
- **Git workflow (do first):**
  1. Merge the open **lesson-5** pull request on GitHub (Pull Requests tab → open PR → **Merge pull request** → confirm). This updates `main` with last week's work.
  2. In the terminal, switch to main: `git checkout main`.
  3. Pull the merged work down: `git pull origin main`.
  4. Create this week's branch: `git checkout -b lesson-6`.
- **Git wrap-up (do last):** `git status` → `git add .` → `git commit -m "..."` → `git push`, then open a **Compare & pull request** on GitHub.
- **Submission (non-coding):** the **lesson-6 PR link** (`https://github.com/<user>/<repo>/pull/#`) goes in the submission form. Confirm it points to the lesson-6 branch, not lesson-5.
- **Files:** a new `css/` folder sits **at the same level as** `README.md` and `index.html`, containing `index.css`. Grade the CSS and the HTML changes below; don't grade the Git steps or PR link as questions.

---

### Create & load stylesheet · Objective

Folder `css/` beside `index.html`, containing `index.css`, linked before the closing `</head>`:

```html
<head>
  <!-- ...existing head content... -->
  <link rel="stylesheet" href="css/index.css" />
</head>
```

Check: `rel="stylesheet"`, `href="css/index.css"` (relative path, **not** `index.css` or `/css/index.css`), and the `<link>` is inside `<head>`.

**Mentor note:** A wrong `href` path is the single most common failure — the page loads but no styles apply. If nothing is styling, check this line and the folder/file names first.

---

### Write CSS — required styling · Objective

The design is student-chosen, but the assignment names a specific minimum set of changes. Grade for **presence of each required change**, not for aesthetic taste. Reference solution showing every required rule:

```css
body {
  background-color: #f4f1ea;   /* required: page background color */
  color: #2b2b2b;              /* required: default text color */
  font-family: Arial, Helvetica, sans-serif;  /* required: custom font family */
}

section {
  margin: 2rem 0;              /* required: spacing BETWEEN sections (margin) */
  padding: 1rem;               /* padding = space inside the box */
}

#about {
  text-align: center;          /* required: alignment change on one section */
}

h1, h2 {
  font-size: 1.75rem;          /* required: heading size */
  font-weight: 700;            /* required: heading weight */
  color: #1a3d5c;              /* required: heading color */
}

/* required: transform the Name at the top */
#name, header h1 {
  font-size: 2.5rem;
  letter-spacing: 2px;
  text-transform: uppercase;
}

/* required: Experience items as styled blocks */
#experience li {
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 6px;
  padding: 1rem;
  margin-bottom: 0.75rem;
}

/* required: style the Connect links */
#connect a {
  color: #1a3d5c;
  text-decoration: none;
  font-weight: bold;
}
#connect a:hover {
  text-decoration: underline;
}
```

Required checklist (all must be present somewhere): body background color, default text color, custom font family, section spacing, alignment of one section, heading size **and** weight **and** color, restyled Name, Experience items as blocks, styled Connect links.

**Mentor note:** For space *between* sections students need `margin`, not `padding` — a common mix-up worth confirming they understand.

**Stretch — Google Fonts:** an `@import` in the CSS *or* a `<link>` to `fonts.googleapis.com` in the HTML, then the font used in `font-family` with a fallback:
```css
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
body { font-family: 'Poppins', sans-serif; }
```

**Stretch — photo:** an `<img>` with a meaningful `alt` attribute (accessibility was explicitly called out). Flag a missing or empty `alt`.

**Stretch — social icons:** link text replaced with image/icon; each icon still needs accessible text (`alt`, or `aria-label` on the link).

---

### Formatting — nav + new sections (HTML) · Objective

A `<nav>` with internal (`#id`) links to every section, plus two new empty sections. Reference:

```html
<nav>
  <a href="#about">About</a>
  <a href="#experience">Experience</a>
  <a href="#skills">Skills</a>
  <a href="#projects">Projects</a>
  <a href="#connect">Connect</a>
</nav>

<section id="skills">
  <h2>Skills</h2>
</section>

<section id="projects">
  <h2>Projects</h2>
  <ul></ul>   <!-- empty; filled by API/JS in a later lesson -->
</section>
```

Check: `<nav>` present with a link per section; each `href="#..."` matches an existing `id`; **Skills** section has an `h2` + `id` (may be empty); **Projects** section has an `h2` + `id` **and** an empty `<ul>`. Both sections stay empty of content for now.

**Mentor note:** Nav links only "jump" if the target `id` exists — students who add the nav before adding the Skills/Projects sections will have dead links to those two.

---

### Formatting — Flexbox layout (CSS) · Objective

Reformat **Experience** and **Connect** with Flexbox. Reference for the suggested Experience layout (title left, dates right, description below):

```css
#experience li {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;  /* title left, dates right */
  align-items: baseline;
}
#experience .job-title { font-weight: bold; }
#experience .job-desc {
  flex-basis: 100%;                /* forces description onto its own row below */
}

#connect ul {
  display: flex;
  gap: 1rem;
  list-style: none;   /* drop bullets */
  padding: 0;         /* drop default list indent */
}
```

Check: `display: flex` is on the **container** (the parent), not the individual items; Experience is no longer a plain vertical list; Connect links/icons sit in a Flexbox row.

**Mentor note:** The two most common Flexbox misses — forgetting `display: flex` entirely (nothing changes), and forgetting `list-style: none; padding: 0;` when converting a `<ul>` into a row (leftover bullets and indent).

**Stretch — sticky header:**
```css
nav {
  position: sticky;
  top: 0;          /* required — sticky does nothing without an offset */
  z-index: 10;
  background-color: #fff;
}
```
Check that `top: 0` is present; `position: sticky` alone has no effect. Also breaks if an ancestor has `overflow: hidden`.

---

### Overall design (creativity) · Subjective

The assignment invites students to go beyond the minimum rubric.

- A strong submission has a coherent, readable result — consistent colors, legible contrast, and sensible spacing — not just each required property technically present.
- Reasonable to see a wide range of styles; there is no single "correct" look. Grade whether the required changes are visibly in effect, not personal taste.
- Common miss: rules written but not applied because of a selector typo, a missing semicolon/brace, or the file not saved/refreshed — a rule that silently does nothing usually means one of these, not a misunderstanding of the property.
