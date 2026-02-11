# Lesson 6 Mentor Resource: CSS Basics

**Resources:**
* [How to use this template, and tips on holding effective mentor sessions](https://github.com/reidrussom/intro-to-programming-2026/tree/main/mentor-resources)
* [CTD AI Reviewer](https://ai-review.codethedream.org/)
* [Link to slide decks](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides)

## Lesson Overview
This week students learn CSS: selectors, properties, the cascade, the box model (margin, padding, border), block vs. inline elements, positioning, and Flexbox. The assignment has students create a `css/index.css` file, link it to their HTML, and style their portfolio page. They also add a navigation bar, a "Skills" section (empty for now), and a "Projects" section (with an empty `<ul>` for later). They use Flexbox to lay out the Experience and Connect sections.

This is where the portfolio starts to come alive visually. Students often find CSS both exciting (they can see immediate results) and frustrating (things don't always go where expected). Flexbox especially can take time to click.

---

## Group Mentor Sessions

### Explore Session

**Warm-Up** (5-10 minutes)
- Ask: "When you look at a well-designed website, what catches your eye first? Colors? Layout? Fonts?"
- Or show two versions of the same HTML page — one unstyled, one with CSS — and ask: "What's the difference? How do you think this was done?"

**I Do** (~15 minutes) – **check out the [slides](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides) for this portion!**
- Demo linking a CSS file to HTML (the `<link>` tag in `<head>`).
- Show basic CSS syntax: selector, property, value. Change the `background-color` and `font-family` of the body.
- Walk through the box model: show how margin, padding, and border affect element spacing. Use the browser's developer tools to visualize it.

**We Do** (15-20 minutes)
- Discussion: "What's the difference between margin and padding? When would you use each?"
- Build a simple layout together: style a heading, a paragraph, and a list. Ask students to suggest colors, fonts, and spacing.
- Introduce Flexbox: create a container with three items and demonstrate `display: flex`, `justify-content`, and `align-items`. Ask students to predict what will happen as you change values.
- If using breakout rooms: give each group a simple HTML snippet and ask them to style it with at least 3 different CSS properties. Rotate and ask "What property would you change to add space between these items?"

**You Do** (15-20 minutes)
- Have students open their portfolio's `index.html` and create their `index.css` file. Challenge them to:
  1. Change the background color
  2. Change the font
  3. Add padding to their sections
- Share screens to see everyone's different designs.

**Wrap-Up** (5-10 minutes)
- Ask: "What CSS property was the most fun to play with? Which one was the most confusing?"
- Preview next week: the DOM API — using JavaScript to dynamically change HTML content.
- Encourage students to experiment and look at the CSS resources for inspiration.

---

### Apply Session

**Warm-Up** (5-10 minutes)
- Ask: "How is styling your portfolio going? What does your page look like so far?"
- Quick question: "What's Flexbox used for?"

**I Do** (~15 minutes)
- Pull up the assignment and demo creating the `css` folder and `index.css` file, then linking it.
- Walk through styling the Experience section with Flexbox, showing how to turn a list into a row/column layout.
- Show how to add a `<nav>` element with links to each section using `id` attributes and `#` links.

**We Do** (15-20 minutes)
- Work together to style the Connect section with Flexbox — turning the links into a horizontal row.
- Demo using the browser's developer tools to inspect elements, test CSS changes live, and troubleshoot layout issues.
- Ask students: "What happens if you add `display: flex` to an element that only has one child? What about three children?"

**You Do** (15-20 minutes)
- Give students time to work on their CSS styling. Circulate and help with specific issues.
- Tip: if students are struggling to visualize their layout, suggest they add temporary borders (`border: 2px solid red`) to sections so they can see where things are.

**Wrap-Up** (5-10 minutes)
- Quick show-and-tell: have 1-2 students share their screen to show their styled portfolio.
- Remind students to add the Skills and Projects sections (even though they'll be empty for now).
- Point ahead: DOM API — they'll use JavaScript to add content to their HTML dynamically.

---

## 1:1 Session Guide

- **Build rapport**: CSS can be subjective. Ask the student about their design choices — what look are they going for?
- **Check understanding**: Ask the student to explain the box model. Can they point to margin, padding, and border on their page using developer tools?
- **Encourage independence**: If something isn't laying out correctly, guide the student to use browser dev tools rather than giving them the CSS fix. Ask: "What does the element inspector show about this element's spacing?"
- **Goal-setting**: Help the student prioritize: the assignment has specific requirements (background color, font, padding, Flexbox layout). Make sure these are done before the student spends too much time on optional polish.
- **Common sticking points this week**:
  - CSS file not loading: incorrect `href` path in the `<link>` tag
  - Flexbox: not understanding the parent/child relationship (`display: flex` goes on the parent)
  - Margin collapse: unexpected spacing behavior between adjacent elements
  - Navigation links not jumping to sections: mismatched `id` values and `href="#id"` values
  - Understanding the difference between classes and IDs
