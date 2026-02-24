# Lesson 9 – Fetch API

## 9.1 Lessons

**Go through *both* resources (Odin *and* Scrimba) for this topic** as they will help you gain a more clear understanding of this topic.

Remember to please go to each link in this list and read through the content on that page. If there are links you are redirected to as you read/work through the content, follow those links as well and read the content there too.

### The Odin Project Articles

- **[The Odin Project – JSON](https://www.theodinproject.com/lessons/node-path-javascript-json)**
- **[The Odin Project – Working with APIs](https://www.theodinproject.com/lessons/node-path-javascript-working-with-apis)**
- **[The Odin Project - Async and Await](https://www.theodinproject.com/lessons/node-path-javascript-async-and-await)**

### Scrimba Videos
- **[Scrimba - JS Deep Dive - Async JS - Make Network Requests with fetch()](https://v2.scrimba.com/javascript-deep-dive-c0a/~02p)**
- **[Scrimba - JS Deep Dive - Async JS - Challenge: Fetch API](https://v2.scrimba.com/javascript-deep-dive-c0a/~02q)**
- **[Scrimba - JS Deep Dive - Async JS - Promises with async-await](https://v2.scrimba.com/javascript-deep-dive-c0a/~02r)**
- **[Scrimba  - JS Deep Dive - Async JS - Catch Errors with async-await](https://v2.scrimba.com/javascript-deep-dive-c0a/~02s)**
- **[Scrimba - Introduction to ES6+ - Async & Await](https://v2.scrimba.com/introduction-to-es6-c0t/~0u)**

## 9.2 The fetch API

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

### AI Learning Prompt: Retrieval Practice
1. Open your preferred AI chatbot (like CTD’s AI Reviewer).
2. Explain the purpose of the fetch API in your own words, and list the three components you can define in the optional "options" parameter.
3. Ask the AI to give you feedback on your explanation and tell you what you got right or where your understanding of request components (like method, headers, and body) could be improved.

**Example Prompt:**
> "I just learned about the fetch API. Here's my understanding: it's used to [your explanation]. I also think the options object can include [list 3 components]. Can you tell me what I got right and what I should refine in my understanding?"

## 9.3 Async and Await

The `async` keyword is applied to a function. On its own, the async keyword transforms the function so that when the function is invoked, the return value will be wrapped in a promise.

The async keyword works in tandem with the `await` keyword inside of your function body.

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

## 9.4 Final Project Rubric

Now is a good time to review the **rubric** for the portfolio portion of your final project. A grading rubric is a tool that spells out the exact requirements for your final project - it's what your mentors will use to grade your work. As you complete your final project, make sure the requirements are checked! Note that some requirements are marked as optional - these are great additions to your project, but not required to pass.

**[Rubric: Final Project - Portfolio](https://github.com/Code-the-Dream-School/intro-to-programming-2026/wiki/Portfolio-Rubric)**

### AI Learning Prompt: Retrieval Practice: Rubric Comprehension

To ensure you have a clear roadmap for your project, let's practice retrieving the core requirements from the rubric:

1. Open your preferred AI chatbot.
2. Explain the four specific JavaScript tasks you must complete for your portfolio (Hint: Look at the index.js section of the rubric, which includes the footer, skills section, form handling, and API fetch).
3. Ask the AI to verify if your summary matches the requirements and ask for a suggestion on which task you should tackle first based on your current progress.

**Example Prompt:**
> "I am reviewing my portfolio project rubric. Based on my reading, I need to use JavaScript to: 1) [Task 1], 2) [Task 2], 3) [Task 3], and 4) [Task 4]. Am I missing any technical requirements regarding the footer or the projects section? Based on these, which one is the best to start with now that I've learned about Fetch?".

## 🙌 That's lesson 9 in the books!
You're nearing the end of Intro to Programming! As always, reach out if you need help, and congrats on your hard work so far.
