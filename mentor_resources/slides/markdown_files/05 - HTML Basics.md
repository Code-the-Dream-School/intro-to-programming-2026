---
marp: true
theme: default
paginate: true
style: |
  section {
    background-color: #FFFFFF;
    color: #1C1C1C;
    font-family: 'Segoe UI', Arial, sans-serif;
  }
  h1 {
    color: #12284C;
    border-bottom: 3px solid #FF5C35;
    padding-bottom: 6px;
    margin-bottom: 12px;
  }
  h2 { color: #12284C; }
  h3 { color: #FF5C35; }
  pre {
    background-color: #1C1C1C;
    border-left: 5px solid #FF5C35;
    border-radius: 4px;
  }
  code {
    background-color: #F1F2F2;
    border-radius: 3px;
    padding: 1px 5px;
    color: #12284C;
  }
  pre code {
    background-color: transparent;
    color: #F1F2F2;
    padding: 0;
  }
  blockquote {
    border-left: 4px solid #F3C300;
    background-color: #F1F2F2;
    padding: 8px 16px;
    border-radius: 0 4px 4px 0;
    color: #12284C;
    margin: 8px 0;
  }
  section.title {
    background-color: #12284C;
    color: #FFFFFF;
    text-align: center;
  }
  section.title h1 {
    color: #F3C300;
    border-color: #FF5C35;
  }
  section.title h2,
  section.title h3,
  section.title p {
    color: #F1F2F2;
    border: none;
  }
  section.section-break {
    background-color: #FF5C35;
    color: #FFFFFF;
    text-align: center;
  }
  section.section-break h1 {
    color: #FFFFFF;
    border: none;
    font-size: 2.8em;
  }
  section.section-break h2,
  section.section-break p {
    color: #FFFFFF;
    border: none;
  }
  section.cfu {
    background-color: #F1F2F2;
  }
  section.cfu h1 {
    color: #12284C;
    border-bottom-color: #F3C300;
  }
---

<!--
MENTOR SETUP — Read before presenting. This is not a slide.

Opening Marp:
  VS Code: Install the Marp extension → open this file → "Open Preview" → fullscreen
  Browser: marp.app → paste this markdown → present from browser

Two-mentor structure (suggested):
  Mentor 1 leads the Explore section (slides 3–17).
  Mentor 2 leads the Apply section (slides 18–28).
  Both mentors stay on screen throughout.
  Mentor 2 can help answer questions and monitor chat during Explore.

Speaker notes appear in comment blocks on each slide.
In Marp presenter mode, notes display in your presenter panel — students do not see them.
-->

<!-- _class: title -->

# Lesson 5: HTML Basics

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Explain what happens when you load a web page
- Describe the roles of HTML, CSS, and JavaScript
- Identify elements, tags, and attributes in HTML code
- Write an HTML boilerplate from scratch
- Use headings, paragraphs, lists, links, and sections

<!--
Welcome students. Ask if anyone ran into anything interesting while reading the lesson.
This week is a shift from JavaScript to HTML — reassure students that this is a fresh start
and intentionally more visual and readable than what they've done before.
-->

---

<!-- _class: section-break -->

# Explore

---

# How the Web Works

When you visit a website, three things happen:

1. Your **browser** sends a request to a server
2. The **server** sends back files
3. Your **browser** reads the files and shows the page

> The browser is the client. It asks. The server answers.

<!--
Keep this brief — one minute or less. Students read an article about this before the session.
Goal: activate prior knowledge, not re-teach.
Ask: "Has anyone heard the term DNS before? What do you think it does?"
-->

---

# HTML, CSS, and JavaScript

Every web page is built with three languages:

| Language | Job |
|----------|-----|
| **HTML** | Structure — what's on the page |
| **CSS** | Style — how it looks |
| **JavaScript** | Behavior — what it does |

This week: **HTML only**.

<!--
A helpful analogy: HTML is the skeleton (bones), CSS is the skin and clothes, JS is the muscles.
Remind students they already know JavaScript — now they're adding a second tool.
-->

---

# What Is HTML?

**HTML** stands for HyperText Markup Language.

- Created in 1989
- Uses **tags** inside angle brackets `< >` to describe content
- Tells the browser: "This is a heading." "This is a link." "This is a list."

```html
<p>This is a paragraph.</p>
```

- `<p>` — opening tag
- `</p>` — closing tag (has a `/`)
- The text in between — the content

<!--
HTML is intentionally readable — it uses real English words like "paragraph", "head", "body".
Encourage students to think of tags as labels the browser reads.
-->

---

# Elements vs. Tags vs. Attributes

**Element** — the whole package: opening tag + content + closing tag

```html
<h1>Maria Santos</h1>
```

**Self-closing tag** — some elements need only one tag

```html
<img src="photo.jpg" alt="My photo">
```

**Attribute** — extra information inside the opening tag

```html
<a href="https://github.com">GitHub</a>
```

<!--
Students often mix up "element" and "tag". A simple rule: a tag is the `< >` part.
An element is everything, including the content inside.
The `href` in the anchor tag is a great first example of an attribute — it tells the
browser *where* the link goes.
-->

---

# Headings and Paragraphs

HTML has **six heading levels**. Level 1 is the biggest.

```html
<h1>My Name</h1>
<h2>About</h2>
<h3>Subsection</h3>
```

Paragraphs use `<p>`:

```html
<p>I am learning to code with Code the Dream.</p>
```

> Use headings to organize your page, not just to make text big.

<!--
Students will use h1, h2, and p in the assignment. Keep this focused.
You can ask: "What heading level would you use for a page title? What about a section title?"
-->

---

# Lists

**Unordered list** — bullet points

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

**Ordered list** — numbered

```html
<ol>
  <li>Read the lesson</li>
  <li>Write the code</li>
</ol>
```

<!--
Students use ul and li in the Experience section of the assignment.
Ask: "When would you use an ordered list instead of an unordered list?"
(Good answer: steps in a process, rankings, recipes.)
-->

---

# Links and Images

**Link** — uses `<a>` and the `href` attribute

```html
<a href="https://github.com/yourusername">GitHub</a>
```

**Image** — self-closing, uses `src` and `alt`

```html
<img src="photo.jpg" alt="A photo of me">
```

> Always include `alt` text. Screen readers use it.

<!--
The `alt` attribute is an accessibility requirement. Worth a brief mention.
For links: `href` = "hypertext reference" — where the link goes.
Students will add GitHub and LinkedIn links in the Connect section of the assignment.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What is the correct way to write a closing tag for a paragraph?**

A) `<p/>`

B) `<\p>`

