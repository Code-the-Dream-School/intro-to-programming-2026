# **Loops**

Computers don’t get tired, and they’re really, *really* fast! For that reason, they are well suited to solving problems that involve doing calculations multiple times. In some cases, a computer will be able to repeat a task *thousands* or even *millions* of times in just a few short seconds where it might take a human many hours. (Obviously, speed here depends on the complexity of the calculation and the speed of the computer itself). One way to make a computer do a repetitive task is using a **loop**.

1. Read this [MDN article](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code). It’s a longer one, but make sure you tackle the ‘Active Learning’ sections at the bottom of the page.
2. Once again, same info, slightly different context from [JavaScript.info](http://javascript.info/while-for). (Skim the info if you think you know it all, but **don’t forget the tasks at the end of the page**. You learn best by *doing*.)

# **Arrays**

Strings and numbers may be our building blocks, but as your scripts get more complex, you’re going to need a way to deal with large quantities of them. Luckily, JavaScript has a couple of data types that are used for just that. An Array is simply an ordered collection of items (Strings, numbers, or other things).

- [JS Deep Dive - Module Intro: Arrays](https://scrimba.com/javascript-deep-dive-c0a/~01h)
- [JS Deep Dive - Build Flexible Collection with Arrays](https://scrimba.com/javascript-deep-dive-c0a/~01i)
- [JS Deep Dive - Challenge: Your First Array](https://scrimba.com/javascript-deep-dive-c0a/~01j)
- [JS Deep Dive - Check Element Existence in Arrays](https://scrimba.com/javascript-deep-dive-c0a/~01k)

1. [This tutorial](https://www.w3schools.com/js/js_arrays.asp) is a great introduction.
2. [This article](https://www.w3schools.com/js/js_array_methods.asp) covers some of the most useful built-in array methods. These fundamentals are something you’ll use every day, so don’t rush too much and miss out!
3. [Web Dev Simplified video](https://www.youtube.com/watch?v=7W4pQQ20nJg) explains an overview of arrays in JavaScript in about 6 minutes.

# **Knowledge Check**

This section contains questions for you to check your understanding of the lessons from this week and last week on your own. If you’re having trouble answering a question, click it and review the material it links to.

- [What is an array?](https://www.w3schools.com/js/js_arrays.asp)
- [What are arrays useful for?](https://www.w3schools.com/js/js_arrays.asp)
- [How do you access an array element?](https://www.w3schools.com/js/js_arrays.asp)
- [How do you change an array element?](https://www.w3schools.com/js/js_arrays.asp)
- [What are some useful array properties?](https://www.w3schools.com/js/js_arrays.asp)
- [What are some useful array methods?](https://www.w3schools.com/js/js_array_methods.asp)
- [What are loops useful for?](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code#why_bother)
- [What is the break statement?](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code#exiting_loops_with_break)
- [What is the continue statement?](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code#skipping_iterations_with_continue)

# Scope

In JavaScript, scope defines the accessibility of variables, functions, and objects within different parts of your code. It determines where these elements are visible and can be referenced. 

https://www.w3schools.com/js/js_scope.asp


# Version Control System / Git

Last week, we learned about GitHub which is an online platform used to host software repositories. You created your first repository. This week, we are going to learn about Git which is the version control system used by GitHub to manage your software repository. Although there are other version control systems, Git is the most widely used.

A version control system is a software tool that tracks and manages changes to files and directories over time. It allows multiple developers to collaborate on a project, maintain a history of all changes, and easily revert to previous versions if needed. It is essential for a development team that is working in the same code base.

Git can be confusing when you first start learning about it. There are quite a few steps which might seem unnecessary, but will definitely make sense when you are working in a team environment.

When you created your GitHub repository, you created a repository in a cloud environment. While you can edit files remotely, you will want to have your code in a local development environment where you can easily run and debug it. This week, we are going to copy our software repository to our local computer.  This is called cloning.  There are gui interfaces that will let you submit git commands, but we are going to learn how to submit the commands through a terminal interface.

## Installing and Setting Up Git
The following information will help you setup git on your local machine.

- [The Odin Project – Setting Up Git](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/setting-up-git)

The Odin link does not provide a link to the Windows installer which can be found here:
- [Windows Installer](https://git-scm.com/downloads/win)

After installing, follow the rest of the instructions on the Odin page for setting up Git.

**TODO - Video - Clone Repo**

## Assignment - CLONE your GitHub Repository to your local machine
Clone the repository you just created in GitHub to your local computer by following these steps:
   - [ ] On the main Code page of your GitHub repository, click the green "Code" button
   - [ ] Your lesson walked you through setting up an SSH key with GitHub.  You should select "SSH" as the Local Clone type (not HTTPS or GitHub CLI).
   - [ ] Click the copy button (two overlapping squares icon) to copy your repository address.  It should look something like `git@github.com:yourUsernameHere/firstname-lastname-class.git`
   - [ ] Go to your IDE terminal or your computer terminal.  Make sure you're in the proper directory for where you want to create and store files for your work (ex. your Desktop or a CodeTheDream folder).  Then run `git clone <repository>` where "\<repository\>" is replaced with the last portion you copied in the last step.

## Git / GitHub Workflow
The following image shows the steps involved in using Git and GitHub.  Pay attention to where files are located in each step - either on your local machine or remote in GitHub.  
We will work on the entire workflow in pieces over Lessons 2, 3 and 4.

![image](https://github.com/Code-the-Dream-School/intro-to-programming-2026/blob/main/assets/GitFlow.jpg?raw=true)
