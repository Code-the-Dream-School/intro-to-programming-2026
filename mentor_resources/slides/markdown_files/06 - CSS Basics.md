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
  One mentor leads the Explore section (slides 3–15).
  The other leads the Apply section (slides 16–26).
  Both mentors stay on screen throughout. The second mentor can support questions during Explore.

Speaker notes (mentor-only guidance) appear in comment blocks like this one.
In Marp presenter mode, notes display in your presenter panel.
-->

<!-- _class: title -->

# Lesson 6: CSS Basics

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Explain what CSS is and how it connects to HTML
- Write CSS rules using selectors, properties, and values
- Use the box model to control spacing with padding and margin
- Create a flexible layout using Flexbox
- Add a navigation bar to a webpage

<!--
This is also your checklist for pacing. If you're running short on time, the box model
and Flexbox slides are the highest priority — both are required in the assignment.
-->

---

<!-- _class: section-break -->

# Explore

---

# What Is CSS?

**HTML** gives a page its **structure**.
**CSS** gives a page its **style**.

```css
body {
  background-color: #f0f0f0;
  color: #333;
  font-family: Arial, sans-serif;
}
```

CSS stands for **Cascading Style Sheets**.
These three lines change the background, text color, and font for the entire page.

<!--
Ask: "Think of a website you like the look of. What makes it visually appealing?"
Give students 30 seconds to type one word in the Zoom chat before moving on.
This is a low-stakes way to connect CSS to things they already care about.
-->

---

# How to Link CSS to HTML

Create a file called `index.css` inside a `css` folder.
Then link it in the `<head>` of your HTML file:

```html
<head>
  <title>My Portfolio</title>
  <link rel="stylesheet" href="css/index.css">
</head>
```

The `<link>` tag tells the browser: "apply the styles in this file."

> The `href` value must match the exact path to your CSS file.

<!--
This is the first task in the assignment. Many students create the file but forget to link it —
or they get the path wrong. Remind them: the folder is named css, and the file is index.css.
-->

---

# CSS Syntax

Every CSS rule follows the same pattern:

```css
selector {
  property: value;
}
```

A real example:

```css
h1 {
  color: navy;
  font-size: 2em;
}
```

- **Selector** — which element to style (`h1`)
- **Property** — what to change (`color`, `font-size`)
- **Value** — what to change it to (`navy`, `2em`)

<!--
Point out the curly braces and the semicolons. Missing semicolons are one of the
most common bugs students hit. If a style does not appear to work, that is the first thing to check.
-->

---

# Three Types of Selectors

**Element** — styles every instance of that tag:
```css
p { color: gray; }
```

**Class** — styles any element with that class name:
```css
.highlight { background-color: yellow; }
```

**ID** — styles one specific element:
```css
#about { padding: 20px; }
```

<!--
The assignment uses IDs heavily — each section (about, experience, connect, skills, projects)
has an id attribute. Make sure students understand the # prefix for IDs and . for classes.
-->

---

# The Cascade: Which Style Wins?

When two rules target the same element, CSS has to choose one.

```css
p { color: blue; }        /* lower specificity */

.red-text { color: red; } /* higher specificity */
```

```html
<p class="red-text">Hello World</p>
```

The text will be **red** — the class rule wins.

> This is the "Cascading" part of CSS. More specific rules override less specific ones.

<!--
This is taken directly from the lesson's AI prompt exercise. If students have worked ahead
they may have already explored this. Ask: "Who tried the predict-then-check exercise in the lesson?"
-->

---

<!-- _class: cfu -->

# Check for Understanding

**An element has both a tag rule and a class rule targeting the same property. Which one applies?**

A) The tag rule — it was written first

B) The class rule — classes are more specific than tags

C) Neither — they cancel each other out

D) Both — the styles are combined

<!--
Answer: B.
Specificity order from lowest to highest: element → class → ID → inline style.
If students pick D, clarify: when two rules set the same property, only one value can win.
Different properties from both rules can still apply (e.g., color from the class, font-size from the tag).
-->

---

# The Box Model

Every HTML element is a **box** with four layers:

- **Content** — the text or image inside
- **Padding** — space between content and the border
- **Border** — the visible edge of the box
- **Margin** — space outside the border, between elements

```css
section {
  padding: 20px;
  margin-bottom: 30px;
  border: 1px solid #ccc;
}
```

> Tip: add a colorful border to any element to see its box clearly.

<!--
The box model confuses almost everyone at first. The tip at the bottom is extremely practical
and mirrors advice in the assignment itself. Encourage students to use it while building.
-->

---

# Padding vs. Margin

**Padding** = space *inside* the box (between content and border)

**Margin** = space *outside* the box (between this element and its neighbors)

```css
.card {
  padding: 16px;   /* breathing room inside */
  margin: 24px;    /* pushes neighbors away */
}
```