C) `</p>`

D) `<!--p-->`

<!--
Answer: C.
Common mistake: students sometimes write <p/> (which is self-closing syntax from XML/JSX).
In HTML, closing tags use a forward slash before the tag name: </tagname>.
Let students answer before confirming — a show of hands or typed response in chat works well.
-->

---

# The HTML Boilerplate

Every HTML file starts with this structure:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Page</title>
  </head>
  <body>
    <!-- visible content goes here -->
  </body>
</html>
```

- `<!DOCTYPE html>` — tells the browser this is HTML5
- `<head>` — metadata (not visible to users)
- `<body>` — everything users see

<!--
"Boilerplate" means standard starter code. Professionals copy-paste it — students will
write it from scratch this week to understand each part.
Emphasize: the <head> is NOT the header at the top of the page. It's background information.
-->

---

# Inside the `<head>`

The `<head>` holds information *about* the page — not visible content.

```html
<head>
  <title>Maria's Portfolio</title>
  <meta charset="utf-8">
  <meta name="description" content="My portfolio page">
</head>
```

- `<title>` — shows in the browser tab
- `<meta charset>` — sets the character encoding
- `<meta name="description">` — helps with search engines

<!--
Students need to include at least two meta elements in the assignment.
Point them to the W3Schools HTML Head page (linked in the assignment) for more options.
The title element is visible in one place: the browser tab. Ask students to look at
their own browser tabs — every page they have open has a title.
-->

---

# Organizing with `<section>` and `id`

Use `<section>` to group related content.
Use `id` to label each section.

```html
<section id="about">
  <h2>About</h2>
  <p>I'm learning to code.</p>
