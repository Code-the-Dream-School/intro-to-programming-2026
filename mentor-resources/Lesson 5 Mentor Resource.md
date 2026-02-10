# Lesson 5 Mentor Resource: HTML Basics

## Lesson Overview
This week marks a major transition: students move from pure JavaScript exercises to building web pages. They learn about how the web works, HTML elements, tags, attributes, the HTML boilerplate, headings, paragraphs, lists, links, images, and semantic elements like `<section>`. They also install Visual Studio Code (or a similar IDE). The assignment has students create an `index.html` file for a personal portfolio with their name, an About section, an Experience section, and a Connect section with social media links.

This is the beginning of the portfolio project that students will build on for the rest of the course. It's exciting for students because they can finally see something visual in the browser, but it's also a big shift from the JavaScript coding exercises they've been doing.

---

## Group Mentor Sessions

### Explore Session

**Warm-Up** (5-10 minutes)
- Ask: "Have you ever looked at the source code of a website? What did you notice?"
- Or: "What's your favorite website? What do you think makes it look the way it does?"

**I Do** (~15 minutes)
- Give a brief overview of how the web works: browsers, servers, HTML/CSS/JS as the building blocks.
- Demo creating a basic HTML file from scratch: `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`. Open it in a browser to show the result.
- Walk through common elements: `<h1>` through `<h6>`, `<p>`, `<ul>/<li>`, `<a>`, `<img>`. Show the difference between elements that need closing tags and self-closing elements.

**We Do** (15-20 minutes)
- Build a simple page together: ask students what content to include (e.g., a page about the class). Have students suggest which HTML elements to use for each piece of content.
- Discussion: "What's the difference between the `<head>` and the `<body>`? What goes in each?"
- If using breakout rooms: give each group a list of content (a heading, a paragraph, 3 list items, and a link) and have them write the HTML. Rotate and ask "Did you remember to close your tags?"

**You Do** (15-20 minutes)
- Have students start setting up their `index.html` with the boilerplate code and their name in an `<h1>`.
- Challenge: "Can you add a link to your GitHub profile using an `<a>` tag?"

**Wrap-Up** (5-10 minutes)
- Ask: "What was it like seeing your code show up in the browser for the first time?"
- Preview next week: CSS — they'll make their pages look polished with colors, fonts, and layout.
- Remind students about VS Code extensions (like Live Server) that auto-refresh the browser.

---

### Apply Session

**Warm-Up** (5-10 minutes)
- Ask: "How is writing HTML different from writing JavaScript? What feels easier or harder?"
- Quick question: "What does the `<a>` tag do, and what attribute does it need to create a link?"

**I Do** (~15 minutes)
- Pull up the assignment and walk through the boilerplate structure: DOCTYPE, html, head (title, meta), body.
- Demo creating the About section with an `<h2>` and a `<p>`, wrapping it in a `<section>` element with an `id` attribute.
- Show how to view the file in the browser and use the Live Server extension.

**We Do** (15-20 minutes)
- Work through the Experience section together: creating a `<ul>` with `<li>` items. Ask students: "What are some experiences you want to highlight?"
- Work through the Connect section: creating links with `<a>` tags. Show how `href` works and demo linking to a real URL.

**You Do** (15-20 minutes)
- Give students time to complete their `index.html` file. Encourage them to open it in the browser frequently to check their work.
- For students who finish early: encourage the stretch goal of adding images or a navigation menu.

**Wrap-Up** (5-10 minutes)
- Ask: "Does everyone's page show up in the browser? Does anything look different than you expected?"
- Remind students about the Git workflow: they'll need to push their work and create a pull request.
- Point ahead: CSS next week — they'll transform their plain HTML into a styled page.

---

## 1:1 Session Guide

- **Build rapport**: This is an exciting week — students are building something visible. Celebrate their progress and ask them to show you their page.
- **Check understanding**: Ask the student to explain the structure of their HTML file. Can they identify the head vs. body? Do they understand what each element does?
- **Encourage independence**: If a student's page doesn't look right, have them use the browser's "View Source" or developer tools to compare what they wrote with what the browser is rendering. Ask: "Are all your tags closed? Is everything inside the `<body>` tags?"
- **Goal-setting**: Help the student plan what content they want in each section. Having a plan before coding helps.
- **Common sticking points this week**:
  - Forgetting to close tags (especially `</section>`, `</ul>`, `</li>`)
  - Mixing up `<head>` and `<body>` — putting visible content in the head
  - The `<a>` tag: forgetting the `href` attribute or using incorrect URL format
  - VS Code setup: installing extensions, opening files correctly
  - Understanding the file structure (where to save `index.html`)
