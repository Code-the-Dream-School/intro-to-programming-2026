## Get organized and write some code!
   - [ ] Create a new local branch to house just the work you'll do for this assignment by running `git checkout -b lesson-5` in the terminal which creates a new branch and automatically switches to it
   - [ ] Open the README.md file in your code editor and add your full name.
   - [ ] Create a new file in your project directory (at same level as your README.md file) and title it `index.html`

## Assignment: Task List / Deliverables
In your `index.html`, you will write the HTML "boilerplate" - the standard, required structure used as a starting point for all web pages. While copying and pasting this code is common in professional development, you will write it from scratch this week to fully understand how each element functions. 

Below is a line-by-line breakdown of the HTML boilerplate:

> **Quick Review: HTML Anatomy**
> 
> Before diving into the breakdown, remember these three key concepts:
> 
> * **Elements vs. Tags:** An **element** is the whole package. It usually consists of an **opening tag**, the **content**, and a **closing tag**. 
>   * *Example:* `<title>My Web Page</title>` is a `<title>` element.
> * **Self-Closing Tags:** Some elements don't wrap around text and close themselves in a single tag.
>   * *Example:* `<meta charset="utf-8">` or `<img src="logo.png">`
> * **The Visible Page:** The boilerplate contains background setup data, but the bulk of your actual website content (what users see) will always live inside the `<body>` element.

### HTML Boilerplate

#### - Doctype
First let's define what type of document the browser will be reading.
   - [ ] Define the document type at the top of the file by typing in `<!DOCTYPE html>` on line 1.

#### - Head Element
The "head" of an HTML document contains all the page's meta information, such as title and description.  This information helps with web searches and displays the page title in the browser tab.
   - [ ] Before your name, but after the `<html>` opening tag, insert a `<head>` element.
   - [ ] Inside the `<head>` element, add a `<title>` element to title your webpage (ex. Maria Santiago's Portfolio)
   - [ ] Below your `<title>` element, add additional `<meta>` elements (at least two) from the meta elements you've learned about and/or find at this resource: [W3Schools HTML Head](https://www.w3schools.com/html/html_head.asp))

#### - Body Element
The "body" of an HTML document contains all the page's visible content.
   - [ ] After the closing `</head>` tag, begin the body of your page by adding the opening `<body>` element. 
   - [ ] Close the body of your page by adding the closing `</body>` element right before the closing `</html>` tag
   - [ ] Confirm that all of the following content is inside the `<body>` tags, in this order:
     - [ ] Your name in an `h1` element
     - [ ] The word 'About' in an `h2` element
     - [ ] A paragraph about you in a `p` element
     - [ ] The word 'Experience' in an `h2` element
     - [ ] Your listed experiences in a `ul` element, with each individual item in a `li` element.  Experiences can be courses you've taken, coding/tech languages you've learned, technologies you've worked with, or other experiences that highlight your value.
     - [ ] The word 'Connect' in an `h2` element
     - [ ] Your social media links in `a` elements, and you can also wrap them in `ul` and `li` tags if you wish.  Include at least two, your GitHub and LinkedIn profiles.  You can include more (Facebook, YouTube, Instagram, WhatsApp, TikTok, Discord, X, etc.) if you like.

#### - Additional Elements
HTML describes the structure of a webpage using various semantic elements, such as: headings, paragraphs, lists, and more, as you just saw by writing content for the body of your page.  Now let's organize that content...
   - [ ] Wrap each of the About, Experience, and Connect sections in a `<section>` element.  You’ll use this later when styling your webpage to stay organized and apply different style settings to each section.
   - [ ] Give each of these sections an "id" property with the same name as the section.  Example:  The About section would look like this:

``` jsx
<section id="About">
   <h2>About</h2>
   <p>
      This is a paragraph about me.  Here's more info about me.
   </p>
</section>
```
   - [ ] STRETCH GOAL (optional):  Feel free to use even more HTML elements by adding images, navigation menus, etc.

By the end of this lesson, your `index.html` file must include:

**1. Page Setup & Metadata**
* The HTML boilerplate code so the browser knows how to render the page.
* Metadata about your page (such as the `<title>` and keywords).

**2. Visible Page Content**
* **Your Name** as the main heading.
* **About Section:** An "About" header followed by a short paragraph about yourself.
* **Experience Section:** An "Experience" header followed by a list of your professional or personal experiences.
* **Connect Section:** A "Connect" header containing at least two working links (e.g., your LinkedIn or GitHub).
## Back up to the cloud
Once you've made the above changes to your html file, follow the below instructions to push a copy from your local machine like you did at the end of last assignment.  Confirm that your code gets copied to GitHub by adding changes to staging, committing the staged changes, and pushing them from your local machine to GitHub:
   - [ ] Check the status of the changes you just made (editing the index.html file) by running `git status` in your terminal
   - [ ] Stage all your changes for commit by running `git add .` in your terminal
   - [ ] Run `git status` again to see how things have changed.  You should get a response indicating changes staged for commit.
   - [ ] Create a commit message for reference.  You can use a different message if you wish.  Run `git commit -m "boilerplate and content added"`
   - [ ] Push these changes to your GitHub repository from your local computer by running `git push`

## Submit Assignment
Now let's make sure that lesson branch will be reviewed.
   - [ ] Go to your GitHub repository page in your web browser now, and you should see a "lesson-5 has a recent push" notice with a green "Compare & pull request" button.  Click that button
   - [ ] Feel free to put notes to yourself or notes for your reviewer in the description (be sure you're including any questions to your reviewer in your assignment submission form though!) and click the green "Create pull request" button.
   - [ ] Copy the address of your pull request page (should look like `https://github.com/yourUsername/name-classname/pull/#`) and paste it into your assignment submission form.

## What next?
   - If you are ready to start on the next lesson and have not gotten your review comments back yet, you can go ahead and merge your pull request and continue working.
   - if you are unsure about your work this week, schedule a 1:1 session with a mentor and review your work together before merging.
