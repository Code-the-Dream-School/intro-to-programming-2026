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
  One mentor leads the Explore section (slides 3–14).
  The other leads the Apply section (slides 15–25).
  Both mentors stay on screen throughout. The second mentor can support questions during Explore.

Speaker notes (mentor-only guidance) appear in comment blocks like this one.
In Marp presenter mode, notes display in your presenter panel.
-->

<!-- _class: title -->

# Lesson 10: Open API

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Explain what an open API is and why developers use them
- Read basic API documentation to find an endpoint and a URL
- Explain what an API key is and how to use one safely
- Make a `fetch()` call to a public API and display the response
- Plan a two-endpoint API page that connects to your portfolio

---

<!-- _class: section-break -->

# Explore

---

# What Is an Open API?

An **API** (Application Programming Interface) lets your code talk to another service.

An **open API** (or public API) is free to use — no payment required.

Examples you may have heard of:
- A weather app gets its data from a weather API
- A map uses a maps API
- This week, **you** will fetch real data and show it on a page

> APIs send data back as JSON — the same format you've already seen with `fetch()`.

<!--
Connect to what students already know. If they completed Lesson 9, they've used fetch().
If any students missed Lesson 9, reassure them: the pattern is the same every time.
-->

---

# API Options This Week

Pick one that interests you:

| API | What it has |
|-----|-------------|
| Open-Meteo | Weather data |
| Swapi.Tech | Star Wars characters and films |
| ARTIC | Artwork from the Art Institute of Chicago |
| TheDogAPI / TheCatAPI | Dog and cat images |
| Marvel | Marvel characters and comics |
| API-Sports (Soccer) | Football stats |

> Each API has documentation — a guide that shows you what data is available and how to ask for it.

<!--
Let students call out which ones sound interesting. The goal is curiosity, not commitment.
They will finalize their choice during the Apply section.
-->

---

# Reading API Documentation

Before writing any code, read the docs. Look for:

1. **Base URL** — where all requests start (e.g. `https://api.artic.edu/api/v1`)
2. **Endpoints** — the specific paths that return data (e.g. `/artworks`)
3. **Parameters** — options you can add to filter or limit results
4. **Response format** — what fields come back in the JSON

> TheDogAPI and TheCatAPI include ready-to-use fetch examples in their docs — great starting points.

<!--
Show a documentation page on screen if possible (ARTIC or TheDogAPI work well).
Point out the base URL and one endpoint. Normalize the idea that reading docs is a normal part of the job.
-->

---

# Making a Fetch Call

The pattern is the same as Lesson 9:

```javascript
fetch("https://api.artic.edu/api/v1/artworks?limit=3")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.log("Error:", error));
```

**Try this in your browser console right now.**

Open the browser console:
- **Chrome / Edge:** Right-click → Inspect → Console
- **Firefox:** Right-click → Inspect → Console

<!--
Paste the URL above and run it live so students can see a real API response.
Ask: "What do you notice about the shape of the data?" before moving on.
-->

---

# Reading the Response

API responses are objects. You have to dig in to find the data you want.

```javascript
fetch("https://api.artic.edu/api/v1/artworks?limit=3")
  .then(response => response.json())
  .then(data => {
    let artworks = data.data;      // the array of results
    let title = artworks[0].title; // first artwork's title
    console.log(title);
  });
```

> If you see `[object Object]` on the page, that means you need to go deeper into the object.

<!--
The "[object Object]" problem is extremely common. Mentioning it here inoculates students.
The lesson materials include an AI prompt specifically for this error — point students to it.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**An API returns this JSON. How do you access the dog's name?**

```javascript
{
  "dog": {
    "name": "Biscuit",
    "breed": "Labrador"
  }
}
```

A) `data.name`

B) `data.dog.name`

C) `data["Biscuit"]`

D) `data[0].name`

<!--
Answer: B.
Walk through why: data is the whole object, data.dog gets inside the "dog" key, data.dog.name gets the value.
Wrong answers to address: A skips the "dog" layer; D treats an object like an array.
-->

---

# What Is an API Key?

Some APIs require a **key** — a unique code that identifies your app.

Think of it like a library card: the library uses it to track who is borrowing books.

```javascript
const API_KEY = "your_key_here";

let url = `https://api.example.com/data?api_key=${API_KEY}`;

