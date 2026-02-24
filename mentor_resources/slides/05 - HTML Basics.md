---
marp: true
theme: default
paginate: true
style: |
  section {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #ffffff;
    color: #333333;
  }
  h1 { color: #1a73e8; }
  h2 { color: #1a73e8; }
  code {
    background-color: #f0f4f8;
    padding: 2px 6px;
    border-radius: 4px;
  }
  pre code { padding: 16px; }
  section.title-slide {
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  blockquote {
    border-left: 4px solid #1a73e8;
    padding-left: 16px;
    color: #555;
  }
---

<!--
FOR MENTORS: Using These Slides

IN VS CODE:
1. Install the "Marp for VS Code" extension
2. Open this .md file
3. Command Palette > "Marp: Open Preview to the Side"
4. Export: Command Palette > "Marp: Export Slide Deck"

IN THE BROWSER:
1. Go to https://web.marp.app/
2. Paste or upload this file
3. Present directly or export
-->

<!-- _class: title-slide -->

# Lesson 5: HTML Basics

## Intro to Programming

### Code the Dream

---

# Today's Game Plan

| Section | Time |
|---------|------|
| Warm-Up | 5 min |
| I Do | 10-15 min |
| We Do | 15-20 min |
| You Do | 5-10 min |
| Wrap-Up | 5 min |

---

# Warm-Up (5 min)

**Zoom chat:**

Go to any website you like. Right-click and choose "View Page Source."

What do you notice? Does anything look familiar?

<!--
This is a great way to show students that every website they use
is built with the same HTML they're about to learn.
-->

---

# What You'll Learn This Week

- **How the web works** — clients, servers, requests
- **HTML** — the structure of every web page
- **Elements, tags, and attributes** — the building blocks
- **VS Code** — your development environment
- **Building a portfolio page** — your assignment!

---

# I Do: How the Web Works

When you visit a website:

1. Your **browser** (client) sends a request
2. A **server** sends back files
3. Your browser **renders** those files

The server sends three types of files:
- **HTML** — structure and content
- **CSS** — styling and layout
- **JavaScript** — behavior and interactivity

---

# I Do: What Is HTML?

**HyperText Markup Language** — the skeleton of every web page.

HTML uses **tags** to define elements:

```html
<p>This is a paragraph.</p>
```

- `<p>` — opening tag
- `</p>` — closing tag
- Everything between — the content

---

# I Do: Common HTML Elements

**Headings** (6 levels):
```html
<h1>Main Title</h1>
<h2>Section Title</h2>
<h3>Subsection</h3>
```

**Paragraph:**
```html
<p>This is some text about me.</p>
```

**Link:**
```html
<a href="https://example.com">Click here</a>
```

---

# I Do: Lists and Images

**Unordered list:**
```html
<ul>
    <li>JavaScript</li>
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

**Image** (self-closing tag):
```html
<img src="photo.jpg" alt="My photo">
```

> The `alt` attribute describes the image for accessibility.

---

# I Do: HTML Boilerplate

Every HTML file starts with this structure:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Page</title>
  </head>
  <body>
    <!-- Visible content goes here -->
  </body>
</html>
```

- `<head>` — metadata (title, description)
- `<body>` — what users see

---

# I Do: Sections and IDs

Use `<section>` to organize your page:

```html
<section id="about">
    <h2>About</h2>
    <p>A paragraph about me.</p>
</section>

<section id="experience">
    <h2>Experience</h2>
    <ul>
        <li>Code the Dream</li>
    </ul>
</section>
```

The `id` attribute lets you target specific sections later.

---

<!--
Transition to We Do:
- Ask: "What questions do you have about HTML so far?"
- Emphasize that HTML is about structure, not appearance.
-->

# We Do: Build a Page Together! (15-20 min)

Let's build a simple portfolio page from scratch.

Open **VS Code** (or any code editor) and create a new file called `index.html`.

---

# We Do: Start with the Boilerplate

**Ask the group:** What goes first?

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Maria's Portfolio</title>
  </head>
  <body>

  </body>
</html>
```

Save and open in your browser — what do you see?

---

# We Do: Add Content

Let's add a name and About section inside `<body>`:

```html
<h1>Maria Santos</h1>

<section id="about">
    <h2>About</h2>
    <p>I'm learning to code with Code the Dream!</p>
</section>
```

**Ask the group:** What should we add next?

---

# We Do: Add a List

Let's add an Experience section:

```html
<section id="experience">
    <h2>Experience</h2>
    <ul>
        <li>Intro to Programming - Code the Dream</li>
        <li>Self-taught HTML and CSS</li>
    </ul>
</section>
```

**Follow-up:** How would we add a Connect section with links?

---

# We Do: Add Links

```html
<section id="connect">
    <h2>Connect</h2>
    <ul>
        <li>
            <a href="https://github.com/maria">GitHub</a>
        </li>
        <li>
            <a href="https://linkedin.com/in/maria">LinkedIn</a>
        </li>
    </ul>
</section>
```

Save and refresh — you have a portfolio page!

---

<!--
Transition to You Do:
Set a timer for 5-10 minutes.
-->

# You Do: Independent Practice (5-10 min)

Open your editor and try **one** of these:

**A)** Create an HTML file with the boilerplate, your name in an `<h1>`, and a paragraph about yourself.

**B)** Add a list of your skills or hobbies using `<ul>` and `<li>`.

**C)** Add links to your GitHub and LinkedIn profiles.

---

# You Do: Share Out

**Who wants to share their page?**

- What elements did you use?
- Did anything surprise you about how it rendered?

---

# Assignment Preview

This week you'll build **your portfolio page** in `index.html`:

- HTML boilerplate (DOCTYPE, head, body)
- Your name in an `<h1>`
- **About** section with a paragraph
- **Experience** section with a list
- **Connect** section with links (GitHub, LinkedIn)
- Each section wrapped in `<section>` with an `id`

---

# VS Code Setup

If you haven't already, install **Visual Studio Code**:

- A code editor that combines text editing, terminal, and file management
- Install the **Live Server** extension to preview your page in real-time

> The lesson includes a video walkthrough of the setup.

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel writing basic HTML?

### Before next session:
- Install **VS Code** if you haven't already
- Work through the **lesson materials** (Odin Project or Scrimba)
- Build your **portfolio page** in `index.html`
- Reach out on **Slack** if you get stuck!

---

# Resources

- **Odin Project:** Elements & Tags, Boilerplate, Working with Text, Lists, Links & Images
- **Scrimba:** HTML & CSS Crash Course
- **W3Schools:** [HTML Tutorial](https://www.w3schools.com/html/)
- **MDN:** [HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)

> **Next week:** CSS Basics — making your page look great!

---

<!-- _class: title-slide -->

# Great work this week!

## You've built your first web page.

Questions? Reach out on Slack anytime.
