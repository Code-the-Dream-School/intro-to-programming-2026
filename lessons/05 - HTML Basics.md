
# 1.1 How the Web Works

Read then following article: **[How Does the Web Work?](../assets/Lesson05/Lesson05-How-Does-the-Web-Work.md)**

## AI Learning Prompt: Retrieval Practice

1. Open your preferred AI chatbot (CTD’s AI Reviewer is a great choice).
2. In your own words, explain what happens when you load a webpage — from typing in a URL to seeing an interactive page. Try to include DNS, HTTP/HTTPS, and the roles of HTML, CSS, and JavaScript.
3. Share your explanation with the AI and ask it to tell you what you explained clearly and point out anything that’s missing or slightly incorrect.
4. Revise your explanation based on the feedback.

**Example Prompt**:

>“I just learned how the web works. Here’s my understanding of what happens when I load a website:[your explanation]. Can you tell me what I got right, what I might be missing, and where I could improve my understanding?”

# 1.2 HTML Basics

### The Odin Project Links:

- **[The Odin Project - Introduction to HTML and CSS](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/introduction-to-html-and-css)**
- **[The Odin Project - Elements and Tags](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/elements-and-tags)**
- **[The Odin Project - HTML Boilerplate](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/html-boilerplate)**
- **[The Odin Project - Working with Text](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/working-with-text)**
- **[The Odin Project - Lists](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/lists)**
- **[The Odin Project - Links and Images](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/links-and-images)**

### Scrimba Links:

- **[Scrimba - HTML & CSS Crash Course](https://v2.scrimba.com/html-css-crash-course-c02l)**

Watch the following sections:
- **Let's write some HTML!**
- **strong and emphasis**
- **File naming and organization**
- **Anchors and Attributes!**
- **Lists**
- **Images**

## HTML Overview

*Hypertext Markup Language (created in 1989)*, commonly called *HTML*, is a markup language that is used to create the structure of a web page. The basic idea of HTML is that the brackets < > surrounding the code of a web page tell the web browser what information it's working with.

At its core, hypertext is digital text that can link to other places, such as one website connecting to another. HTML, a markup language, uses tags like **`<head>`** and **`<body>`** to structure web content in a way that browsers can display. Unlike technical programming code, HTML uses human-readable words, making it user-friendly for web content creation.

HTML is the foundational component of a website adding these elements to a web page:

- Text: Words and written content
- Media: Images, videos, and other visual or auditory elements
- Links: Clickable paths to other places, like other websites
- Containers: Elements that are used to give web pages structure for layout purposes

### Element vs Tag vs Attribute

HTML **_elements_** are the basic building blocks of a webpage. Each HTML element represents a different type of content (such as a link, image, heading, list, paragraph, etc.). Each HTML element is represented using 1 or 2 tags.

An HTML **_tag_** is how we code an HTML element. All tags use **brackets** <>. Some HTML elements are represented by writing only 1 tag. For example, this 1 tag represents an image element in HTML:

```html
<img src="myPhoto.jpg" alt="This Is My Photo">
```

Some HTML elements need 2 tags: an _opening tag_ and a _closing tag_ (sometimes called a _begin tag_ and an _end tag_, respectively). Here are some examples:

```html
<p>This is my paragraph's content. Notice the opening tag is a bit different from the closing tag.</p>
```

In the HTML element above, notice that it has an opening tag: `<p>`. The closing tag for this element is very similar to its opening tag, but it has a / in it: `</p>`  Here are more examples of elements with 2 tags:

```html
<h1>Here is a heading type of HTML element.</h1>

<div class='mySpecialClassName'>Some tags have additional attributes. Notice the end tag remains simple. The end tag doesn't have the extra attributes of the begin tag.</div>
```

For html elements which require 2 tags, the end tag will look very similar to the begin tag. Except, the end tag will have the `/` character in it.

## AI Learning Prompt: Predict-then-Check

Study this snippet of HTML code without opening it in a browser:

```html
<ul>
  <li>Apples</li>
  <li>Bananas</li>
</ul>
```

1. Predict how this will look on a web page.
2. Explain to an AI chatbot why you think it will look that way, specifically identifying what the `<ul>`and `<li>` tags represent.
3. Ask: "Is my reasoning about how these list tags work correct?"
4. Check your prediction by searching for "HTML list elements" or running the code in a text editor.

# 1.3 IDEs and Visual Studio Code

To write HTML and JavaScript effectively, developers use an **IDE (Integrated Development Environment)**. IDEs are helpful programs that combine several tools (a text editor, the command line/terminal, file organization, and more) into one program. The most popular IDE is **Visual Studio Code** (abbreviated VS Code).

If you aren't currently using an IDE of your own preference, watch the video below and install VS Code and the suggested extensions before you start this week's assignment.

* [Visual Studio Code Info Session with Shawn Clary](https://www.youtube.com/watch?v=R8lusLkuWJQ)
* [Browser debugging in VS Code](https://code.visualstudio.com/docs/nodejs/browser-debugging)

## 5.4 AI Learning Prompt: Scaffold Removal
As you begin writing your own HTML files in Visual Studio Code, you may find that your images don't appear or your links don't work. Instead of asking an AI to write the code for you, use it to guide your troubleshooting.

**Example Prompt for a Bug**:

> "I'm trying to add an image to my HTML page, but it's showing a 'broken' icon instead of the picture. Here is my code: [paste code]. Can you ask me 3 questions that will help me figure out why the path might be wrong?"

**Example Prompt for a Hint:**
> "I'm stuck on how to nest a link inside a paragraph. Can you give me 3 high-level hints for how to structure the tags without giving me the final code?"

# 🥳 Great job on Lesson 5!
You're well on your way to becoming a skilled developer. Attend a mentor session and ask for help – we're rooting for you!