</section>
```

The `id` attribute lets you jump to a section or style it later with CSS.

<!--
Students will create three sections in the assignment: About, Experience, Connect.
Preview: "Next week in CSS, you'll use these id values to style each section differently."
The id value should match the section name — about, experience, connect.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**Where does visible page content go in an HTML file?**

A) Inside `<head>`

B) Inside `<meta>`

C) Inside `<body>`

D) Inside `<!DOCTYPE html>`

<!--
Answer: C.
Students often confuse <head> and the visual "top of the page." Reinforce: <head> = background
info, <body> = what users actually see. If students pick A, gently walk through the boilerplate
again and point to where the h1 and section tags go.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**Which tag creates a clickable link?**

```html
<a href="https://github.com/yourusername">My GitHub</a>
```

A) `<link>`

B) `<url>`

C) `<a>`

D) `<href>`

<!--
Answer: C. The anchor tag <a> creates links. href is an attribute of <a>, not a tag itself.
<link> is a real HTML tag but it's used in the <head> to link stylesheets, not to create
clickable links on the page. This is a common source of confusion.
-->

---

<!-- _class: section-break -->

# Apply

<!--
Mentor 2 leads from here (suggested).
Open VS Code before this slide. Have a blank index.html file ready.
You'll build the assignment page live with the group, step by step.
Students should have VS Code open and follow along.
-->

---

# Core Activity: Build a Portfolio Page

We'll build `index.html` together — **tell me what to type!**

Open **VS Code** and create a new file called `index.html`.

> This is exactly what you'll build for the assignment.

<!--
You type; students direct you. If someone suggests something incorrect, type it anyway
and show what happens. Real mistakes are more valuable than perfect code.
Narrate as you type: "I'm opening the angle bracket now, typing h1, closing it..."
-->

---

# Step 1 — Write the Boilerplate

**Ask the group:** What goes on line 1?

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Maria's Portfolio</title>
    <meta charset="utf-8">
  </head>
  <body>

  </body>
</html>
```

Save the file. Open it in a browser. What do you see?

<!--
Students should see a blank page with "Maria's Portfolio" in the browser tab.
That small visible result is satisfying — celebrate it.
Ask: "Why is the page blank? Where does our visible content go?"
-->

---

# Step 2 — Add a Name and About Section

Inside `<body>`, add:

```html
<h1>Maria Santos</h1>

<section id="about">
  <h2>About</h2>
  <p>I'm learning to code with Code the Dream!</p>
</section>
```

Save and refresh. What changed?

<!--
Students should see a heading and a paragraph appear on the page.
Ask: "What heading level would your own name use? Why not h2?"
This step mirrors the first two checklist items in the body section of the assignment.
-->

---

# Step 3 — Add an Experience Section

```html
<section id="experience">
  <h2>Experience</h2>
  <ul>
    <li>Intro to Programming — Code the Dream</li>
    <li>Self-taught HTML</li>
  </ul>
</section>
```

**Ask the group:** What comes next?

<!--
Students should recognize the Connect section is next.
If no one answers, ask: "Look at the assignment checklist — what are the three sections?"
Keep the pacing steady. The goal is to finish through the Connect section.
-->

---

# Step 4 — Add a Connect Section

```html
<section id="connect">
  <h2>Connect</h2>
  <ul>
    <li><a href="https://github.com/yourusername">GitHub</a></li>
    <li><a href="https://linkedin.com/in/you">LinkedIn</a></li>
  </ul>
</section>
```