fetch(url)
  .then(response => response.json())
  .then(data => console.log(data));
```

> For this class, storing the key as a `const` in your JS file is fine.

<!--
The Marvel API requires a key. Open-Meteo, ARTIC, TheDogAPI and TheCatAPI do not.
Students choosing Marvel will need to sign up at developer.marvel.com.
Reinforce: in a real job, keys go in environment variables — never committed to GitHub.
-->

---

# What Happens Without a Key?

If a key is required and you forget it, the server sends back an error — not data.

Common responses:
- **401 Unauthorized** — no key provided
- **403 Forbidden** — key is wrong or expired

```javascript
fetch("https://api.example.com/data") // no key!
  .then(response => {
    console.log(response.status); // 401
    return response.json();
  })
  .then(data => console.log(data)); // error message
```

> Always check `response.status` if you are not getting data back.

<!--
This connects to the AI learning prompt in the lesson: students are asked to predict
what happens without a key, then test it. Encourage them to try this.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**You make a fetch call and get a `401` status code. What does that mean?**

A) The request worked — `401` is the number of results

B) The server is down and you should try again later

C) The server rejected the request because no valid API key was included

D) Your internet connection is too slow

<!--
Answer: C.
401 = Unauthorized. Reinforce that HTTP status codes are part of the API contract.
Students are used to seeing 200 (success) — 401 and 404 come up constantly in real projects.
-->

---

# Two Endpoints Required

Your assignment requires **two separate fetch calls** to two different endpoints.

**Example with Open-Meteo:**
- **Call 1:** Get the current temperature
- **Call 2:** Get the wind speed

Each button or nav link in your HTML should trigger a **different** fetch.

> Do not fetch everything at once and hide parts of it. Make two real API calls.

<!--
Students sometimes try to do one fetch and split the result into two views.
That does not meet the rubric. Two calls = two endpoints.
If using TheDogAPI: Call 1 could be a random dog image, Call 2 could be a list of breeds.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**A student writes one fetch call and uses JavaScript to show/hide different parts of the response. Does this meet the two-endpoint requirement?**

A) Yes — the user sees two different views

B) Yes — one fetch call can return all the data needed

C) No — two endpoints means two separate fetch calls to two different API URLs

D) It depends on which API they are using

<!--
Answer: C.
This is a rubric question. Be direct: two endpoints = two fetch() calls to two different URLs.
Having one call with two pieces of data from the same response does not count.
-->

---

<!-- _class: section-break -->

# Apply

<!--
Second mentor leads from here (suggested).
You will run a live coding demo tied directly to the assignment.
Before this slide: have a code editor or browser console ready to share your screen.
Suggested API for the demo: ARTIC (no key needed, clear JSON structure).
-->

---

# Core Activity: Let's Build an API Page

We will build a minimal Open API page step by step — **tell me what to type!**

We will use the **ARTIC API** (Art Institute of Chicago) — no key needed.

**Goal:** Two buttons, two fetch calls, results shown on the page.

> This is the same structure you will use in your assignment.

<!--
You type; students direct you. If something breaks, leave it and debug together.
Live errors are more educational than perfect code.
This demo is intentionally minimal — students will customize it for their own API.
-->

---

# Step 1 — The HTML Shell

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Art Explorer</title>
  <link rel="stylesheet" href="css/openapi.css">
</head>
<body>
  <nav>
    <a href="index.html">Portfolio</a>
    <button id="btn-artworks">Browse Artworks</button>
    <button id="btn-artists">Browse Artists</button>
  </nav>
  <main id="display"></main>
  <script src="js/openapi.js"></script>
</body>
</html>
```

<!--
Point out the nav link back to index.html — this is a rubric requirement.
Also note the two buttons: each will trigger a different fetch call.
-->

---

# Step 2 — First Fetch Call

```javascript
const display = document.getElementById("display");

function fetchArtworks() {
  fetch("https://api.artic.edu/api/v1/artworks?limit=5")
    .then(response => response.json())
    .then(data => {
      let artworks = data.data;
      display.innerHTML = "";
      artworks.forEach(art => {
        display.innerHTML += `<p>${art.title}</p>`;
      });
    })
    .catch(error => {
      display.innerHTML = "<p>Something went wrong.</p>";
    });
}
```

