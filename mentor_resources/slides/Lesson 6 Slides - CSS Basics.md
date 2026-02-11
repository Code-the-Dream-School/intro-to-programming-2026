---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 6: CSS Basics"
---

# Lesson 6: CSS Basics

**Mentor Session Slide Deck**

Topics: CSS Syntax, Selectors, Box Model, Flexbox, Layout

---

# What is CSS?

**Cascading Style Sheets** — the language that makes HTML look good.

- HTML = **what** is on the page (structure)
- CSS = **how** it looks (style)

```css
body {
    background-color: #1a1a2e;
    color: white;
    font-family: Arial, sans-serif;
}
```

One line of CSS can change the entire look of your page.

---

# Linking CSS to HTML

Create a separate CSS file and link it in your HTML `<head>`:

```html
<head>
    <title>My Portfolio</title>
    <link rel="stylesheet" href="css/index.css" />
</head>
```

**File structure**:
```
my-project/
├── index.html
├── css/
│   └── index.css
```

**Tip**: Make sure the `href` path matches your actual file location!

---

# CSS Syntax

```css
selector {
    property: value;
    property: value;
}
```

**Example**:
```css
h1 {
    color: #e94560;
    font-size: 36px;
    text-align: center;
}
```

- **Selector** = which element(s) to style
- **Property** = what to change
- **Value** = how to change it

---

# CSS Selectors

| Selector | Targets | Example |
|----------|---------|---------|
| `h1` | All `<h1>` elements | `h1 { color: blue; }` |
| `.card` | Elements with `class="card"` | `.card { padding: 20px; }` |
| `#about` | The element with `id="about"` | `#about { background: gray; }` |

```html
<section id="about" class="card">
    <h2>About Me</h2>
</section>
```

**Rule of thumb**: Use **classes** for reusable styles, **IDs** for unique elements.

---

# The Box Model

Every element is a **box** with four layers:

```
┌───────────── Margin (space outside) ──────────────┐
│  ┌─────────── Border ───────────┐                  │
│  │  ┌─────── Padding ────────┐  │                  │
│  │  │                        │  │                  │
│  │  │       Content          │  │                  │
│  │  │                        │  │                  │
│  │  └────────────────────────┘  │                  │
│  └──────────────────────────────┘                  │
└────────────────────────────────────────────────────┘
```

```css
.card {
    padding: 20px;          /* Space inside the border */
    margin: 16px;           /* Space outside the border */
    border: 2px solid gray; /* The border itself */
}
```

---

# Seeing the Box Model

Use your browser's **Developer Tools** to visualize it:

1. Right-click any element → **Inspect**
2. Look at the **Box Model** diagram in the panel
3. Hover over elements to see their boxes highlighted

**Debugging tip**: If spacing looks wrong, add a temporary border:
```css
section {
    border: 2px solid red;
}
```
This makes it easy to see where each section starts and ends.

---

# Flexbox: Modern Layouts

Flexbox makes it easy to **arrange elements** in rows or columns:

```css
.nav-links {
    display: flex;
    justify-content: space-around;
    align-items: center;
}
```

```html
<ul class="nav-links">
    <li>About</li>
    <li>Experience</li>
    <li>Connect</li>
</ul>
```

**Key rule**: `display: flex` goes on the **parent** (container), and it affects the **children** (items inside).

---

# Flexbox Properties

| Property | What it does | Common values |
|----------|-------------|---------------|
| `display: flex` | Activates flexbox | — |
| `flex-direction` | Row or column | `row`, `column` |
| `justify-content` | Horizontal alignment | `center`, `space-between`, `space-around` |
| `align-items` | Vertical alignment | `center`, `flex-start`, `flex-end` |
| `gap` | Space between items | `10px`, `1rem` |

```css
.experience-list {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 16px;
}
```

---

# Building a Navigation Bar

```html
<nav>
    <ul class="nav-list">
        <li><a href="#about">About</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#connect">Connect</a></li>
    </ul>
</nav>
```

```css
.nav-list {
    display: flex;
    justify-content: center;
    gap: 24px;
    list-style: none;
    padding: 0;
}

.nav-list a {
    text-decoration: none;
    color: #0f3460;
    font-weight: bold;
}
```

---

# Try This!

Take this HTML and style it with Flexbox:

```html
<section class="team">
    <div class="member">Alice — Developer</div>
    <div class="member">Bob — Designer</div>
    <div class="member">Carol — PM</div>
</section>
```

Goals:
1. Display the three members in a **horizontal row**
2. Add **spacing** between them
3. Give each member a **background color**, **padding**, and **rounded corners**

**Bonus**: Make the row become a column on small screens (hint: `flex-direction`).

---

# Key Takeaways

- CSS styles HTML with **selectors**, **properties**, and **values**
- Link your CSS file in the HTML `<head>` with `<link rel="stylesheet">`
- The **Box Model**: content → padding → border → margin
- **Flexbox** is the go-to tool for layout — `display: flex` on the parent
- Use **Dev Tools** to inspect and debug your styles in real time

**Next week**: The DOM API — using JavaScript to dynamically add and change content on your page!
