# Algorithms

This week we are going to look at **algorithms**. An algorithm sounds like it might be something hard and complex, but it really is just a set of steps that you are going to code in order to accomplish an end goal - a set of step-by-step instructions to solve a specific problem or perform a task.

Here is a non-coding explanation of algorithms, which can be a helpful way to think about some of the problems we are trying to solve.

* [Algorithms in Everyday Life](https://www.learning.com/blog/7-examples-of-algorithms-in-everyday-life-for-students/)

### Real-world example of an algorithm: Making a peanut butter and jelly sandwich
- Check if you have bread, peanut butter, and jelly
- If any ingredient is missing:
  - Make a note of what to buy
  - Stop (can't make sandwich)
- Take out the following things:
  - Two slices of bread
  - Jar of peanut butter
  - Jar of jelly
  - knife
  - plate
- Open the peanut butter jar
- Spread peanut butter on first slice
- Open the jelly jar  
- Spread jelly on second slice
- Put the slices together
- Cut sandwich in half (optional)
- Serve on plate

### Real World Algorithms You Use Daily:
- Following a recipe (step-by-step instructions)
- Using a GPS (algorithm finds best route)
- ATM withdrawal (checks balance, dispenses cash, updates account)
- Doing laundry (sort, wash, dry, fold - in that order!)

###  Practice Tip:
Practice your pseudo-code thinking! Before coding, try writing out the steps for these everyday tasks:
- Making a cup of coffee
- Brushing your teeth
- Checking if you need an umbrella (hint: check weather!)

## AI Learning Prompt: Retrieval Practice

1. Open your preferred AI chatbot.
2. **Explain the concept of an algorithm** using an everyday example (like making a sandwich or doing laundry).
3. Ask the AI to provide feedback on whether your example accurately represents how a computer follows a set of instructions.

**Example Prompt**: 

>"I’m learning about algorithms. My understanding is that an algorithm is like a recipe for a computer. For example, the 'algorithm' for making coffee would be: [insert your steps]. Does this explanation accurately capture the concept of an algorithm? How could I make it more precise?"

# Pseudocode

As the problems you are trying to solve become more complex, it can be helpful to write the steps of your program down in plain language instead of jumping straight to code. Even experienced developers do this as a way of thinking about the problem they are trying to solve without having to drill down into the specifics of how to code it.

Pseudocode will not compile or run, but can be made as a set of comments with code filled in later in the appropriate places. It is also helpful that the pseudocode can simply become the comments for your code once it is written.

Let's take the simple example of a tip calculator which will be one of your questions for assignment 4.

```jsx
// We know it's a function and that it takes 2 parameters, so we'll just go ahead and code that part
function tipCalculator(billTotal, tipPercentage) {
  // Check the parameters and make sure they are valid
  // Multiply the total by the tip percentage which gives us the tip
  // Add the tip to the bill total to get the final amount paid
  // Return the final amount paid
}
```
# Callbacks

Callbacks are functions that you provide to another function or system to be executed when a certain condition or event occurs. They are a way of saying, "Hey, when this thing happens, do this specific task.”

Here is some additional information on callbacks:  
https://www.w3schools.com/js/js_callback.asp

Imagine you have a button on a website, and you want something to happen when the button is clicked. You could create a callback function that specifies what should happen when the button is clicked. This callback function is then associated with the button.

```jsx
// A function that adds two numbers and uses a callback to return the result
function addNumbers(a, b, callback) {
  const result = a + b;
  callback(result);
}

// Define a callback function to handle the result
function handleResult(result) {
  console.log("The result is: " + result);
}

// Call the addNumbers function with a callback
addNumbers(5, 3, handleResult);
```

In this example, the **`addNumbers`** function takes two numbers **`a`** and **`b`**, adds them together, and then calls a provided **`callback`** function with the result. The **`handleResult`** function is the callback, and it prints the result to the console.

Callbacks are a versatile and powerful concept in programming, and they can be used in various scenarios. Here are some common situations where callbacks are useful:

1. **Asynchronous Operations:** Callbacks are often used with asynchronous operations, like making network requests, reading files, or interacting with databases. They allow you to specify what should happen when the operation is completed without blocking the rest of your program.
2. **Event Handling:** In user interfaces, callbacks are used to respond to user interactions such as button clicks, mouse movements, or keyboard input. You define a callback function that gets triggered when the event occurs.
3. **Modular and Reusable Code:** Callbacks make it easier to write modular and reusable code. You can create functions that accept callbacks to perform specific tasks, allowing you to reuse those functions with different behaviors depending on the callback provided.
4. **Iterations and Loops:** Callbacks can be used in iterations and loops to execute a function for each element in a collection, like an array or a list. This is known as "callback-based iteration."
5. **Promises and Promisified Code:** In JavaScript, promises often work with callbacks to handle asynchronous tasks more cleanly. Promises provide a structured way to handle callbacks and make asynchronous code easier to read and maintain.

Overall, callbacks are a fundamental building block in software development, enabling you to define what should happen when a particular event or operation occurs, making your code more flexible, modular, and responsive.

Don't worry if each of these uses doesn't make complete sense yet. It's just helpful to become familiar with some of the terminology. We will be covering callbacks again in some of the later lessons.

## Why callbacks are useful:

```jsx
// WITHOUT callbacks - we'd need separate functions for everything:
function printDouble(num) {
  console.log(num * 2);
}
function printTriple(num) {
  console.log(num * 3);
}
function printSquare(num) {
  console.log(num * num);
}

// WITH callbacks - one flexible function:
function processNumber(num, action) {
  action(num);  // Let the user decide what to do!
}

// Now we can do anything:
processNumber(5, (n) => console.log(n * 2));    // doubles it
processNumber(5, (n) => console.log(n * 3));    // triples it
processNumber(5, (n) => console.log(n * n));    // squares it
processNumber(5, (n) => console.log("The number is " + n));  // or anything else!

// Callbacks let us write flexible, reusable code!
```

# Continuing with Git - What is a Pull Request?

A pull request is a request to merge a set of changes from one branch into another. 
You can also think of it as requesting that a branch pull your updated code into that branch.

- **Source Branch**: The branch containing the new or modified code that the developer wants to contribute. 
- **Target Branch**: The branch into which the changes will be merged, typically the main or development branch of the project. 

After the PR (Pull Request) has been approved (generally by some type of review process), then the owner of the target branch can merge the code.  In the case of multiple people working in the same area of code, there may potentially be conflicts that have to be resolved during the merge process.

**GitHub: About Pull Requests:**

[About Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

**Watch this video on creating a Pull Request:**
[Creating a Pull Request Video](https://www.youtube.com/watch?v=89hjRfX0dS4)

## Assignment - Create and Submit a PR
Now, let's submit a PR.
- [ ] Go to your GitHub repository page in your web browser now, and you should see a "lesson-3 has a recent push" notice with a green "Compare & pull request" button.  Click that button
- [ ] Feel free to put notes to yourself or notes for your reviewer in the description (be sure you're including any questions to your reviewer in your assignment submission form though!) and click the green "Create pull request" button.
- [ ] Copy the address of your pull request page (should look  something like `https://github.com/yourUsername/name-classname/pull/1`) and paste it into your assignment submission form.  Each of the following weeks, you will submit a PR link for review. 

### MERGE back into the remote (GitHub) main repo
- This week, we are going to go ahead and merge our updates back into the main branch right now so that you can see how that works.  
- For future weeks, if you are ready to start on the next lesson and have not gotten your review comments back yet, you can go ahead and merge your pull request and continue working.  If you are unsure about your work, schedule a 1:1 session with a mentor and review your work together before merging.

### PULL back into your local main repo
- [ ] In your terminal, make sure you're on your main branch. You can use `git status` to see. If you're still on your lesson-3 branch, you can switch to your main branch by using the git command `git checkout main`.
- [ ] Update your local main branch to include your lesson-3 work by pulling your changes from your GitHub repository main. Use the following git command in your terminal to do this: `git pull origin main`.

## Git / GitHub Workflow
The following image shows the entire workflow involved in using Git and GitHub.  Pay attention to where files are located in each step - either on your local machine or remote in GitHub.  

In this lesson, we have completed the portion of the workflow outlined with the red dashed line, which completed the entire workflow.

![image](https://github.com/Code-the-Dream-School/intro-to-programming-2026/blob/main/assets/Lesson04/GitFlow-Lesson04.jpg?raw=true)

## AI Learning Prompt: Scaffold Removal

If you encounter a "merge conflict" or an error while trying to `git pull`, use the AI to help you think, not just give the answer.

**Example Prompt:**

>"I just merged my pull request on GitHub, but when I try to run `git pull origin main` in my terminal, I get this error: [paste error]. Can you ask me 3 questions that will help me figure out how to sync my local repository correctly?"

# 🕶️ Great job with Lesson 4!

As always, book a session with your mentor if you need extra help. 