<!--
Walk through each line. Highlight: data.data (the array is nested), forEach, innerHTML.
Ask students: "What do you think .catch() does?" before explaining.
-->

---

# Step 3 — Second Fetch Call

```javascript
function fetchArtists() {
  fetch("https://api.artic.edu/api/v1/agents?limit=5")
    .then(response => response.json())
    .then(data => {
      let artists = data.data;
      display.innerHTML = "";
      artists.forEach(artist => {
        display.innerHTML += `<p>${artist.title}</p>`;
      });
    })
    .catch(error => {
      display.innerHTML = "<p>Something went wrong.</p>";
    });
}
```

> This is the **second endpoint** — a different URL, a different fetch, different data.

<!--
Ask: "What is different between this function and the previous one?"
Answer: the URL and the variable names. The structure is the same — this is the pattern.
-->

---

# Step 4 — Connect the Buttons

```javascript
document
  .getElementById("btn-artworks")
  .addEventListener("click", fetchArtworks);

document
  .getElementById("btn-artists")
  .addEventListener("click", fetchArtists);
```

**Test it:** Click each button. Do you see different data each time?

<!--
If something does not work, debug together. Common issues:
- Typo in the element ID
- Script tag above the elements in the HTML (not at the bottom of <body>)
- CORS error (unlikely with ARTIC, but possible with some APIs)
-->

---

<!-- _class: section-break -->

# Extension Activity

*Only if students are ready and time allows.*

---

# Extension — Display Rich Data

Instead of plain text, display a card with multiple fields.

```javascript
artworks.forEach(art => {
  display.innerHTML += `
    <div class="card">
      <h2>${art.title}</h2>
      <p>Artist: ${art.artist_title || "Unknown"}</p>
      <p>Year: ${art.date_display || "N/A"}</p>
    </div>
  `;
});
```

**Challenge:** Add an image using the ARTIC image URL format:
`https://www.artic.edu/iiif/2/{image_id}/full/400,/0/default.jpg`

<!--
The ARTIC image URL requires the image_id field from the response. Students need to
log the data object and find that field themselves — good practice for reading JSON.
-->

---

# Assignment Preview

This week you will build your **Open API page**:

- [ ] New `openapi.html`, `openapi.css`, and `openapi.js` files
- [ ] A nav link from your portfolio (`index.html`) to the new page
- [ ] A nav link on the new page back to your portfolio
- [ ] Two separate `fetch()` calls to two different endpoints
- [ ] Both results displayed on the page
- [ ] Error handling with `.catch()`
- [ ] Review the **Open API Rubric** before submitting

---

# Tips for the Assignment

1. **Choose your API first** — read the docs before writing any code
2. **Test in the browser console** — paste a fetch call and explore the response
3. **Log the whole response first** — `console.log(data)` before accessing properties
4. **If you see `[object Object]`** — you need to go one level deeper
5. **Stuck?** Use the AI prompts from the lesson materials to get hints without getting answers

> "Can you ask me 3 questions that will help me figure out how to access the specific properties inside the returned object?"

<!--
The AI prompts in section 10.3 of the lesson are genuinely useful. Point students to them specifically.
The "[object Object]" tip addresses the single most common error for this assignment.
-->

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel making a fetch call and reading the response?

### Before next session:
- **Choose your API** and read its documentation
- **Build your Open API page** (HTML, CSS, JS)
- Fetch from **two endpoints** and display both results
- Add **error handling** with `.catch()`
- Review the **Open API Rubric**
- Post questions in the **Slack** `#discussion` channel anytime

---

# Resources

| Resource | What it's for |
|----------|---------------|
| Open-Meteo | Free weather API — no key needed |
| ARTIC API | Free art data API — no key needed |
| TheDogAPI / TheCatAPI | Free — includes fetch examples in docs |
| Swapi.Tech | Free Star Wars data API |
| Marvel API | Requires a free API key |
| MDN: Using Fetch | Reference for the fetch pattern |
| Open API Rubric | Linked in your lesson materials |

> **Next week:** Final Project — putting it all together!

---

<!-- _class: title -->

# Great work today!

## You're building something entirely your own.

Questions? Reach out on Slack anytime.
