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

# Lesson 9: Fetch API

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

Where do you think the data on a weather app comes from? How does the app get today's forecast?

<!--
This connects to the idea of APIs — the weather app fetches
data from a server, just like students will do this week.
-->

---

# What You'll Learn This Week

- **JSON** — the data format of the web
- **Fetch API** — requesting data from a server
- **Promises in action** — `.then()` and `.catch()`
- **async/await** — a cleaner way to write async code
- **GitHub API** — fetching your own repositories!

---

# I Do: What Is JSON?

**JavaScript Object Notation** — a format for sending data.

```json
{
    "name": "intro-to-programming",
    "language": "JavaScript",
    "private": false
}
```

It looks like a JavaScript object, but it's a **string**. We parse it to use it as real data.

---

# I Do: What Is the Fetch API?

`fetch` lets you **request data from a server** using JavaScript.

```javascript
fetch("https://api.github.com/users/octocat/repos")
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error(error));
```

Three steps:
1. **fetch** — send the request
2. **.then** — handle the response
3. **.catch** — handle errors

---

# I Do: Breaking Down Fetch

```javascript
fetch("https://api.github.com/users/octocat/repos")
```
Sends a GET request to that URL.

```javascript
.then(response => response.json())
```
Converts the response to usable JSON data.

```javascript
.then(data => console.log(data))
```
Do something with the data (log it, display it, etc.).

```javascript
.catch(error => console.error(error))
```
If anything goes wrong, handle the error gracefully.

---

# I Do: async/await

A cleaner way to write the same thing:

```javascript
async function fetchRepos() {
    try {
        let response = await fetch(
            "https://api.github.com/users/octocat/repos"
        );
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}

fetchRepos();
```

`await` pauses until the promise resolves — reads like synchronous code!

---

# I Do: Fetch → Display on Page

Once you have data, use the DOM to show it:

```javascript
let projectList = document.querySelector("#projects ul");

data.forEach(function(repo) {
    let project = document.createElement("li");
    project.textContent = repo.name;
    projectList.appendChild(project);
});
```

This is just loops + DOM — skills you already have!

---

<!--
Transition to We Do:
- Ask: "What questions do you have about fetch?"
- Try running a fetch in the browser console live to show it works.
-->

# We Do: Fetch Data Together! (15-20 min)

Open your browser console. Let's try a live fetch.

---

# We Do: Fetch in the Console

Paste this into your browser console:

```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
    .then(response => response.json())
    .then(data => console.log(data));
```

**What comes back?**

<!--
Walk through the response object. Point out the id, title,
and body fields. This is real data from a real API.
-->

---

# We Do: Fetch GitHub Repos

Now let's fetch your actual GitHub repositories:

```javascript
fetch("https://api.github.com/users/YOUR_USERNAME/repos")
    .then(response => response.json())
    .then(repos => {
        repos.forEach(repo => console.log(repo.name));
    })
    .catch(error => console.error(error));
```

**Replace `YOUR_USERNAME` with your GitHub username.**

**Zoom chat:** How many repos showed up?

---

# We Do: Display Repos on the Page

In `index.js`, let's add your repos to the Projects section:

```javascript
fetch("https://api.github.com/users/YOUR_USERNAME/repos")
    .then(response => response.json())
    .then(repos => {
        let projectList = document.querySelector("#projects ul");
        repos.forEach(repo => {
            let project = document.createElement("li");
            project.textContent = repo.name;
            projectList.appendChild(project);
        });
    })
    .catch(error => console.error("Error:", error));
```

**Save and refresh.** Your repos appear on your portfolio!

---

# We Do: Error Handling

**Ask the group:** What happens if we misspell the username?

```javascript
.catch(error => console.error("Error:", error));
```

The `.catch()` block handles network errors. We should also check `response.ok`:

```javascript
.then(response => {
    if (!response.ok) {
        throw new Error("Request failed");
    }
    return response.json();
})
```

---

<!--
Transition to You Do:
Set a timer for 5-10 minutes.
-->

# You Do: Independent Practice (5-10 min)

Try **one** of these:

**A)** Open your browser console and fetch data from `jsonplaceholder.typicode.com/posts/1`.

**B)** Fetch your GitHub repos and log each repo name.

**C)** Display your repo names in the Projects section of your portfolio.

---

# You Do: Share Out

**Who wants to demo their fetch?**

- What data did you get back?
- Did you run into any errors?

---

# Assignment Preview

This week you'll add **real GitHub data** to your portfolio:

- Fetch your repos from the GitHub API
- Parse the JSON response
- Loop through repos and display them in the Projects section
- Add error handling with `.catch()`
- Style the projects list

> Also: review the **Portfolio Rubric** — the final project is coming up!

---

# Wrap-Up (5 min)

**Zoom chat:** Rate your confidence 1-5
> How comfortable do you feel using fetch to get data?

### Before next session:
- Work through the **lesson materials** (JSON, Fetch, async/await)
- **Fetch your GitHub repos** and display them on your portfolio
- Review the **Portfolio Rubric**
- Reach out on **Slack** if you get stuck!

---

# Resources

- **Odin Project:** JSON, Working with APIs, Async and Await
- **Scrimba:** Network Requests with fetch(), Promises, async-await
- **MDN:** [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)

> **Next week:** Open API project — your chance to get creative!

---

<!-- _class: title-slide -->

# Great work this week!

## Your portfolio now pulls live data from the web.

Questions? Reach out on Slack anytime.
