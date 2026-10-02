# Error Handling with `fetch`

Things go wrong in real programs: the Wi-Fi drops, a server is down, or you ask for a page that doesn't exist. Error handling means writing code that deals with these situations gracefully instead of crashing or silently showing nothing.  As a software developer, you will end up writing a large portion of code that handles unexpected things happening.

## The key idea: two different kinds of failure

`fetch` can fail in two very different ways, and beginners often don't realize they behave differently.

Think of `fetch` as sending a letter and waiting for a reply:

1. **The letter never reaches anyone.** The mail truck broke down. In `fetch` terms, this is a **network error** (no internet, bad domain name, server unreachable). The Promise **rejects**, so `.catch()` runs.
2. **The letter arrives, but the reply says "No such address."** The delivery worked, but the answer is bad news. In `fetch` terms, this is an **HTTP error** (like `404 Not Found` or `500 Server Error`). The Promise **still resolves**, so `.catch()` does *not* run on its own.

| Situation | Example | What `fetch` does |
|---|---|---|
| Network failure | Offline, wrong domain, server down | Promise **rejects** (goes to `.catch`) |
| HTTP error response | 404, 500, 403 | Promise **resolves** with `response.ok === false` |
| Success | 200, 201 | Promise **resolves** with `response.ok === true` |

Because of this, you have to check for HTTP errors yourself.

## Step 1: Check `response.ok`

Every response has two useful properties:

- `response.ok` is `true` for status codes 200-299, and `false` otherwise.
- `response.status` is the number itself (`200`, `404`, `500`, and so on).

```javascript
fetch('https://jsonplaceholder.typicode.com/posts/999999')
  .then(response => {
    console.log(response.status); // 404
    console.log(response.ok);     // false
  });
```

Notice that no error was thrown even though the post doesn't exist. To send this problem to `.catch()`, we throw an error ourselves:

```javascript
fetch('https://jsonplaceholder.typicode.com/posts/999999')
  .then(response => {
    if (!response.ok) {
      throw new Error(`Request failed with status ${response.status}`);
    }
    return response.json();
  })
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Something went wrong:', error.message);
  });
```

When you `throw` inside a `.then()`, JavaScript skips the remaining `.then()` steps and jumps straight to `.catch()`. Now network failures *and* HTTP errors end up in the same place.

## Step 2: Use `try`/`catch` with `async`/`await`

Most modern code uses `async`/`await`, where errors are handled with `try`/`catch`:

```javascript
async function getPost(id) {
  try {
    const response = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);

    if (!response.ok) {
      throw new Error(`Request failed with status ${response.status}`);
    }

    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Something went wrong:', error.message);
  }
}

getPost(1);       // works
getPost(999999);  // logs the 404 error
```

Any error thrown inside the `try` block, whether from a network failure, your own `throw`, or a parsing problem, jumps to the `catch` block.

## Step 3: Know the three places things can fail

A single `fetch` call really has three steps, and each can go wrong:

1. **Sending the request** can fail with a network error. You get a `TypeError` (Chrome's message is usually `Failed to fetch`).
2. **Checking the response** can fail when the server returns a 404, 500, and so on. You throw this error yourself.
3. **Reading the body** can fail. `response.json()` throws a `SyntaxError` if the server sends something that isn't valid JSON, such as an HTML error page.

You can tell these apart using the error's `name`:

```javascript
async function getPost(id) {
  try {
    const response = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);

    if (!response.ok) {
      throw new Error(`Server responded with status ${response.status}`);
    }

    return await response.json();
  } catch (error) {
    if (error.name === 'TypeError') {
      console.error('Network problem. Check your internet connection.');
    } else if (error.name === 'SyntaxError') {
      console.error('The server sent data that was not valid JSON.');
    } else {
      console.error(error.message); // our own HTTP error
    }
  }
}
```

## Step 4: Respond differently to different status codes

Status codes tell you *what* went wrong, so you can give the user a helpful message:

| Status | Meaning | Friendly message idea |
|---|---|---|
| 400 | Bad Request (you sent something invalid) | "Please check your input." |
| 401 | Unauthorized (not logged in) | "Please log in and try again." |
| 403 | Forbidden (not allowed) | "You don't have permission." |
| 404 | Not Found | "We couldn't find what you asked for." |
| 429 | Too Many Requests | "Slow down and try again shortly." |
| 500+ | Server error (their fault, not yours) | "Something went wrong on our end." |

```javascript
if (!response.ok) {
  if (response.status === 404) {
    throw new Error('That item could not be found.');
  } else if (response.status >= 500) {
    throw new Error('The server is having problems. Try again later.');
  } else {
    throw new Error(`Unexpected error (status ${response.status}).`);
  }
}
```

## Step 5: Show errors to the user, not just the console

`console.error` is for developers. Real users never open the console, so display a message on the page:

```javascript
async function loadPost(id) {
  const output = document.querySelector('#output');
  output.textContent = 'Loading...';

  try {
    const response = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);

    if (!response.ok) {
      throw new Error(`Request failed with status ${response.status}`);
    }

    const post = await response.json();
    output.textContent = post.title;
  } catch (error) {
    output.textContent = 'Sorry, we could not load that post. Please try again.';
    console.error(error); // still log details for yourself
  }
}
```

A good habit is to show a friendly message to the user and log the technical details for yourself.

## A reusable helper

If you make many requests, repeat the checking logic once in a helper function:

```javascript
async function fetchJson(url, options) {
  const response = await fetch(url, options);

  if (!response.ok) {
    throw new Error(`Request failed with status ${response.status}`);
  }

  return response.json();
}

// Now each use is short:
try {
  const post = await fetchJson('https://jsonplaceholder.typicode.com/posts/1');
  console.log(post);
} catch (error) {
  console.error(error.message);
}
```

## Optional: add a timeout

By default, `fetch` can wait a very long time. Modern browsers let you give up after a set time:

```javascript
try {
  const response = await fetch(url, { signal: AbortSignal.timeout(5000) }); // 5 seconds
  // ...
} catch (error) {
  if (error.name === 'TimeoutError') {
    console.error('The request took too long.');
  }
}
```

## Common beginner mistakes

- **Assuming `.catch()` handles 404s.** It doesn't. Always check `response.ok`.
- **Forgetting `await`.** Without it, you get a Promise instead of the response, and errors escape your `try`/`catch`.
- **Forgetting `return` in a `.then()`.** The next `.then()` receives `undefined`.
- **An empty `catch` block.** `catch (error) {}` hides problems completely. At minimum, log the error.
- **Only testing the happy path.** Always test what happens when things fail.

## Try it: make errors happen on purpose

The best way to learn is to break things. Paste these into your browser console:

1. **HTTP error:** request `https://jsonplaceholder.typicode.com/posts/999999` and watch the 404 handling.
2. **Network error:** request `https://this-domain-does-not-exist-12345.com` and look at the `TypeError`.
3. **Offline:** open DevTools, go to the **Network** tab, set throttling to **Offline**, and run a request.
4. **Bad JSON:** call `response.json()` on a URL that returns a web page, like `https://example.com`. This usually triggers a `SyntaxError`. Your browser may block this request due to CORS, in which case you'll see a `TypeError` instead, which is a good reminder that a `TypeError` isn't *always* an offline problem.

## Summary checklist

1. Wrap `await fetch(...)` in `try`/`catch` (or add `.catch()` to a Promise chain).
2. Check `response.ok` and `throw` if it's `false`.
3. Remember that `response.json()` can fail too.
4. Show the user a friendly message, and log the technical details.
5. Test failure cases on purpose.


### AI Learning Prompt: Predict-then-Check

Study this logic based on the fetchData function without running it:

```js
async function fetchData() {
  console.log("A");
  const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
  console.log("B");
}
fetchData();
console.log("C");
```

1. Predict the order in which "A", "B", and "C" will be printed to the console.
2. Explain to an AI chatbot why you think that order will occur, specifically focusing on how the await keyword pauses execution inside the function.
3. Ask: "Is my understanding of the `await` keyword and the order of execution correct here?"
4. Run the code in your browser console and see if you were right.


### AI Learning Prompt: Scaffold Removal

As you work on fetching data for your portfolio, you may encounter "Request failed" errors or "undefined" data. Instead of asking an AI to fix your code, use these prompts to help you do the thinking.

**Example Prompt for an Error:**
> "I'm getting a 'Request failed' error message when I try to fetch data. Here is my code: [paste code]. Can you ask me 3 questions that will help me figure out if I'm checking the response.ok status or the URL correctly?"

**Example Prompt for a Hint:**
> "I'm stuck on how to use a try...catch block to handle network errors in my fetch function. Can you give me 3 high-level hints for how to structure this without giving me the final answer?"