Think of it like a picture frame:
- Padding = the white mat inside the frame
- Margin = the wall space around the frame

<!--
This analogy resonates with students. If time allows, ask: "What would happen if you set
padding to 0? What about margin to 0?" Let students predict before you demonstrate.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**You want more space between two `<section>` elements. Which property should you change?**

A) `padding` — it controls spacing between elements

B) `border` — making it thicker adds space

C) `margin` — it controls space outside the element

D) `font-size` — bigger text makes sections farther apart

<!--
Answer: C.
Padding adds space inside an element; margin adds space outside.
If students pick A, draw the box model mentally: padding pushes the content away from the border,
but the border of one section is still right against the border of the next.
-->

---

# Flexbox

Flexbox lets you **arrange items in a row or column**.

```css
#connect ul {
  display: flex;
  gap: 16px;
  list-style: none;
  padding: 0;
}
```

Before: links stacked in a vertical list.
After: links sit side by side in a row.

Key properties:
- `display: flex` — turns on Flexbox
- `gap` — space between flex items
- `justify-content` — aligns items left/center/right
- `flex-direction` — `row` (default) or `column`

<!--
Flexbox is required for both the Experience section and the Connect section in the assignment.
Focus on display: flex and gap first — those two alone produce a noticeable change.
Save flex-direction and justify-content for the Apply demo.
-->

---

# Flexbox for the Experience Section

The assignment asks you to display experience items in columns:

```css
#experience ul {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  list-style: none;
  padding: 0;
}

#experience li {
  flex: 1 1 200px;
  padding: 12px;
  border: 1px solid #ccc;
}
```

Each `<li>` becomes a styled card that wraps to the next row when the screen is narrow.

<!--
The assignment specifically suggests: job title on the left, dates on the right, description below.
Students do not need to match exactly — they should experiment. This slide shows one approach.
flex: 1 1 200px means: grow, shrink, and start at 200px wide. Students don't need to memorize this.
-->

---

# Navigation with `<nav>`

A `<nav>` element groups your navigation links.
Internal links use `#` followed by the section's `id`:

```html
<nav>
  <a href="#about">About</a>
  <a href="#experience">Experience</a>
  <a href="#skills">Skills</a>
  <a href="#projects">Projects</a>
  <a href="#connect">Connect</a>
</nav>
```

Clicking a link **scrolls the page** to that section.

> The section must have a matching `id` attribute for the link to work.

<!--
Students often forget to add the id attributes to their sections before testing the nav links.
Remind them: <section id="about"> must exist for <a href="#about"> to work.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**Which CSS property is required to make a Flexbox layout?**

A) `flex-direction: row`

B) `display: flex`

C) `gap: 20px`

D) `justify-content: center`

<!--
Answer: B.
display: flex is the one required property — it activates Flexbox on a container.
All other flex properties are optional and have default values.
A is a default (row), so it has no visible effect unless you want column.
C and D are useful but not required.
-->

---

<!-- _class: section-break -->

# Apply

<!--
Second mentor leads from here (suggested).
Before this slide: open VS Code with a portfolio project ready — or use a simple
HTML/CSS starter file in the browser. The goal is live coding students can follow along with.
Have the browser DevTools open alongside your editor so students can see both.
-->

---

# Core Activity: Style a Page Together

We will build CSS step by step — **you tell me what to type!**

Open your portfolio project in VS Code.
Make sure your `css/index.css` file is linked in `index.html`.

> Make one small change, save, and refresh before moving to the next step.

<!--
You type; students direct. If someone suggests something unexpected, try it — seeing an
unintended result is often more educational than seeing perfect code.
Remind students: save the file, then refresh the browser. Many forget to refresh.
-->

---

# Step 1 — Body Styles

Let's set a foundation for the whole page:

```css
body {
  background-color: #f5f5f5;
  color: #333;
  font-family: 'Segoe UI', Arial, sans-serif;
  margin: 0;
  padding: 20px;
}
```

**Save and refresh.** What changed on the page?

<!--
Ask the group to describe what they see before explaining it yourself.
Setting margin: 0 removes the browser's default margin — students notice the page
no longer has a gap around the edges.
-->

---

# Step 2 — Style the Headings

```css
h1 {
  font-size: 2.5em;
  text-align: center;
}

h2 {
  color: #12284C;
  border-bottom: 2px solid #FF5C35;
  padding-bottom: 4px;
}
```

**Ask the group:** What does `border-bottom` do to an `h2`?

<!--
Students are often surprised that you can put a border on just one side of an element.
This is a good opportunity to mention border-top, border-left, border-right as well.
-->

---

# Step 3 — Add Spacing Between Sections

```css
section {
  padding: 20px;
  margin-bottom: 30px;
}
```

**Debugging tip — add a temporary border to see the boxes:**

```css
section {
  border: 2px solid red;
}
```

Remove the red border once you understand the layout.

