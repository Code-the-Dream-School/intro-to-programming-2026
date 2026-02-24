# 3.1 JavaScript Objects

In JavaScript, **objects** are used to manage data using key-value pairs. While primitive types (like strings or numbers) hold a single value, objects allow you to group related data together.

Read these two explanations of objects and how they work.
* [JavaScript.Info: Objects](https://javascript.info/object)
* [Mozilla DevDocs: Objects Basics](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Object_basics)

Scrimba Videos for those who find them helpful:
- [JS Deep Dive - Use Objects for Managing Key-Value-Pairs](https://scrimba.com/javascript-deep-dive-c0a/~016)
- [JS Deep Dive - Challenge: Your First Object](https://scrimba.com/javascript-deep-dive-c0a/~017)
- [JS Deep Dive - Understand Primitive vs Object Types](https://scrimba.com/javascript-deep-dive-c0a/~018)
- [JS Deep Dive - Get and Modify Object Data](https://scrimba.com/javascript-deep-dive-c0a/~019)

## Check for Understanding: Objects

**Question**: What is the primary purpose of an object in JavaScript?
* A) To repeat a task a specific number of times
* B) To store ordered lists of data using index numbers
* C) To manage and store data as a collection of key-value pairs
* D) To define if a condition is true or false

<details>

<summary>View answer</summary>

**Answer**: C) To manage and store data as a collection of key-value pairs

</details>

## AI Learning Prompt: Retrieval Practice

Now that you have explored the basics of objects, let's reinforce your understanding of how they differ from other data types:

1. Open your preferred AI chatbot (CTD's AI Reviewer, ChatGPT, etc.).
2. Explain the difference between **primitive types** and **object types** in your own words.
3. Ask the AI to give you feedback on your explanation and suggest where you could strengthen your understanding.

**Example Prompt:**
> "I'm learning about JavaScript objects. Here is my explanation of how an object is different from a primitive data type like a string: [your explanation]. What am I getting right, and where could I improve my understanding?"

## AI Learning Prompt: Predict-then-Check

Study this code without running it:

```js
const user = {
  name: "Alex",
  score: 10
};
user.score = 15;
console.log(user.score);
```

1. **Predict** what will be printed to the console.
2. Explain to an AI chatbot **why** you think that output will appear, specifically focusing on how to **modify object data**.
3. Ask: "Is my reasoning about modifying object properties correct?"
4. Run the code to see if you were right. If you were wrong, ask the AI to explain the concept you misunderstood.

# 3.2 Continuing with Git - Commit and Push Updates

Last week, we cloned our repository to our local machine.

This week, we are going to make some changes in our repository, **commit** them and **push** them back to our remote repository. This process involves creating a new **branch**, staging your changes with `git add`, and saving them to your history with `git commit`.

### Watch this video on how to make changes in your repository: ###
[Making Changes in Your Repository](https://www.youtube.com/watch?v=Uqn8Ws_jzmg)

## Assignment - Making changes in our repository
   - [ ] Navigate into the directory you cloned last week by typing `cd <name-classname>` in the terminal where the <name-classname> portion is the name of your repository.
   - [ ] Create a new local branch to house just the work you'll do for this assignment by running `git checkout -b lesson-3` in the terminal
   - [ ] You can run `git status` or `git branch --show-current` to verify that you are currently working in the correct branch.
   - [ ] Open the README.md file in your code editor and add your full name.
   - [ ] Create a new file in your project directory (same level as your README.md file) and title it `index.html`
   - [ ] Check the status of the changes you just made (editing the readme.md file and making a new index.html file) by running `git status` in your terminal
   - [ ] Stage all your changes for commit by running `git add .` in your terminal
   - [ ] Run `git status` again to see how things have changed.  You should get a response indicating changes staged for commit.
   - [ ] Create a commit message for reference.  Run `git commit -m "my first commit"`
   - [ ] Push these changes to your GitHub repository from your local computer by running `git push origin lesson-3`
   - [ ] **NOTE:** if you get a "fatal: The current branch..." error message.  READ the message and follow the instructions in that message to confirm that you push your work to your GitHub account.
   - [ ] When you submit your assignment this week, please copy and paste the link to the branch you created in the "second link to assignment" field.

## Git / GitHub Workflow
The following image shows the entire workflow involved in using Git and GitHub.  Pay attention to where files are located in each step - either on your local machine or remote in GitHub.  

In this lesson, we have completed the portion of the workflow outlined with the red dashed line. We will work on the remaining workflow in Lesson 4.

![image](https://github.com/Code-the-Dream-School/intro-to-programming-2026/blob/main/assets/Lesson03/GitFlow-Lesson03.jpg?raw=true)

## Check for Understanding: GitHub Workflow

**Question 1**: Which command is used to stage all your recent changes before committing them?
* A) `git commit -m`
* B) `git status`
* C) `git add`
* D) `git checkout -b` 


<details>

<summary>View answer</summary>

**Answer**: C) `git add`

</details>

**Question 2:** What is the purpose of the command `git push origin lesson-3`?
* A) To delete the "lesson-3" branch from your computer
* B) To upload your local branch and its commits to your remote GitHub repository
* C) To create a new file named "lesson-3"
* D) To see which files have been modified Answer: B) To upload your local branch and its commits to your remote GitHub repository

<details>

<summary>View answer</summary>

**Answer**: B) To upload your local branch and its commits to your remote GitHub repository

</details>

# 💪🏾 Nice job on Lesson 3!
Next, complete this week's coding assignment. Reach out to your mentor if you have questions or need help – you're making great progress!
