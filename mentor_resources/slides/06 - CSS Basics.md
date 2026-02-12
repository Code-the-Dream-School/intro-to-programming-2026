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

# Lesson 6: CSS Basics

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

Think of a website you love the look of. What makes it visually appealing? Colors? Layout? Fonts?

<!--
This gets students thinking about design before we introduce CSS.
It's okay if they can't name specific CSS properties — we'll get there.
-->

---

# What You'll Learn This Week

- **CSS** — styling your HTML page
- **Selectors** — targeting elements to style
- **The box model** — how spacing works
- **Flexbox** — creating layouts
- **Navigation** — linking sections of your page

---

# I Do: What Is CSS?

**Cascading Style Sheets** — the design layer of the web.

HTML = **structure** | CSS = **presentation**

```css
body {
    background-color: #f0f0f0;
    color: #333;
    font-family: Arial, sans-serif;
}
```

This changes the background, text color, and font of the entire page.

---

# I Do: CSS Syntax

Every CSS rule has the same pattern:

```css
selector {
    property: value;
}
```

```css
h1 {
    color: navy;
    font-size: 2em;
}
```

- **Selector** — what to style (`h1`)
- **Property** — what to change (`color`)
- **Value** — what to change it to (`navy`)

---

# I Do: Linking CSS to HTML

Create a file called `index.css` and link it in your HTML `<head>`:

```html
<head>
    <title>My Portfolio</title>
    <link rel="stylesheet" href="css/index.css">
</head>
```

Now any styles in `index.css` will apply to your page.

---

# I Do: Selectors

**Element** selector — targets all of that element:
```css
p { color: gray; }
```

**Class** selector — targets elements with a class:
```css
.highlight { background-color: yellow; }
```

**ID** selector — targets one specific element:
```css
#about { padding: 20px; }
```

---

# I Do: The Box Model

Every HTML element is a **box** with four layers:

- **Content** — the actual text/image
- **Padding** — space inside the border
- **Border** — the edge of the box
- **Margin** — space outside the border

```css
section {
    padding: 20px;
    margin: 10px;
    border: 1px solid #ccc;
}
```

> Tip: add colored borders to see your sections clearly!

---

# I Do: Flexbox

Flexbox lets you **arrange items in rows or columns**.

```css
.experience-list {
    display: flex;
    gap: 20px;
}
```

This turns a stacked list into a horizontal row.

Key properties:
- `display: flex` — activates flexbox
- `gap` — space between items
- `justify-content` — horizontal alignment
- `align-items` — vertical alignment

---

# I Do: Navigation

Add a `<nav>` element to your HTML for internal links:

```html
<nav>
    <a href="#about">About</a>
    <a href="#experience">Experience</a>
    <a href="#connect">Connect</a>
</nav>
```

The `#about` links to the element with `id="about"` — clicking it scrolls there.

---

<!--
Transition to We Do:
- Ask: "What questions do you have about CSS so far?"
- Remind students: make small changes, save, and refresh.
-->

# We Do: Style a Page Together! (15-20 min)

Open your portfolio's `index.html` and create `css/index.css`.

**Let's make it look great — one step at a time!**

---

# We Do: Background and Text

Let's start with the basics:

```css
body {
    background-color: #f5f5f5;
    color: #333;
    font-family: 'Segoe UI', Arial, sans-serif;
    margin: 0;
    padding: 20px;
}
```

**Save and refresh.** What changed?

---

# We Do: Style the Heading

```css
h1 {
    color: #1a73e8;
    font-size: 2.5em;
    text-align: center;
}

h2 {
    color: #555;
    border-bottom: 2px solid #1a73e8;
    padding-bottom: 5px;
}
```

**Ask the group:** What does `border-bottom` do?

---

# We Do: Add Spacing with the Box Model

```css
section {
    padding: 20px;
    margin-bottom: 30px;
}
```

**Debugging tip:** Add a temporary border to see your boxes:

```css
section {
    border: 2px solid red;
}
```

**Ask the group:** What's the difference between padding and margin?

---

# We Do: Flexbox Layout

Let's lay out the Connect links in a row:

```css
#connect ul {
    display: flex;
    gap: 20px;
    list-style: none;
    padding: 0;
}
```

**Zoom chat:** What does `list-style: none` do?

---

<!--
Transition to You Do:
Set a timer for 5-10 minutes.
Encourage students to experiment — there are no wrong answers in design!
-->

# You Do: Independent Practice (5-10 min)

Try **one** of these on your own portfolio:

**A)** Change the background color and font of your page.

**B)** Add padding and margin to your sections.

**C)** Use flexbox to lay out your Experience or Connect section.

> Tip: Use browser DevTools (right-click > Inspect) to experiment!

---

# You Do: Share Out

**Who wants to share their styled page?**

- What CSS properties did you use?
- What was harder than you expected?

---

# Assignment Preview

This week's assignment has two parts:

**CSS Styling:**
- Background color, text color, fonts
- Padding/margin between sections
- Styled headings, name, list items, and links

**HTML Additions:**
- Add a `<nav>` with internal links
- Add **Skills** and **Projects** sections (empty for now)
- Use flexbox for Experience and Connect layouts

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel writing basic CSS?

### Before next session:
- Work through the **lesson materials** (Odin Project or Scrimba)
- **Style your portfolio** (CSS file + navigation)
- Add **Skills** and **Projects** section headings
- Reach out on **Slack** if you get stuck!

---

# Resources

- **Odin Project:** Intro to CSS, The Cascade, Box Model, Flexbox
- **Scrimba:** HTML & CSS Crash Course, Learn Flexbox
- **CSS-Tricks:** [A Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- **MDN:** [CSS Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)

> **Next week:** The DOM API — making your page interactive with JavaScript!

---

<!-- _class: title-slide -->

# Great work this week!

## Your portfolio is starting to take shape.

Questions? Reach out on Slack anytime.
