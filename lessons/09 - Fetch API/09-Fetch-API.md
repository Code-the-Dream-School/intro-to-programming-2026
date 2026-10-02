# The Fetch API

`fetch` is a built-in browser function for making HTTP requests. In other words, it lets your JavaScript ask a server for data (or send data to a server) and then read the server's reply.

Because requests take time to complete, `fetch` is **asynchronous**: your code doesn't freeze while it waits. Instead, `fetch` returns a **Promise**, which is an object that stands for a result that will arrive later.

## Promises

A promise is a JavaScript object that represents a value you don't have yet but expect to get later. Network requests, timers, and file reads all take time, and a promise lets your code say "go do this, and here's what to do when it finishes" without freezing the page while it waits.

Think of ordering food at a counter and getting a buzzer. The buzzer isn't your meal, but it's a placeholder that will eventually either light up (your food is ready) or tell you something went wrong (they're out of the dish).

A promise is always in one of three states:

- **Pending** - the work is still in progress.
- **Fulfilled** - the work succeeded, and the promise now holds a result value.
- **Rejected** - the work failed, and the promise holds an error.

You'll also hear the word **resolved**. For now, treat "fulfilled" and "resolved" as meaning the same thing: the promise finished and has a value for you.

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

`await` pauses the function until the Promise finishes. In the code you write for this course, `await` can only be used inside an `async` function.

## Parameters

`fetch` takes two parameters: a URL and an optional options object.

1. **`url`** (required): the address you want to send the request to. If this is the only argument, `fetch` makes a **GET** request.
2. **`options`** (optional): an object that customizes the request. Common properties are:
   - `method`: the HTTP method (`'GET'`, `'POST'`, `'PUT'`, `'PATCH'`, `'DELETE'`)
   - `headers`: an object whose key-value pairs are header names and values
   - `body`: the data to send, as a string (usually created with `JSON.stringify`)

### Example: sending data with POST

```javascript
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    title: 'Hello',
    body: 'My first post',
    userId: 1
  })
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('An error occurred:', error));
```

The `Content-Type` header tells the server that the body is JSON. (This example skips the `response.ok` check to keep it short. In real code, include it, as you'll see in the next topic.)

## The Response object

`fetch` returns a Promise that is fulfilled with a [Response object](https://developer.mozilla.org/en-US/docs/Web/API/Response) as soon as the server's reply starts to arrive. Useful parts of the Response include:

- `response.ok`: `true` if the status code is 200-299
- `response.status`: the numeric status code (e.g. `200`, `404`, `500`)
- `response.json()`: reads the body and parses it as JSON (returns another Promise)
- `response.text()`: reads the body as plain text (also returns a Promise)

Error handling is an important part of using `fetch` and is covered in the next topic.

## AI Learning Prompt: Retrieval Practice

1. Open your preferred AI chatbot (like CTD's AI Reviewer).
2. Explain the purpose of the fetch API in your own words, and list three common components you can define in the optional "options" parameter.
3. Ask the AI to give you feedback on your explanation and tell you what you got right or where your understanding of request components (like method, headers, and body) could be improved.

**Example Prompt:**
> "I just learned about the fetch API. Here's my understanding: it's used to [your explanation]. I also think the options object can include [list 3 components]. Can you tell me what I got right and what I should refine in my understanding?"

## AI Learning Prompt: Predict-then-Check

Study this code without running it:

```javascript
async function fetchData() {
  console.log("A");
  const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
  console.log("B");
}
fetchData();
console.log("C");
```

1. Predict the order in which "A", "B", and "C" will be printed to the console.
2. Explain to an AI chatbot why you think that order will occur, specifically focusing on how the `await` keyword pauses execution inside the function.
3. Ask: "Is my understanding of the `await` keyword and the order of execution correct here?"
4. Run the code in your browser console and see if you were right.

