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

# Lesson 10: Open API Project

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

If you could pull data from any source and display it on a web page, what would you build?

A weather dashboard? A Star Wars fan page? A dog gallery?

<!--
This gets students excited about the creative freedom of this project.
Let several students share — it helps the quieter ones get ideas.
-->

---

# What You'll Learn This Week

- **Open APIs** — free data you can use
- **API keys** — authentication basics
- **Multiple endpoints** — fetching different data sets
- **Project planning** — structuring a multi-page site
- **Creative freedom!** — design it your way

---

# I Do: What Is an Open API?

An **open API** provides free public data you can use in your projects.

You've already used one — the GitHub API!

This week, you'll pick a new API and build a **second page** for your portfolio.

---

# I Do: API Options

Pick one that interests you:

- **Open-Meteo** — weather data
- **Swapi.Tech** — Star Wars info
- **Marvel** — Marvel characters and comics
- **ARTIC** — artwork from the Art Institute of Chicago
- **TheDogAPI / TheCatAPI** — dog and cat images
- **API-Sports (Soccer)** — football stats

> Each has documentation showing what data is available.

---

# I Do: API Keys

Some APIs require a **key** to identify you:

```javascript
const API_KEY = "your_key_here";
let url = `https://api.example.com/data?key=${API_KEY}`;
```

An API key is like a library card — it tracks who's using the service.

> For this class, it's fine to store the key as a constant in your JS file.

---

# I Do: Two Endpoints Required

Your project must fetch from **2 different endpoints**.

Example with a weather API:
- **Endpoint 1:** Current temperature
- **Endpoint 2:** Weather conditions/forecast

Each navigation link triggers a **separate GET request** — don't fetch everything at once.

---

# I Do: Project Structure

You'll add a second page to your portfolio:

```
your-project/
├── index.html          ← portfolio
├── openapi.html        ← new page
├── css/
│   ├── index.css
│   └── openapi.css     ← new styles
└── js/
    ├── index.js
    └── openapi.js      ← new script
```

Link between pages using `<nav>`:

```html
<a href="openapi.html">Open API</a>
```

---

# I Do: Planning Your Page

Before coding, plan:

1. **Which API** will you use?
2. **What 2 endpoints** will you call?
3. **What data** will you display from each?
4. **How will the user navigate** between them?
5. **How will you handle errors?**

> Write this out as pseudocode or notes before touching code.

---

<!--
Transition to We Do:
This session is more about planning and exploring than live coding.
Help students pick an API and understand the documentation.
-->

# We Do: Explore an API Together (15-20 min)

Let's pick one API and explore it as a group.

---

# We Do: Read the Documentation

**Pick an API** (let the group vote or pick one for the demo).

Open the documentation and look for:
- The **base URL**
- Available **endpoints** (what data can you get?)
- Whether you need an **API key**
- The **response format** (what fields come back?)

---

# We Do: Test in the Console

Try a fetch right in the browser console:

```javascript
fetch("https://api.artic.edu/api/v1/artworks?limit=5")
    .then(response => response.json())
    .then(data => console.log(data));
```

**Explore the response together:**
- What does the data look like?
- What fields are useful?
- How would you display this?

---

# We Do: Plan the Page

Let's sketch out what this page could look like:

1. **Navigation** — links to each endpoint view + back to portfolio
2. **Display area** — where the fetched data appears
3. **Two buttons/links** — each triggers a different fetch

**Ask the group:** How would you structure the HTML?

<!--
You can whiteboard or screen-share a simple wireframe.
The goal is to get students thinking about structure before coding.
-->

---

# We Do: Starter Code

Here's a skeleton to get started:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My API Project</title>
    <link rel="stylesheet" href="css/openapi.css">
</head>
<body>
    <nav>
        <a href="index.html">Portfolio</a>
        <a href="#" id="btn-endpoint1">View 1</a>
        <a href="#" id="btn-endpoint2">View 2</a>
    </nav>
    <main id="display"></main>
    <script src="js/openapi.js"></script>
</body>
</html>
```

---

<!--
Transition to You Do:
This is mostly a planning session. Students should leave with
an API chosen and a rough plan.
-->

# You Do: Plan Your Project (5-10 min)

Spend a few minutes answering these questions:

1. Which **API** will you use?
2. What **2 endpoints** will you call?
3. What **data** will you display from each?
4. Write **pseudocode** for one of your fetch calls.

> If you finish early, try fetching from your API in the console!

---

# You Do: Share Out

**Who wants to share their plan?**

- Which API did you pick?
- What will your two views show?

---

# Assignment Preview

This week you'll build your **Open API page**:

- New HTML, CSS, and JS files
- Navigation between your portfolio and the new page
- **2 separate fetch calls** to different endpoints
- Display the data on the page
- Error handling
- Review the **Open API Rubric**

---

# Open API Rubric Highlights

- Linked from your portfolio nav
- Nav bar to get back to your portfolio
- **2 endpoints** with separate GET requests
- Navigation between the two data views
- Code runs without errors
- Clean, readable code
- Effective styling

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel planning an API project?

### Before next session:
- **Choose your API** and read its documentation
- **Build your Open API page** (HTML, CSS, JS)
- Fetch from **2 endpoints** and display the data
- Review the **Open API Rubric**
- Reach out on **Slack** if you get stuck!

---

# Resources

- **API Options:** Open-Meteo, Swapi.Tech, Marvel, ARTIC, TheDogAPI, TheCatAPI, Soccer API
- **MDN:** [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
- **Open API Rubric:** linked in your lesson materials

> **Next week:** Final Project — putting it all together!

---

<!-- _class: title-slide -->

# Great work this week!

## You're building something entirely your own.

Questions? Reach out on Slack anytime.
