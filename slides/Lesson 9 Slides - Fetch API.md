---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 9: Fetch API"
---

# Lesson 9: Fetch API

**Mentor Session Slide Deck**

Topics: Making HTTP Requests, JSON, `.then()` Chains, `async/await`, Error Handling

---

# What is an API?

**API** = Application Programming Interface

It's a way for your code to **request data** from a server.

Think of it like a **restaurant menu**:
- The menu shows what you can order (the API documentation)
- You place an order (make a request)
- The kitchen prepares your food (the server processes it)
- You receive your meal (the response with data)

---

# What is JSON?

**JSON** (JavaScript Object Notation) — the language APIs use to send data:

```json
{
    "name": "Durham",
    "state": "North Carolina",
    "population": 300000,
    "landmarks": ["Duke University", "Durham Bulls Athletic Park"]
}
```

Looks familiar? It's **just like a JavaScript object** — but as a text format that any programming language can read.

---

# The `fetch` Function

```javascript
fetch("https://jsonplaceholder.typicode.com/users/1")
    .then(function(response) {
        return response.json();   // Parse the JSON
    })
    .then(function(data) {
        console.log(data.name);   // "Leanne Graham"
        console.log(data.email);  // "Sincere@april.biz"
    })
    .catch(function(error) {
        console.error("Failed to fetch:", error);
    });
```

**Step by step**:
1. `fetch(url)` — sends the request, returns a promise
2. `.then(response.json())` — converts the response to usable data
3. `.then(data)` — now you can use the data!
4. `.catch(error)` — handles any failures

---

# Why Two `.then()` Calls?

```javascript
fetch(url)
    .then(response => response.json())   // This is also a promise!
    .then(data => console.log(data));     // Now we have actual data
```

- `fetch` returns a **Response object** (not the data itself)
- `response.json()` **also returns a promise** that resolves to the parsed data
- So we need two `.then()` calls: one for the response, one for the data

This is the #1 thing that confuses students — it's worth repeating!

---

# `async/await` — Cleaner Syntax

The same thing, written with `async/await`:

```javascript
async function getUserInfo() {
    try {
        let response = await fetch("https://jsonplaceholder.typicode.com/users/1");
        let data = await response.json();

        console.log(data.name);
        console.log(data.email);
    } catch (error) {
        console.error("Failed to fetch:", error);
    }
}

getUserInfo();
```

**Same behavior**, but reads like synchronous code. `await` pauses until the promise resolves.

---

# Error Handling

Things can go wrong: bad URLs, server outages, network issues.

```javascript
async function fetchSafely(url) {
    try {
        let response = await fetch(url);

        if (!response.ok) {
            throw new Error(`Server error: ${response.status}`);
        }

        let data = await response.json();
        return data;
    } catch (error) {
        console.error("Something went wrong:", error.message);
    }
}
```

**Always check `response.ok`** — `fetch` doesn't throw on 404s or 500s!

---

# Live Example: Fetching a User List

```javascript
async function displayUsers() {
    try {
        let response = await fetch("https://jsonplaceholder.typicode.com/users");
        let users = await response.json();

        let list = document.querySelector("#user-list");

        for (let i = 0; i < users.length; i++) {
            let item = document.createElement("li");
            item.textContent = `${users[i].name} — ${users[i].company.name}`;
            list.appendChild(item);
        }
    } catch (error) {
        console.error("Could not load users:", error);
    }
}

displayUsers();
```

This is the **exact pattern** you'll use to display your GitHub repos!

---

# The Fetch + DOM Pattern

1. **Fetch** data from an API
2. **Parse** the JSON response
3. **Loop** through the data
4. **Create** DOM elements for each item
5. **Append** them to the page
6. **Catch** any errors

```
fetch → parse → loop → create → append → catch
```

You've already learned each of these pieces individually. This week, they all come together!

---

# Try This!

Fetch data from `https://jsonplaceholder.typicode.com/posts` and:

1. Display the **title** of the first 5 posts as `<li>` items in a `<ul>`
2. If the fetch fails, show an error message on the page instead

**Starter**:
```javascript
async function loadPosts() {
    // Your code here
    // 1. Fetch the data
    // 2. Parse the JSON
    // 3. Loop through the first 5 items
    // 4. Create <li> elements and append them
    // 5. Handle errors
}
```

**Bonus**: Make each post title a clickable link!

---

# Key Takeaways

- **`fetch(url)`** sends an HTTP request and returns a promise
- **`response.json()`** parses the response — this is also a promise (two `.then()` calls!)
- **`async/await`** makes promise code read like synchronous code
- **Always handle errors** with `.catch()` or `try/catch`
- The pattern: **fetch → parse → loop → create → append**

**Next week**: Open API — you'll pick a public API and build a creative second page!
