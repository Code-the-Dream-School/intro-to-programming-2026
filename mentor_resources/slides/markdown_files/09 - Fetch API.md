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
  Mentor 1 leads the Explore section (slides 3–15).
  Mentor 2 leads the Apply section (slides 16–26).
  Both mentors stay on screen throughout.
  Mentor 2 can field questions and paste code into chat during Explore.

Speaker notes appear in comment blocks like this one.
In Marp presenter mode, notes display in your presenter panel — students do not see them.
-->

<!-- _class: title -->

# Lesson 9: Fetch API

## Intro to Programming — Code the Dream

---

# Session Overview

**By the end of this session, you will be able to:**

- Explain what an API is and why developers use them
- Use `fetch()` to request data from a server
- Handle a server response using `.then()` and `.catch()`
- Write an `async/await` function to do the same thing
- Display fetched data on a web page using the DOM

<!--
Mentor 1 leads from here.
Quick framing before diving in: ask students "Has anyone used a weather app or checked a sports score online?" That data is fetched from an API — same concept as today.
-->

---

<!-- _class: section-break -->

# Explore

---

# What Is an API?

**API** stands for **Application Programming Interface**.

Think of it as a menu at a restaurant:
- The kitchen has data (the food)
- You send a request (your order)
- The kitchen sends back a response (your meal)

You do not need to know how the kitchen works — just how to order.

> In web development, APIs let your code ask a server for data.

<!--
Keep this analogy brief — just 30–45 seconds.
The goal is to lower anxiety. Students often think APIs are scary. They are just structured requests and responses.
Connect to the assignment: the GitHub API is the "kitchen" — it has data about repos, and fetch() is how we order it.
-->

---

# What Is JSON?

**JSON** stands for **JavaScript Object Notation**.

It is the most common format for API data.

```json
{
  "name": "intro-to-programming",
  "language": "JavaScript",
  "private": false
}
```

- It looks like a JavaScript object, but it is a **string**
- We use `response.json()` to convert it into real JavaScript data

<!--
Students often confuse JSON with a regular JS object. The key difference: JSON is always a string when it travels over the network. response.json() parses it into usable data.
You can show a quick analogy: a letter arrives in an envelope (string). You open it and read it (parse it). Now it is useful.
-->

---

# What Is `fetch()`?

`fetch()` is a built-in browser function that sends a request to a server.

```javascript
fetch("https://api.github.com/users/octocat/repos")
```

- The URL tells fetch **where to send the request**
- By default, fetch sends a **GET** request — asking for data
- `fetch()` returns a **Promise** — the response will arrive later

> `fetch()` is available in every major browser. No install needed.

<!--
Emphasize "arrives later" — this is the whole reason we need Promises and async/await.
A GET request just means "please give me data." Other methods (POST, PUT, DELETE) send or change data — students do not need those for this assignment.
-->

---

# Promises and `.then()`

`fetch()` does not give you data right away. It gives you a **Promise**.

A Promise is a placeholder that says: **"I will give you a value when I'm ready."**

We use `.then()` to say: **"When the data arrives, do this."**

```javascript
fetch("https://api.github.com/users/octocat/repos")
  .then(response => response.json())
  .then(data => console.log(data));
```

Each `.then()` receives the result of the step before it.

<!--
Students often struggle to visualize the chain. Use a simple real-world analogy: ordering a pizza online.
  Step 1: You place the order (fetch).
  Step 2: The pizza arrives (first .then — the raw response).
  Step 3: You open the box and eat it (second .then — parsed data you can use).
-->

---

# Handling Errors with `.catch()`

What happens if the request fails? Use `.catch()`.

```javascript
fetch("https://api.github.com/users/octocat/repos")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error("Something went wrong:", error));
```

`.catch()` runs if **any step in the chain** throws an error.

> Always include `.catch()`. Network requests can fail for many reasons.

<!--
Common student question: "Why do we need catch? Doesn't the browser show an error?"
Answer: the browser shows an error in the console, but your users won't see that. catch() lets you show a friendly message on the page instead.
-->

---

# Checking `response.ok`

`.catch()` only handles **network failures** (no connection, DNS errors).

If the server responds with an error code (like 404), `.catch()` won't run.

```javascript
fetch("https://api.github.com/users/octocat/repos")
  .then(response => {
    if (!response.ok) {
      throw new Error("Request failed: " + response.status);
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

Check `response.ok` to catch server-side errors too.

<!--
response.ok is true when the status code is 200–299 (success range).
A 404 means the URL was valid but the resource was not found — the network worked fine, so .catch() would not fire unless we throw manually.
This is directly relevant to the assignment's error-handling step.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**What does `fetch()` return immediately when you call it?**

A) The data from the server

B) A Promise

C) A JSON string

D) `undefined`

<!--
Answer: B.
This is the most important conceptual point of the lesson. fetch() is asynchronous — the data is not there yet when the line runs. It returns a Promise as a placeholder.
If students pick A, gently ask: "How long does a network request take? Can JavaScript know the answer instantly?"
-->

---

# `async` and `await`

`async/await` is a cleaner way to write the same fetch logic.

```javascript
async function fetchRepos() {
  const response = await fetch(
    "https://api.github.com/users/octocat/repos"
  );
  const data = await response.json();
  console.log(data);
}

