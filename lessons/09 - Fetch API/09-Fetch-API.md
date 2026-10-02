# The Fetch API

`fetch` is a built-in JavaScript browser function for making HTTP requests. In other words, it lets your JavaScript ask a server for data (or send data to a server) and then read the server's reply.

Because requests take time to complete, `fetch` is **asynchronous**: your code doesn't freeze while it waits. Instead, `fetch` returns a **Promise**, which is an object that stands for a result that will arrive later.  We will explain **Promise**s more in a later section.

## Try it yourself

Almost every modern browser supports `fetch`, so you can try it right now. Open the **Console** tab in your browser's developer tools (Chrome or Firefox) and paste this in. You can also put it inside a `<script>` tag in a local HTML file.

```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => {
    if (!response.ok) {
      throw new Error('Request failed');
    }
    return response.json(); // Parse the response body as JSON
  })
  .then(data => {
    console.log(data); // Do something with the data
  })
  .catch(error => {
    console.error('An error occurred:', error);
  });
```

Here's what each step does:

1. `fetch(url)` sends the request and returns a Promise.
2. The first `.then()` runs when the server's response arrives. We check `response.ok` (true for status codes 200-299), then call `response.json()` to read the body as JSON.
3. The second `.then()` runs once the JSON has been parsed, and `data` is a regular JavaScript object.
4. `.catch()` runs if anything goes wrong along the way.

## The same thing with `async`/`await`

`async`/`await` is a newer syntax that makes Promise code read top to bottom, like normal code. Most modern code is written this way.

```javascript
async function getPost() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');

    if (!response.ok) {
      throw new Error(`Request failed with status ${response.status}`);
    }

    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('An error occurred:', error);
  }
}

getPost();
```

`await` pauses the function until the Promise finishes, and it can only be used inside an `async` function.

## Parameters

`fetch` takes two parameters: a URL and an optional options object.

1. **`url`** (required): the address you want to send the request to. If this is the only argument, `fetch` makes a **GET** request.
2. **`options`** (optional): an object that customizes the request. Common properties are:
   - `method`: the HTTP method (`'GET'`, `'POST'`, `'PUT'`, `'PATCH'`, `'DELETE'`)
   - `headers`: an object whose key-value pairs are header names and values
   - `body`: the data to send, as a string (usually created with `JSON.stringify`)


## Promises

The `fetch` function returns a Promise that will be fulfilled when a response comes back from the server. A promise is a JavaScript object that represents a value you don't have yet but expect to get later. Network requests, timers, and file reads all take time, and a promise lets your code say "go do this, and here's what to do when it finishes" without freezing the page while it waits.

Think of ordering food at a counter and getting a buzzer. The buzzer isn't your meal, but it's a placeholder that will eventually either light up (your food is ready) or tell you something went wrong (they're out of the dish).

A promise is always in one of three states:
- **Pending** - the work is still in progress.
- **Fulfilled** - the work succeeded, and the promise now holds a result value.
- **Rejected** - the work failed, and the promise holds an error.

Useful parts of the Response include:
- `response.ok`: `true` if the status code is 200-299
- `response.status`: the numeric status code (e.g. `200`, `404`, `500`)
- `response.json()`: reads the body and parses it as JSON (returns another Promise)
- `response.text()`: reads the body as plain text (also returns a Promise)

Error Handling is an important part of a fetch and will be discussed in the next section.

## Scrimba Videos to Watch
- **[Scrimba - JS Deep Dive - Async JS - Make Network Requests with fetch()](https://v2.scrimba.com/javascript-deep-dive-c0a/~02p)**
- **[Scrimba - JS Deep Dive - Async JS - Challenge: Fetch API](https://v2.scrimba.com/javascript-deep-dive-c0a/~02q)**
- **[Scrimba - JS Deep Dive - Async JS - Promises with async-await](https://v2.scrimba.com/javascript-deep-dive-c0a/~02r)**
- **[Scrimba  - JS Deep Dive - Async JS - Catch Errors with async-await](https://v2.scrimba.com/javascript-deep-dive-c0a/~02s)**
- **[Scrimba - Introduction to ES6+ - Async & Await](https://v2.scrimba.com/introduction-to-es6-c0t/~0u)**

## AI Learning Prompt: Retrieval Practice
1. Open your preferred AI chatbot (like CTD’s AI Reviewer).
2. Explain the purpose of the fetch API in your own words, and list the three components you can define in the optional "options" parameter.
3. Ask the AI to give you feedback on your explanation and tell you what you got right or where your understanding of request components (like method, headers, and body) could be improved.

**Example Prompt:**
> "I just learned about the fetch API. Here's my understanding: it's used to [your explanation]. I also think the options object can include [list 3 components]. Can you tell me what I got right and what I should refine in my understanding?"
