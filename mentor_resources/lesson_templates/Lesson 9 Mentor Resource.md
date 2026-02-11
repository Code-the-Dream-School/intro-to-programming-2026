# Lesson 9 Mentor Resource: Fetch API

**Resources:**
* [How to use this template, and tips on holding effective mentor sessions](https://github.com/reidrussom/intro-to-programming-2026/tree/main/mentor-resources)
* [CTD AI Reviewer](https://ai-review.codethedream.org/)
* [Link to slide decks](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides)

## Lesson Overview
This week students learn the Fetch API: making HTTP GET requests, working with JSON data, chaining `.then()` calls, handling errors with `.catch()`, and using `async/await` syntax. They also learn about the `response.json()` method and the `try/catch` pattern. The assignment has students fetch their own GitHub repositories using the GitHub API and display them in the Projects section of their portfolio. The lesson also points students to the portfolio rubric to start thinking about their final project.

This is where everything comes together: JavaScript, DOM manipulation, and async programming combine to create a dynamic web page that pulls in real data. It's a milestone moment for students.

---

## Group Mentor Sessions

### Explore Session

**Warm-Up** (5-10 minutes)
- Ask: "Have you ever used an app that shows data from somewhere else — like a weather app or a social media feed? Where do you think that data comes from?"
- Or review: "What's a promise? What are the three states it can be in?"

**I Do** (~15 minutes) - **check out the [slides](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides) for this portion!**
- Explain what an API is at a high level: a way for programs to request data from a server.
- Demo a `fetch` call in the browser console using a simple public API (like `https://jsonplaceholder.typicode.com/posts/1`).
- Walk through the chain: `fetch(url).then(response => response.json()).then(data => console.log(data))`.
- Show the same thing with `async/await` syntax and explain how it reads more like synchronous code.

**We Do** (15-20 minutes)
- Walk through the GitHub API URL together: `https://api.github.com/users/{username}/repos`. Have a student volunteer their username and fetch their repos live.
- Discussion: "What data came back? What properties does each repo object have?"
- If using breakout rooms: give each group a different public API endpoint (JSONPlaceholder, a dog/cat API) and have them make a fetch call and log the data. Rotate and ask "What did the response look like? What properties are useful?"

**You Do** (15-20 minutes)
- Have students fetch their own GitHub repos in the browser console and explore the returned data.
- Challenge: "Can you write a function that fetches the data and logs just the name of each repository?"

**Wrap-Up** (5-10 minutes)
- Ask: "What was it like seeing your own GitHub data come back from an API call?"
- Preview next week: Open API — they'll choose a public API and build a second page for their project.
- Remind students to review the portfolio rubric.

---

### Apply Session

**Warm-Up** (5-10 minutes)
- Ask: "Has anyone gotten their GitHub repos to display on their portfolio yet?"
- Quick question: "What's the difference between `.then()` and `async/await`? Are they doing the same thing?"

**I Do** (~15 minutes)
- Pull up the assignment and walk through the full flow:
  1. Write the `fetch` call to the GitHub API
  2. Chain `.then()` to parse the JSON
  3. Chain another `.then()` to loop through the repos and create DOM elements
  4. Add `.catch()` for error handling
- Show how to select the Projects section and append list items for each repo.

**We Do** (15-20 minutes)
- Work through the DOM manipulation portion together: creating `<li>` elements inside a loop and appending them to the `<ul>` in the Projects section.
- Debug a common issue together: "What happens if the username is wrong or the API is down?" Show what the `.catch()` handles.
- Ask students: "How could we also display the repo's description or URL instead of just the name?"

**You Do** (15-20 minutes)
- Give students time to complete the fetch, display, and error handling portions of the assignment.
- For students who finish early: encourage them to style the project list with Flexbox/Grid and link each repo name to its GitHub URL.

**Wrap-Up** (5-10 minutes)
- Quick show-and-tell: have 1-2 students share their portfolio with the Projects section populated.
- Remind students to push their work and submit their pull request.
- Point ahead: Open API — they'll pick a fun API and build something creative.

---

## 1:1 Session Guide

- **Build rapport**: This week is a big milestone. Celebrate the student seeing their own data on their portfolio page.
- **Check understanding**: Ask the student to walk you through their fetch code line by line. Can they explain what `.then(response => response.json())` does?
- **Encourage independence**: If the fetch isn't working, guide the student to check the browser console for errors. Common issues: typo in the URL, CORS errors, or trying to access data before the promise resolves. Ask: "What does the error message say? What line does it point to?"
- **Goal-setting**: Encourage the student to start thinking about which Open API they want to use next week. Looking at options early helps.
- **Common sticking points this week**:
  - Forgetting `.json()` on the response (getting a Response object instead of data)
  - Not understanding that `.json()` also returns a promise (needs another `.then()` or `await`)
  - Trying to use the data outside the `.then()` chain (it's not available yet)
  - Error handling: not knowing what `.catch()` does or forgetting to include it
  - The GitHub API URL: incorrect username or missing the `/repos` path