Save and refresh. Click the links — do they work?

<!--
Point out that href="https://..." uses the full URL. Students often forget the https://.
If a link doesn't work, ask the group to find the bug. This is good practice.
Remind students: for the assignment, they should use their real GitHub and LinkedIn URLs.
-->

---

<!-- _class: section-break -->

# Extension Activity

*Only if time allows and students are ready.*

---

# Extension — Add Images and Navigation

**Challenge: Add a profile photo and a navigation menu.**

```html
<img src="photo.jpg" alt="A photo of Maria">
```

```html
<nav>
  <a href="#about">About</a>
  <a href="#experience">Experience</a>
  <a href="#connect">Connect</a>
</nav>
```

**What happens when you click a nav link?**

<!--
The nav links use #about, #experience, #connect — they jump to the matching id on the page.
This is the "anchor link" pattern. Students may not have seen it before.
The image won't load unless a real file named photo.jpg is in the same folder.
Ask: "What does the browser show if the image file isn't found?" (broken image icon)
This connects to the AI debugging prompt in the lesson: "my image shows a broken icon."
-->

---

# Assignment Preview

This week you'll build your own `index.html` portfolio page:

- HTML boilerplate: `<!DOCTYPE html>`, `<head>`, `<body>`
- At least two `<meta>` elements in `<head>`
- Your name in an `<h1>`
- **About** section — paragraph about you
- **Experience** section — list of skills or experiences
- **Connect** section — links to GitHub and LinkedIn
- Each section wrapped in `<section id="...">` 

> Push your work to a new `lesson-5` branch and open a pull request.

<!--
Walk through this checklist quickly. Students have the full assignment in writing.
Key things to flag:
  1. The id values matter — they should match "about", "experience", "connect".
  2. Links need real URLs with https:// to work.
  3. They push to a lesson-5 branch this week (git checkout -b lesson-5).
-->

---

# Tips for the Assignment

1. **Write the boilerplate first** — then add content inside `<body>`
2. **Save and refresh often** — check your page in the browser as you go
3. **Indent nested tags** — it makes your code easier to read and debug
4. **Stuck on a broken image or link?** Ask AI for hints:

> "My image shows a broken icon. Here is my code: [paste]. Can you ask me 3 questions to help me find the path problem?"

<!--
Tip 3 is worth demonstrating: show indented vs. un-indented HTML side by side if time allows.
Tip 4 mirrors the AI prompt from section 5.4 of the lesson. Normalize using AI for debugging hints.
Remind students: VS Code can auto-format HTML — right-click → Format Document.
-->

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel writing basic HTML?

### Before next session:
- Install **VS Code** if you haven't already
- Work through the **lesson materials** (Odin Project or Scrimba)
- Build your **portfolio page** in `index.html`
- Push to a `lesson-5` branch and open a pull request
- Post questions in **Slack** anytime

<!--
Read out a few confidence numbers from chat. If many students say 1–2, reassure them:
HTML is very readable — they'll feel more confident once they open VS Code and start typing.
If many say 4–5, ask someone to share one thing they're still unsure about.
-->

---

# Resources

| Resource | What it's for |
|----------|---------------|
| Odin Project — Elements & Tags | Core HTML reading |
| Odin Project — HTML Boilerplate | Boilerplate deep dive |
| Odin Project — Working with Text | Headings and paragraphs |
| Odin Project — Lists | ul, ol, li |
| Odin Project — Links and Images | a, img, attributes |
| Scrimba HTML & CSS Crash Course | Video walkthroughs |
| W3Schools HTML Head | Meta elements reference |
| MDN HTML Basics | Authoritative reference |

> **Next week:** CSS Basics — making your page look great!

---

<!-- _class: title -->

# Great work today!

## You've written your first web page.

Questions? Reach out on Slack anytime.
