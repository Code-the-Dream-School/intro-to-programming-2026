# Week 6 — CSS Basics

**Learning objective:** Apply fundamental CSS concepts (the box model, selectors, and Flexbox) to style a multi-section webpage, implement a navigational header, and manage code changes using a Git branching and pull request workflow.

## Key concepts taught

- **What CSS is** — a style sheet language that supplements HTML: HTML gives structure, CSS gives style.
- **Linking CSS** — external stylesheets via a `<link rel="stylesheet" href="css/index.css">` in the `<head>`; the relative path must be exact.
- **CSS syntax** — the `selector { property: value; }` pattern; curly braces and terminating semicolons.
- **Selectors** — element (`p`), class (`.highlight`), and ID (`#about`). The assignment leans heavily on ID selectors since each section carries an `id`.
- **The cascade / specificity** — which rule wins when two target the same element (element → class → ID → inline). Reinforced by the lesson's predict-then-check exercise.
- **The box model** — content, padding, border, margin; padding is space *inside* the box, margin is space *outside* between elements.
- **Flexbox** — `display: flex` to activate; `gap`, `justify-content`, `flex-direction`, `flex-wrap`, and shorthand like `flex: 1 1 200px` for responsive cards.
- **Navigation** — grouping links in a `<nav>`, using `#id` anchors to jump to on-page sections.
- **Stretch topics** — Google Fonts, images with accessibility attributes, and sticky/fixed positioning (`position: sticky; top: 0; z-index`).

Content is delivered via Odin Project (Intro to CSS, The Cascade, Inspecting HTML/CSS, Box Model, Block & Inline, More CSS Properties, Positioning, Flexbox) *or* Scrimba (HTML & CSS Crash Course plus Learn Flexbox) — students pick one track. There is one **AI Learning Prompt** (predict-then-check on specificity: a blue `p` rule vs a `.red-text` class rule) that models using AI for reasoning-checks rather than answers.

## Brief overview of the assignment

This is an **HTML/CSS assignment, not JavaScript**, building on the portfolio page started in Week 5. There are no numbered questions — it's a checklist of deliverables in five stages, bookended by a full Git branching + PR workflow.

- **Git setup** — merge the open lesson-5 PR, `git checkout main`, `git pull origin main`, then `git checkout -b lesson-6` to start a fresh branch.
- **Create and load stylesheet** — make a `css/` folder alongside `index.html`, create `index.css`, and link it before the closing `</head>`.
- **Write CSS** — required changes: body background color, default text color, custom font family, section spacing (padding/margin), alignment of one section, heading font size/weight/color, styling the Name at top, turning Experience list items into styled blocks, and styling the Connect links. Stretch: Google Fonts, add a photo, social-media icons.
- **Formatting / layout** — add a `<nav>` with internal links to all sections; add new **Skills** and **Projects** sections (each with an `h2` and `id`; Projects gets an empty `<ul>`), left empty for later JS lessons; use **Flexbox** to reformat the Experience section (job title left, dates right, description below) and the Connect section. Stretch: sticky/fixed header.
- **Git wrap-up** — `git status` → `git add .` → `git commit -m "..."` → `git push`, then open a Compare & pull request on GitHub and submit the PR link in the assignment form.

Design specifics beyond the minimums are left to the student.

## Likely trouble spots

- **Stylesheet not applying at all** — wrong `href` path is the single most common setup error. The folder must be `css` and file `index.css`; path is `css/index.css`, not `index.css`. Also check the `<link>` is inside `<head>`.
- **Missing semicolons / braces** — the first thing to check when one rule silently fails.
- **Not saving or refreshing** — students edit CSS but don't save the file or hard-refresh the browser, then think their code is broken.
- **Specificity confusion** — expecting the first-written or element rule to win over a class/ID (directly tied to the predict-then-check exercise).
- **Padding vs margin** — reaching for `padding` when they want space *between* sections (they need `margin`).
- **Flexbox not turning on** — forgetting `display: flex` on the container, or applying flex properties to the items instead of the parent. Experience and Connect layouts both depend on this.
- **Bullets / default list spacing** — forgetting `list-style: none` and `padding: 0` when converting `<ul>` links into a Flexbox row.
- **Nav links that don't jump** — `<a href="#skills">` won't work until a section with the matching `id="skills"` actually exists; students often add the nav before adding the Skills/Projects sections.
- **Sticky nav (stretch)** — adding `position: sticky` but forgetting `top: 0`; also breaks if the nav is nested inside a container with `overflow: hidden`.
- **Git workflow friction** — forgetting to merge/pull last week's work before branching, staying on the `lesson-5` branch instead of creating `lesson-6`, or submitting the wrong PR link. This is the third week of the branch → commit → push → PR cycle but it still trips people up.