<!--
This matches the tip in the assignment text exactly. Normalizing "debugging by adding borders"
as a professional technique helps students feel comfortable using it.
-->

---

# Step 4 — Flexbox for the Connect Section

```css
#connect ul {
  display: flex;
  gap: 20px;
  list-style: none;
  padding: 0;
}
```

**Before:** links stacked vertically.
**After:** links arranged in a row.

**Zoom chat:** What does `list-style: none` remove from the list?

<!--
Answer: the bullet points. Students notice the bullets disappear when they apply this.
After the group answers, ask: "How would we put the links in a column instead of a row?"
(Answer: flex-direction: column — but that is the default behavior without Flexbox.)
-->

---

# Step 5 — Add the Navigation Bar

Add a `<nav>` block near the top of your `index.html`:

```html
<nav>
  <a href="#about">About</a>
  <a href="#experience">Experience</a>
  <a href="#skills">Skills</a>
  <a href="#projects">Projects</a>
  <a href="#connect">Connect</a>
</nav>
```

Then style it in `index.css`:

```css
nav {
  display: flex;
  gap: 16px;
  padding: 12px 20px;
  background-color: #12284C;
}

nav a { color: #FFFFFF; text-decoration: none; }
```

<!--
Students need to add the Skills and Projects sections to their HTML this week as well —
the nav links for those two will not work until those sections exist with matching ids.
Remind them: id="skills" and id="projects" are required.
-->

---

<!-- _class: section-break -->

# Extension Activity

*Only if students are ready and time allows.*

---

# Extension — Sticky Navigation

Make the navigation bar stay at the top of the screen as the user scrolls:

```css
nav {
  position: sticky;
  top: 0;
  z-index: 100;
}
```

- `position: sticky` — the element scrolls normally until it hits the top, then it stays
- `top: 0` — it sticks at the very top edge
- `z-index: 100` — keeps it on top of other content

**Test it:** add enough content to your page that it scrolls, then scroll down.

<!--
This is a stretch goal listed in the assignment. It requires that the nav has position: sticky
AND a defined top value — students often add position: sticky but forget top: 0.
If students try this, make sure their nav is a direct child of the body (not nested inside another
container with overflow: hidden, which would break sticky behavior).
-->

---

# Assignment Preview

**This week's assignment has two parts:**

### Part 1 — CSS Styling
- Link an external stylesheet
- Change background color, text color, and font
- Add padding and margin between sections
- Style headings, your name, list items, and links

### Part 2 — Layout and Navigation
- Add a `<nav>` bar with internal links
- Add **Skills** and **Projects** sections (empty — filled in later)
- Use Flexbox for the Experience and Connect sections

<!--
Don't walk through every checkbox. The goal is to give students a mental map of the work.
Point out that Skills and Projects will be intentionally empty for now — that content comes
in later lessons when students use JavaScript to populate those sections dynamically.
-->

---

# Tips

1. **Make one change at a time** — save and refresh before adding the next rule
2. **Use DevTools to experiment** — right-click any element → Inspect → try CSS live
3. **Colorful borders are your friend** — add `border: 2px solid red` to see any box
4. **The path in `href` must be exact** — `css/index.css`, not `index.css`
5. **Stuck on a property?** Ask an AI for hints, not answers:

> "Explain what `flex-wrap` does and give me one example."

<!--
The path tip (#4) is worth emphasizing verbally — it's the single most common setup error.
DevTools CSS editing (tip #2) is powerful: students can try values live without touching their file,
then copy what works into their actual CSS.
-->

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel writing CSS rules and using Flexbox?

### Before next session:
- Complete the **lesson materials** (Odin Project or Scrimba)
- Style your portfolio with `index.css`
- Add the `<nav>`, **Skills**, and **Projects** sections
- Post questions in the **Slack** `#discussion` channel anytime

<!--
If several students rate themselves 1 or 2, take a moment to normalize it:
"CSS has a steep learning curve at first. The more you experiment, the more it clicks.
Every professional developer uses DevTools and Google constantly — that is not cheating."
-->

---

# Resources

| Resource | What it's for |
|----------|---------------|
| Odin Project — Intro to CSS | Selectors, properties, the cascade |
| Odin Project — The Box Model | Padding, margin, border |
| Odin Project — Intro to Flexbox | Flex containers and items |
| Scrimba — HTML & CSS Crash Course | Video walkthroughs |
| CSS-Tricks: A Guide to Flexbox | Visual flexbox reference |
| MDN CSS Basics | Property lookup and docs |

> **Next week:** The DOM API — using JavaScript to make your page interactive!

<!--
CSS-Tricks Flexbox Guide (css-tricks.com/snippets/css/a-guide-to-flexbox/) is especially
useful for students who are visual learners. It has diagrams for every flex property.
-->

---

<!-- _class: title -->

# Great work today!

## Your portfolio is starting to come alive.

Questions? Reach out on Slack anytime.
