Welcome to Code the Dream's **Intro to Programming** class!

# How to Follow this Content

- Start by reading the lesson's **learning objective** in the `Lesson Overview` section. Each weekly assignment will measure your skills related to the learning objective.
- Lessons are split into **subsections**, labeled like this: `1.1`, `1.2`, etc. Each subsection contains links to written **Odin Project** lessons and links to video lessons in **Scrimba**. You can choose to complete either the Odin Project or Scrimba materials based on which you like more. You don't need to work through both the text and videos.
- Throughout the lesson, you'll also find **AI (Artificial Intelligence) Learning Prompts**. These are interactive prompts that let you get immediate feedback from an AI tool on your learning so far.
- After reading through the lesson content, complete the **Assignment**.

If you have questions at any point, ask a question in the `discussion` Slack channel or reach out to your mentor!

# 1.1 Problem Solving

Read this short article on the most important skill in a software developer's toolkit: problem-solving. As you read, look for the three steps in the problem-solving process!

- [Problem-Solving](https://github.com/Code-the-Dream-School/intro-to-programming-2026/wiki/Problem-Solving)


# 1.2 JavaScript Basics

**Reminder: You can _either_ use the written Odin Project lessons _or_ the video lessons in Scrimba. You can do both if you have the time and want to, but using just one or the other will teach what is needed to complete the coding assignments.**

For the Odin Project, Go to each link in this list and read through the content on that page. If there are links you are redirected to as you read/work through the content, follow those links as well and read the content there too.

### Odin Project

- [The Odin Project – Fundamentals Part 1](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/fundamentals-part-1)
- [The Odin Project – Fundamentals Part 2](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/fundamentals-part-2)
- [The Odin Project – Fundamentals Part 3](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/fundamentals-part-3)

### Scrimba

- [V2 Scrimba - JS Deep Dive - Variables and Strings](https://v2.scrimba.com/javascript-deep-dive-c0a/~04)
- [V2 Scrimba - JS Deep Dive - Types & Conditionals](https://v2.scrimba.com/javascript-deep-dive-c0a/~0g)
- [V2 Scrimba - JS Deep Dive - Functions](https://v2.scrimba.com/javascript-deep-dive-c0a/~0q)

### AI Learning Prompt: Retrieval Practice

Now that you've learned about JavaScript variables and data types, let's reinforce your understanding:

1. Open your preferred AI chatbot (CTD's AI Reviewer, ChatGPT, Microsoft Copilot, etc.)
2. Explain in your own words what variables are and why we use them in programming
3. Ask the AI to give you feedback on your explanation

**Example prompt:**

> "I just learned about variables in JavaScript. Here's my understanding: [your explanation]. Can you tell me what I got right and where I could strengthen my understanding?"

### AI Learning Prompt: Predict-then-Check

Let's test your understanding of how JavaScript evaluates conditions.

Study this code without running it:

```javascript
let temperature = 75;

if (temperature > 80) {
  console.log("It's hot outside!");
} else if (temperature > 60) {
  console.log("Nice weather!");
} else {
  console.log("It's cold!");
}
```

Before running it:

1. Predict what will be printed to the console
2. Explain to an AI chatbot **why** you think that output will appear
3. Ask: "Is my reasoning about how JavaScript evaluates these conditions correct?"
4. Run the code and see if you were right
5. If you were wrong, ask the AI to explain what you misunderstood

**Example prompt**

> "Looking at this code: [paste code]. I predict it will print '[your prediction]' because [your reasoning]. Am I correct? If not, what am I misunderstanding about conditional statements?"

# 1.3 JavaScript Naming and Style Conventions

### Read this page on Naming and Style Conventions:

[Naming and Style Conventions](https://github.com/Code-the-Dream-School/intro-to-programming-2026/wiki/Naming-Conventions)

# 1.4 Running Your Code

Running your code is the process where the instructions you have written cause the computer to perform actions. Do not use the AI Reviewer as a substitute for running your code — the AI Reviewer *reads* your code, but it does not run the code.  Run and debug your code (see more information in the next section), before running the AI Reviewer and finally submitting your assignment.

**Examples of running code:**
- Hitting the red "< RUN" button from within the Learns App  (this is how you will run your first 4 javascript lessons)
- Clicking the "Run" button in Visual Studio Code

**The steps in completing the first 4 JavaScript assignments are as follows:**:
- For each question you should:

  - Write your code 
  - Run your code with debugging statements so that you can see the output of those statements in the console
  - Make corrections based on the console output 
  - Once you feel the code is correct based on those debug statements, move onto the next question
- Once you have completed all of the questions in this manner:
  - Run the AI Reviewer
  - Make additional corrections based on the AI Reviewer
  - Submit your code

# 1.5 Debugging Basics

### Read this page on debugging basics:

[Debugging Basics](https://github.com/Code-the-Dream-School/intro-to-programming-2026/wiki/Debugging-Basics)

### Watch this video on debugging basics:

[Debugging Basics Video](https://www.youtube.com/watch?v=RI_QQZlk4gk)

### AI Learning Prompt: Scaffold Removal

As you work on this week's assignment, you'll encounter bugs and get stuck. That's normal! When it happens, try this approach with AI:

**Instead of asking:** "Fix this code for me"

Try this:

> "I'm working on [describe the task]. Here's my code: [paste code]. I'm getting this error: [paste error]. Can you ask me 3 questions that will help me figure out the solution myself?"

Or:

> "I'm stuck on [specific problem]. Can you give me 3 high-level hints for how to approach this without giving me the answer?"

**Remember**: The goal is for YOU to solve the problem. AI tools should guide your thinking, not do the thinking for you.

# 1.6 Software Repositories

A software repository, often called a "repo", is a centralized storage location for code and related files used in software development. A software repository lets you track changes to your code, revert to previous versions, and merge work from different branches.

Software repositories are especially important on projects being developed by a software team where multiple people are working on the same code base. This is true for the majority of software projects.

There are many cloud based software repositories. In this class we will use GitHub which is based on git which is a distributed version control system. We will learn more about git in lesson 2.

### Watch this video on how to create a new GitHub Repository:

[Creating a New GitHub Repository Video](https://www.youtube.com/watch?v=0AVVOi3hUmE)

## Assignment - Create a New GitHub Repository

Create a new repository in your GitHub account by following these steps:

- [ ] Go to your GitHub page and click the Repositories tab
- [ ] Click the green "New" button in the top right
- [ ] Fill in the fields to give your repository a name (use your name-**_classname_** as the name example: `maria-santiago-jupiter`) and description (example: portfolio project for Intro to Programming course with Code the Dream)
- [ ] Be sure PUBLIC is selected and check the "Initialize this repository with: Add a README file" check box.
- [ ] Click "Create Repository"
- [ ] When you submit your assignment this week, please copy and paste the link to the repository you created in the "second link to assignment" field.

## Computer File Structure
As you start using git, it's important to understand computer file structure.

- [File-Structure](https://github.com/Code-the-Dream-School/intro-to-programming-2026/wiki/File-Structure)


## Why Do We Even Use a Version Control System?

Git can seem confusing when you first encounter the workflow, especially when you are working by yourself on a project. It can feel like there are a lot of steps when you are not doing very much.

However, in real development environments, you are usually working on a team where multiple developers are making changes to the same codebase at the same time. Git is designed to manage this complexity safely and efficiently.

Version control systems like Git:
- Allow multiple developers to work on the same codebase without overwriting each other’s work
- Track changes over time so you can see exactly what changed, when it changed, and why
- Allow you to revert to previous versions of your code if something breaks
- Show who made specific changes, which is important for collaboration and accountability
- Let developers work on new features or bug fixes in isolation without affecting the main working version of the code



## Git / GitHub Workflow

The following image shows the entire workflow involved in using Git and GitHub. Pay attention to where files are located in each step - either on your local machine or remote in GitHub.

In this lesson, we have completed the portion of the workflow outlined with the red dashed line. We will work on the remaining workflow in Lessons 2, 3 and 4.
![image](https://github.com/Code-the-Dream-School/intro-to-programming-2026/blob/main/assets/Lesson01/GitFlow-Lesson01.jpg?raw=true)

---

## 🎉 Congratulations on finishing your first lesson in Intro to Programming!

Your next step is to complete the coding assignment. As always, reach out to your mentor if you have questions, and take time to celebrate your hard work.
