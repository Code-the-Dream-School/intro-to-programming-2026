# Lesson 8 – Asynchronous Programming and Promises

## 8.1 Synchronous vs. Asynchronous Code

### Synchronous Code

- **Blocking execution:** In synchronous code, tasks are executed sequentially. Each operation must complete before the next one can begin.
- **Real life examples:** Phones calls, face to face conversation
- **Predictable flow:** The order of execution is clear and straightforward, making it easier to reason about and debug.
- **Predictability:** The sequential nature of sync operations ensures that tasks are executed in a predictable order, which can be important for tasks requiring strict sequencing.
- **Inefficiency with I/O Operations:** Sync programming can be inefficient for I/O-bound tasks, as operations like file reading or network requests can block the entire thread until completion.

![image](https://github.com/Code-the-Dream-School/intro-to-programming-2026/blob/main/assets/Lesson08/Synchronous%20Flow.JPG?raw=true)

### Asynchronous Code
- **Non-blocking execution:** Asynchronous code allows a program to initiate a task and continue executing other code without waiting for the initiated task to complete.
- **Real life examples:** Text Messages, Email
- **Improved responsiveness:** This is crucial for applications where responsiveness is key, such as web servers handling multiple user requests or user interfaces that need to remain interactive during long operations.
- **Complexity:** Asynchronous code can be more complex to write and debug due to the non-linear flow of execution and the need for mechanisms like callbacks, promises, or async/await keywords to manage results.

![image](https://github.com/Code-the-Dream-School/intro-to-programming-2026/blob/main/assets/Lesson08/Asynchronous%20Flow.JPG?raw=true)

### AI Learning Prompt: Retrieval Practice

1. Open your preferred AI chatbot (like CTD’s AI Reviewer).
2. **Explain the difference between "blocking" and "non-blocking" execution** in your own words.
3. Ask the AI to give you feedback on your explanation and suggest where your understanding could be improved.

**Example Prompt:**
> "I’m learning about Lesson 8. Here is my understanding of the difference between blocking and non-blocking code: [your explanation]. Based on my explanation, what am I getting right and what should I refine?"

## 8.2 Promises

We talked about callbacks in lesson 4.  There are some disadvanatages to callbacks.  Promises are another way to manage asynchronous operations by providing a cleaner way to handle errors and chain multiple asynchronous steps, thereby avoiding the complexity of nested callbacks - often referred to as "callback hell".

- **Callbacks** are functions passed to other functions to be executed later
- **Promises** are objects representing the eventual success or failure of an asynchronouse operation with methods for handling these outcomes.  They are called *promises* because they guarantee that an asynchronous operation, which has not yet completed, will eventaully produce a value or a reason for its failure.  A promise is a placeholder object for a result that is not yet available.

It's important to understand the concept of promises, but we won't be creating them in this lesson.  They are the basis for the fetch API which we will learn about in the next lesson.

### AI Learning Prompt: Predict-then-Check

Consider the concept of a Promise as a "placeholder object" for a result that hasn't arrived yet.
1. Predict: If you try to `console.log()` the direct result of an asynchronous operation before it has finished, what do you think you will see?
2. Explain to an AI chatbot why you made that prediction based on the idea of a "placeholder".
3. Ask: "Is my reasoning about the state of a Promise before it resolves correct?"

## 8.3 Lesson Materials

Remember to please go to each link in this list and read through the content on that page. If there are links you are redirected to as you read/work through the content, follow those links as well and read the content there too.

- **[The Odin Project – Asynchronous Code](https://www.theodinproject.com/lessons/node-path-javascript-asynchronous-code)**

### 🥂 Great job on Lesson 8!

Next week, we'll start **Fetch API**, which you will use to retrieve data from the web. Make sure to book a mentor session if you feel stuck!
