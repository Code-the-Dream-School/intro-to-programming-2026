# Fetch API

Go through **both** resources (Odin **and** Scrimba) for this topic as they will help you gain a more clear understanding of this topic.

Remember to please go to each link in this list and read through the content on that page. If there are links you are redirected to as you read/work through the content, follow those links as well and read the content there too.

- **[The Odin Project – JSON](https://www.theodinproject.com/lessons/node-path-javascript-json)**
- **[The Odin Project – Working with APIs](https://www.theodinproject.com/lessons/node-path-javascript-working-with-apis)**
- **[The Odin Project - Async and Await](https://www.theodinproject.com/lessons/node-path-javascript-async-and-await)**
- **[Scrimba - JS Deep Dive - Async JS - Make Network Requests with fetch()](https://v2.scrimba.com/javascript-deep-dive-c0a/~02p)**
- **[Scrimba - JS Deep Dive - Async JS - Challenge: Fetch API](https://v2.scrimba.com/javascript-deep-dive-c0a/~02q)**
- **[Scrimba - JS Deep Dive - Async JS - Promises with async-await](https://v2.scrimba.com/javascript-deep-dive-c0a/~02r)**
- **[Scrimba  - JS Deep Dive - Async JS - Catch Errors with async-await](https://v2.scrimba.com/javascript-deep-dive-c0a/~02s)**
- **[Scrimba - Introduction to ES6+ - Async & Await](https://v2.scrimba.com/introduction-to-es6-c0t/~0u)**

### The fetch API

At a high level, `fetch` is used to make HTTP requests on the browser. It uses `Promise`s to handle the asynchronous nature of HTTP requests and responses. `fetch` is used to formulate and send a request to a server and read the server response.

Since the `fetch` API is provided by almost all major browsers, you can use the `fetch` API by opening up the "Console" tab in Chrome or Firefox to use the built-in `fetch` function.

You can try this out by running it locally in an html file.
```jsx
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => {
    if (!response.ok) {
      throw new Error('Request failed');
    }
    return response.json(); // Parse the response as JSON
  })
  .then(data => {
    console.log(data); // Do something with the data
  })
  .catch(error => {
    console.error('An error occurred:', error);
  });
```

`fetch` has two parameters, url and options. The first parameter is required it defines the URL of the request that you want to send. If the URL is the only argument passed into the `fetch` function then a GET request will be made. 

The second parameter is optional it defines the other components of the request besides the URL:

- method - the method of the request (GET, POST, PUT, PATCH, DELETE)
- headers - an object whose key-value pairs are header names and values
- body - value should be a string of the body of the request

The `fetch` function returns a Promise that will be fulfilled when a response comes back from the server. The resolved value of the returned Promise is a [fetch Response object](https://developer.mozilla.org/en-US/docs/Web/API/Response) containing information about the response components.

### The async and await keywords

The async keyword is applied to a function. On its own, the async keyword transforms the function so that when the function is invoked, the return value will be wrapped in a promise.

The async keyword works in tandem with the await keyword inside of your function body.

The await keyword allows you to treat asynchronous requests as if they were synchronous.

Using the await keyword before fetch() forces the execution of the code to pause until that asynchronous operation is finished. Once it is, you can then use the resolved response.

```jsx
async function fetchData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
    
    if (!response.ok) {
      throw new Error('Request failed');
    }
    
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('An error occurred:', error);
  }
}

fetchData();
```

In this example, we define an **`async`** function called **`fetchData`**. Inside the function, we use the **`await`** keyword to make a GET request to the JSONPlaceholder API to fetch the post with an ID of 1. We also handle any potential errors using a **`try...catch`** block.

The response is first checked for its status using **`response.ok`**. If the response is successful, we use **`await response.json()`** to parse the JSON data. Finally, we log the data to the console.

## Final Project Rubric

Now is a good time to review the rubric for the portfolio portion of your final project.

[Portfolio Rubric](https://github.com/Code-the-Dream-School/intro-to-programming-2026/wiki/Portfolio-Rubric)