fetchRepos();
```

- `async` marks the function as asynchronous
- `await` pauses the function until the Promise resolves

<!--
Key idea: await only pauses *inside* the async function. Code outside the function keeps running.
This connects to the lesson's predict-then-check exercise: "A", "C", "B" is the output order because C logs before the await resolves.
Students who have seen .then() chains will often prefer async/await once they see it — reassure them both styles are valid and widely used.
-->

---

# `try...catch` with `async/await`

Use `try...catch` for error handling — it replaces `.catch()`.

```javascript
async function fetchRepos() {
  try {
    const response = await fetch(
      "https://api.github.com/users/octocat/repos"
    );
    if (!response.ok) throw new Error("Request failed");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}
```

<!--
The structure mirrors .then()/.catch() exactly — just different syntax.
try = the optimistic path (things go right)
catch = the fallback path (things go wrong)
Students do not need to memorize both styles right now. The assignment uses .then() chains, so focus the demo there. async/await is shown here for completeness and because the lesson materials cover it.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**You write `await fetch(url)` inside an `async` function. What happens?**

A) JavaScript throws an error — `await` is not allowed inside functions

B) The function pauses at that line until the server responds, then continues

C) The rest of your page freezes while waiting for the response

D) `fetch()` runs but the result is ignored

<!--
Answer: B.
Common wrong answer: C. Clarify that only the async function pauses — the rest of the page (other event listeners, animations, etc.) keeps running normally. This is what makes async/await non-blocking.
-->

---

# From Data to the Page

Once you have data, use the DOM to display it.

```javascript
const projectList = document.querySelector("#projects ul");

data.forEach(function(repo) {
  const item = document.createElement("li");
  item.textContent = repo.name;
  projectList.appendChild(item);
});
```

This is loops + DOM — skills you already have!

<!--
Students often feel overwhelmed by fetch but then realize the "display" step is just createElement and appendChild — things they already know from Lesson 7.
Point this out explicitly: "You already know how to do the second half of this assignment."
-->

---

<!-- _class: cfu -->

# Check for Understanding

**Which line actually adds a new item to the visible page?**

```javascript
const item = document.createElement("li");
item.textContent = repo.name;
projectList.appendChild(item);
```

A) Line 1 — `createElement` creates it on the page

B) Line 2 — setting `textContent` makes it visible

C) Line 3 — `appendChild` inserts it into the DOM

D) None — you also need `document.write()`

<!--
Answer: C.
Common misconception: createElement creates the element in memory, but it is not on the page until you append it somewhere. Line 1 is like building a piece of furniture in your garage — it exists, but it is not in your house yet. Line 3 is moving it inside.
-->

---

<!-- _class: section-break -->

# Apply

<!--
Mentor 2 leads from here (suggested).
Before this slide: open your browser console (Chrome/Edge: F12 or right-click → Inspect → Console) and have your index.js file open in your editor.
The Core Activity mirrors the assignment exactly — students should follow along in their own files if possible.
-->

---

# Core Activity: Fetch Your GitHub Repos

We will build this together, step by step.

**Open two things:**
1. Your `index.js` file in your code editor
2. Your browser console (right-click anywhere → Inspect → Console)

We will test in the console first, then move the code into `index.js`.

<!--
Mentor 2: Do the demo yourself, live, in the console. Do not paste pre-written code — type it in real time so students can follow at your pace.
If a student suggests something that has a bug, type it anyway and let the group see the result. Real debugging > perfect code.
-->

---

# Step 1 — Test in the Console

Paste this into your browser console:

```javascript
fetch("https://api.github.com/users/octocat/repos")
  .then(response => response.json())
  .then(data => console.log(data));
```

**What do you see?**

- Try expanding one object in the console
- Find the `name` property — that is what we will display

<!--
Use "octocat" (GitHub's own demo account) so everyone sees the same data, regardless of their own GitHub setup.
Point out the response is an array of objects. Each object is one repo. The name property is what the assignment asks students to display.
Ask: "What other properties do you see? star count? language? description?" This sparks curiosity.
-->

---

# Step 2 — Add Error Checking

Let's also check that the response was successful:

```javascript
fetch("https://api.github.com/users/octocat/repos")
  .then(response => {
    if (!response.ok) {
      throw new Error("Request failed");
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error("Error:", error));
```

**Try it:** Change `octocat` to a fake username. What happens?

<!--
This directly mirrors the assignment's "Handling errors" step.
When students use a fake username, the GitHub API returns a 404 response. response.ok is false, so the error is thrown and caught. The console should show "Error: Request failed".
This is a great moment to explain WHY error handling matters — imagine this is a real portfolio site and the API call quietly fails with no message to the user.
-->

---

# Step 3 — Display Repos on the Page

Now let's move the code into `index.js` and show the repos on your portfolio.

```javascript
const projectSection = document.getElementById("projects");
const projectList = projectSection.querySelector("ul");

fetch("https://api.github.com/users/YOUR_USERNAME/repos")
  .then(response => response.json())
  .then(function(repositories) {
    for (let i = 0; i < repositories.length; i++) {
      const project = document.createElement("li");
      project.textContent = repositories[i].name;
      projectList.appendChild(project);
    }
  })
  .catch(error => console.error("Error:", error));
```

<!--
Replace YOUR_USERNAME with your own GitHub username during the demo.
Use a for loop (not forEach) to match the assignment instructions exactly.
Note the two-step DOM selection: first get the section by ID, then query within it for the ul. This matches the assignment task list step by step.
Save and refresh — your repos should appear in the Projects section of the portfolio.
-->

---

# Step 4 — Check It Works

Save your file and refresh your portfolio in the browser.

You should see:
- Your repository names listed under the Projects heading
- No errors in the console

**Zoom chat:** How many repos showed up?

> If you see fewer than expected — GitHub's API returns 30 repos by default. That is normal.

<!--
Common issues at this step:
  - Blank list: the ul element might have a different ID or structure — check the HTML
  - 401 or 403 error: GitHub rate-limiting. Try a different username (octocat is safe to use)
  - "Cannot read properties of null": querySelector returned null — the selector is wrong
Encourage students to open the console and read the error message before asking for help.
-->

---

<!-- _class: section-break -->

# Extension Activity

*Only if time allows — this is optional.*

<!--
Only move here if you have at least 10 minutes left and students seem confident with the core activity.
This is a good challenge for students who finish the core activity quickly.
-->

---

# Extension — Fetch a Different API

Try fetching from a public API that does not require authentication.

```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

**Challenge:** Can you display the `title` of the post on the page?

**Harder:** Fetch all posts (`/posts`) and show the first 5 titles in a list.

<!--
jsonplaceholder.typicode.com is a free, reliable fake REST API — great for experimenting.
The "harder" challenge requires slicing the array: data.slice(0, 5).forEach(...)
This is a good bridge to the open API project in Lesson 10, where students choose their own API.
-->

---

# Assignment Preview

This week you will add **live GitHub data** to your portfolio:

| Step | Task |
|------|------|
| 1 | Fetch your repos from `api.github.com` |
| 2 | Parse the JSON response |
| 3 | Loop through repos and add each as a `<li>` |
| 4 | Handle errors with `.catch()` |
| 5 | Style the projects list in `index.css` |

> Also: review the **Portfolio Rubric** — the final project is coming up!

<!--
Do not walk through every step in detail — students have the written assignment.
Highlight step 4 (error handling) because students often skip it.
Mention the rubric briefly: the portfolio fetch is one of the four required JavaScript tasks.
-->

---

# Tips for the Assignment

1. **Test in the console first** — make sure your fetch works before adding DOM code
2. **Check `response.ok`** — a 404 will not trigger `.catch()` on its own
3. **Use your exact GitHub username** — capitalization matters
4. **Read the error message** — the console tells you what went wrong
5. **Stuck on the for loop?** It is the same pattern from the Arrays lesson

> Ask for hints, not answers:
> "Can you give me 3 hints without showing me the code?"

<!--
Tip 3 is a common gotcha — GitHub usernames are case-sensitive in the API URL.
Tip 5 is reassurance: the for loop and appendChild pattern from Lesson 7 is exactly what they need here.
-->

---

# Wrap-Up

**Zoom chat:** Rate your confidence from 1 to 5
> How comfortable do you feel using `fetch()` to get data?

### Before next session:
- Work through the **lesson materials** (Odin Project: JSON, APIs, Async/Await)
- **Fetch your GitHub repos** and display them on your portfolio
- Review the **Portfolio Rubric** — know what is required
- Post questions in **Slack** anytime

<!--
The confidence check helps mentors know who to follow up with during the week.
If most students rate 1–2, consider posting a short walkthrough video or offering a drop-in session before next week.
-->

---

# Resources

| Resource | What it's for |
|----------|---------------|
| Odin Project — JSON | Understanding the data format |
| Odin Project — Working with APIs | How HTTP requests work |
| Odin Project — Async and Await | async/await deep dive |
| Scrimba — Make Network Requests | Video: fetch in action |
| MDN — Using Fetch | Full reference with examples |
| jsonplaceholder.typicode.com | Free fake API for practice |

> **Next week:** Open API Project — choose your own API!

---

<!-- _class: title -->

# Great work today!

## Your portfolio now pulls live data from the web.

Questions? Reach out on Slack anytime.
