---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 5: HTML Basics"
---

# Lesson 5: HTML Basics

**Mentor Session Slide Deck**

Topics: How the Web Works, HTML Elements & Tags, Boilerplate, Semantic Structure

---

# How Do Web Pages Work?

1. You type a URL into your browser
2. Your browser sends a **request** to a server
3. The server sends back **files**: HTML, CSS, JavaScript
4. Your browser **renders** those files into the page you see

**HTML** = the structure (skeleton)
**CSS** = the style (appearance)
**JavaScript** = the behavior (interactivity)

---

# HTML: The Structure of a Web Page

HTML uses **tags** wrapped in angle brackets `< >` to describe content:

```html
<h1>This is a heading</h1>
<p>This is a paragraph of text.</p>
```

Most elements have an **opening tag** and a **closing tag**:
- Opening: `<p>`
- Closing: `</p>` (note the `/`)

Some elements are **self-closing**:
```html
<img src="photo.jpg" alt="A photo" />
```

---

# The HTML Boilerplate

Every HTML file starts with this structure:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Website</title>
    <meta charset="UTF-8" />
    <meta name="description" content="A short description" />
  </head>
  <body>
    <!-- Visible content goes here -->
  </body>
</html>
```

- `<head>` — metadata (title, description) — **not visible** on the page
- `<body>` — everything the user **sees**

---

# Common HTML Elements

| Element | Purpose | Example |
|---------|---------|---------|
| `<h1>` to `<h6>` | Headings (h1 = largest) | `<h1>Welcome</h1>` |
| `<p>` | Paragraph | `<p>About me...</p>` |
| `<ul>` / `<li>` | Unordered list / List item | See next slide |
| `<a>` | Link | `<a href="url">Click</a>` |
| `<img>` | Image | `<img src="pic.jpg" alt="desc" />` |
| `<section>` | Groups related content | Wraps a section of the page |

---

# Lists and Links

**Unordered list**:
```html
<ul>
  <li>JavaScript</li>
  <li>HTML</li>
  <li>CSS</li>
</ul>
```

**Links** (anchor tags):
```html
<a href="https://www.github.com">My GitHub</a>
<a href="https://www.linkedin.com/in/yourname">LinkedIn</a>
```

The `href` attribute tells the browser **where** to go when clicked.

---

# Attributes: Extra Information for Tags

Attributes go **inside the opening tag** and provide additional details:

```html
<a href="https://example.com" target="_blank">Visit Example</a>

<img src="photo.jpg" alt="A team photo" width="400" />

<section id="about">
  <h2>About Me</h2>
  <p>I'm learning to code!</p>
</section>
```

Common attributes:
- `href` — where a link goes
- `src` — source of an image
- `alt` — description for accessibility
- `id` — unique identifier for the element

---

# Semantic HTML: Organizing Content

Wrap related content in **semantic elements** to add meaning and structure:

```html
<body>
  <section id="about">
    <h2>About</h2>
    <p>I'm a student at Code the Dream.</p>
  </section>

  <section id="experience">
    <h2>Experience</h2>
    <ul>
      <li>JavaScript fundamentals</li>
      <li>Git version control</li>
    </ul>
  </section>

  <section id="connect">
    <h2>Connect</h2>
    <a href="https://github.com/yourname">GitHub</a>
  </section>
</body>
```

---

# Building a Simple Page Together

Let's build a page about a **local coffee shop**:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Bean There Cafe</title>
  </head>
  <body>
    <h1>Bean There Cafe</h1>
    <section id="menu">
      <h2>Menu</h2>
      <ul>
        <li>Espresso - $3</li>
        <li>Latte - $5</li>
        <li>Cold Brew - $4</li>
      </ul>
    </section>
    <section id="contact">
      <h2>Contact</h2>
      <p>123 Main St, Durham NC</p>
    </section>
  </body>
</html>
```

---

# Try This!

Create a simple HTML page about **your favorite hobby**. Include:

1. A `<title>` in the head
2. Your hobby name in an `<h1>`
3. A "Why I Love It" section with a paragraph
4. A "Gear I Use" section with an unordered list
5. A "Learn More" section with at least one link

**Remember**: Open the file in your browser to see the result!

---

# Key Takeaways

- HTML provides the **structure** of a web page using **tags** and **elements**
- Every page needs the **boilerplate**: `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`
- `<head>` holds metadata; `<body>` holds visible content
- Use **semantic elements** like `<section>` and `id` attributes to organize your page
- **Attributes** add extra info to tags: `href`, `src`, `alt`, `id`

**Next week**: CSS — you'll add colors, fonts, layout, and style to your HTML pages!
