# Week 5 — HTML Basics

**Learning objective:** Construct a functional web page from scratch by writing semantic HTML boilerplate, organizing content with structural elements and attributes, and managing their code using professional development tools like VS Code and Git.

## Key concepts taught

- **How the web works** — the request/response cycle (browser as client, server answers), with DNS and HTTP/HTTPS named. Students read a wiki article before the session; the mentor session activates prior knowledge rather than re-teaching.
- **The three languages** — HTML (structure), CSS (style), JavaScript (behavior). This week is HTML only; it's the first shift away from JS.
- **Element vs. tag vs. attribute** — the whole element (opening tag + content + closing tag) vs. the `< >` tag itself vs. attributes carried inside the opening tag (e.g. `href`, `src`, `alt`). Includes self-closing tags (`<img>`, `<meta>`).
- **HTML boilerplate** — `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`. Students write it from scratch (rather than copy-paste) to understand each part. Emphasis that `<head>` is metadata, NOT the visible top of the page.
- **Inside `<head>`** — `<title>` (browser tab), `<meta charset>`, `<meta name="description">`. At least two meta elements required in the assignment (W3Schools HTML Head is the reference).
- **Content elements** — six heading levels (`h1`–`h6`), paragraphs (`<p>`), unordered/ordered lists (`<ul>`/`<ol>`/`<li>`), links (`<a href>`), images (`<img src alt>`).
- **Semantic structure** — grouping content in `<section>` elements with matching `id` attributes (`About`, `Experience`, `Connect`); previews next week's CSS styling and anchor-link navigation.
- **Tooling** — VS Code as the IDE (install + suggested extensions), save/refresh workflow, indentation, and Format Document.

Content is delivered via **Odin Project** (Intro to HTML/CSS, Elements & Tags, HTML Boilerplate, Working with Text, Lists, Links & Images) *or* **Scrimba** (HTML & CSS Crash Course, selected sections) — students pick one track. **AI Learning Prompts** appear throughout: Retrieval Practice (explain how the web works), Predict-then-Check (a `<ul>`/`<li>` snippet), and Scaffold Removal (ask AI for 3 debugging questions on a broken image/link rather than for the answer).

## Brief overview of the assignment

Not numbered questions — this week is a single build deliverable: an **`index.html` portfolio page** written from scratch, plus a Git workflow. Structure:

- **Setup / Git** — create a `lesson-5` branch (`git checkout -b lesson-5`), add full name to `README.md`, create `index.html` at the repo root.
- **Boilerplate** — `<!DOCTYPE html>` on line 1, then `<head>` (with `<title>` and at least two `<meta>` elements) and `<body>`.
- **Body content, in order** — name in `<h1>`; "About" `<h2>` + paragraph; "Experience" `<h2>` + `<ul>`/`<li>` list; "Connect" `<h2>` + at least two `<a>` links (GitHub and LinkedIn).
- **Semantic structure** — wrap About/Experience/Connect each in a `<section>` with a matching `id`.
- **Stretch goal (optional)** — add more elements: images, navigation menus, etc.
- **Git submission** — `git status` → `git add .` → `git commit -m "..."` → `git push`, then open a Pull Request on GitHub and submit the PR link. Students may self-merge if they want to continue before review.

## Likely trouble spots

- **`<head>` vs. visible page** — the single biggest confusion. Students expect `<head>` to be the visible top of the page and put `h1`/content there. Reinforce: `<head>` = background info, `<body>` = what users see. (Directly tested in a CFU slide.)
- **Closing-tag syntax** — writing `<p/>` (XML/JSX self-closing habit) instead of `</p>`. The `/` goes before the tag name in the closing tag.
- **`<a>` vs. `<link>`** — students reach for `<link>` (a real tag, but for stylesheets in `<head>`) to make a clickable link. Clickable links are `<a href>`.
- **Links without `https://`** — relative/bare URLs in the Connect section that don't navigate. Full `https://...` URLs are needed for external profile links.
- **Broken images (stretch)** — `<img src="photo.jpg">` shows a broken icon unless a real file sits in the same folder. This is exactly the AI-debugging prompt scenario from section 5.4.
- **`id` values not matching section names / anchors** — the convention is capitalized `id="About"`, `id="Experience"`, `id="Connect"` (matching the section names). The `id` and its `href="#..."` anchor must match exactly, including case — a mismatch silently breaks next week's CSS styling and the anchor-link navigation.
- **Forgetting `alt` on images** — accessibility requirement, easy to omit.
- **Git workflow friction** — this is the first full local add/commit/push + PR cycle. Watch for: forgetting to create the `lesson-5` branch, the `fatal: The current branch...` upstream error on first push (the message includes the exact fix), staging nothing, or submitting the repo link instead of the PR link.
- **Meta elements** — students may add only one, or invalid/guessed meta tags; point them to the W3Schools HTML Head resource.
