---
marp: true
theme: default
paginate: true
style: |
  section {
    background-color: #FFFFFF;
    color: #1C1C1C;
    font-family: 'Segoe UI', Arial, sans-serif;
  }
  h1 {
    color: #12284C;
    border-bottom: 3px solid #FF5C35;
    padding-bottom: 6px;
    margin-bottom: 12px;
  }
  h2 { color: #12284C; }
  h3 { color: #FF5C35; }
  pre {
    background-color: #1C1C1C;
    border-left: 5px solid #FF5C35;
    border-radius: 4px;
  }
  code {
    background-color: #F1F2F2;
    border-radius: 3px;
    padding: 1px 5px;
    color: #12284C;
  }
  pre code {
    background-color: transparent;
    color: #F1F2F2;
    padding: 0;
  }
  blockquote {
    border-left: 4px solid #F3C300;
    background-color: #F1F2F2;
    padding: 8px 16px;
    border-radius: 0 4px 4px 0;
    color: #12284C;
    margin: 8px 0;
  }
  section.title {
    background-color: #12284C;
    color: #FFFFFF;
    text-align: center;
  }
  section.title h1 {
    color: #F3C300;
    border-color: #FF5C35;
  }
  section.title h2,
  section.title h3,
  section.title p {
    color: #F1F2F2;
    border: none;
  }
  section.section-break {
    background-color: #FF5C35;
    color: #FFFFFF;
    text-align: center;
  }
  section.section-break h1 {
    color: #FFFFFF;
    border: none;
    font-size: 2.8em;
  }
  section.section-break h2,
  section.section-break p {
    color: #FFFFFF;
    border: none;
  }
  section.cfu {
    background-color: #F1F2F2;
  }
  section.cfu h1 {
    color: #12284C;
    border-bottom-color: #F3C300;
  }
---

<!--
MENTOR SETUP — Read before presenting. This is not a slide.

Opening Marp:
  VS Code: Install the Marp extension → open this file → "Open Preview" → fullscreen
  Browser: marp.app → paste this markdown → present from browser

Two-mentor structure (suggested):
  Mentor 1 leads the opening and Explore section (slides 2–9).
  Mentor 2 leads the Apply section and closing (slides 10–21).
  Both mentors stay on screen throughout. The off-lead mentor should monitor chat
  and be ready to jump in with encouragement or quick answers.

Session notes:
  This is the final session — there is no new content. The goal is to help students
  finish strong, feel celebrated, and leave with a clear path to submission.
  Keep the Explore recap moving quickly (20–25 min) so the bulk of session time
  goes toward project work. Be generous with praise today.
-->

<!-- _class: title -->

# Lesson 11: Final Project

## Intro to Programming — Code the Dream

<!--
Welcome students warmly. Acknowledge that this is the last session.
A simple "We are really proud of how far you've come" goes a long way here.
-->

---

# Session Overview

**Today's session is about you and your project.**

- Reflect on everything you've learned over the past 11 weeks
- Review the final project requirements and submission checklist
- Spend the bulk of the session working on your project with mentor support

> There is no new content today — this time belongs to you.

<!--
Keep this brief. Students are eager to get to work. Let them know the recap
will be short so most of the time is open for project help.
-->

---

<!-- _class: section-break -->

# Explore

<!--
Mentor 1 leads this section.
Goal: short, celebratory recap of the full course arc.
This is not a test — it's a reminder of how much they've built.
Target time: 20–25 minutes for the full Explore section.
-->

---

# 11 Weeks in One Slide

**You started from scratch. Here's what you built:**

| Week | Topic |
|------|-------|
| 1 | JavaScript basics: variables, data types, functions |
| 2–3 | Loops, arrays, objects |
| 4–5 | HTML & CSS — structure, styling, layout |
| 6 | The DOM — selecting and manipulating elements |
| 7 | Forms and events — responding to user input |
| 8 | Algorithms and callbacks |
| 9 | Fetch and async — pulling real data from APIs |
| 10 | Putting it all together — portfolio and Open API page |

<!--
Don't linger here — this is a visual celebration, not a re-teach.
Read a few rows aloud, then say something like:
"Every one of those topics is now inside your project."
-->

---

# The Arc of the Course

**Three big phases:**

1. **The language** — Learning to speak JavaScript (variables, loops, functions, objects)
2. **The browser** — Making things appear and respond (HTML, CSS, DOM, events)
3. **The internet** — Connecting to the outside world (Fetch, APIs, async)

> Your final project uses all three.

<!--
This framing helps students see their work as a coherent whole rather than
a list of disconnected topics. Pause here and let it land.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**Which of these concepts did you use in your portfolio project?**
*(Select all that apply — unmute or drop them in the chat)*

- A) Writing and calling functions
- B) Looping through an array to display items
- C) Handling a form submit event
- D) Using `fetch()` to get data from an API
- E) Selecting and creating DOM elements

<!--
This is meant to be reflective, not evaluative. All answers are likely correct.
The goal is for students to recognize how much of the course they actually applied.
If time allows, ask a student to briefly describe one of the things they used.
-->

---

# Concepts That Stick

**A few things worth remembering long after this course:**

- **Functions** — every program is built from reusable pieces
- **Arrays + loops** — the pattern for displaying any list of data
- **Events** — how the browser listens and responds to users
- **Fetch + async/await** — how modern apps talk to servers
- **Git and GitHub** — how developers share and protect their work

> These aren't just Intro to JavaScript concepts — they are the foundations of every web application you'll ever build.

<!--
Frame this as "you now have a foundation" rather than "you've learned everything."
Encourage students who feel like they don't fully understand everything yet —
that's normal and expected at this stage.
-->

---

<!-- _class: cfu -->

# Check for Understanding

**Looking back at the course, which topic felt like the biggest breakthrough moment for you?**

*(Drop it in the chat — no wrong answers)*

- A) Getting a function to return the right value
- B) Making something appear or change on the page
- C) Handling user input from a form
- D) Seeing real data load from an API
- E) Something else entirely

<!--
This is a celebration question as much as a reflection question.
Read a few responses aloud and react warmly to each one.
This builds energy going into the work session.
Transition: "That's the exact kind of thing your project shows off. Let's make sure it's ready."
-->

---

<!-- _class: section-break -->

# Apply

<!--
Mentor 2 leads from here (suggested).
The Apply section covers: project requirements, submission checklist, tips, and open work time.
Students should spend at least 25–30 minutes on actual project work.
-->

---

# Final Project: Two Parts

**Part 1 — Portfolio Page** (`index.html`)

- About, Experience, Skills, Projects, and Leave a Message sections
- Dynamic footer with copyright year
- Skills rendered from a JavaScript array
- Message form: submit, display, and remove messages
- GitHub repositories fetched and displayed from the API

**Part 2 — Open API Page** (`openapi.html`)

- Two separate GET requests to two different endpoints
- Navigation between the two data views
- Error handling for failed requests
- Linked from your portfolio — and links back

<!--
Don't read this slide word for word. Walk through each part at a normal pace
and invite students to say "yep, got that" or flag anything they're uncertain about.
-->

---

# Portfolio Rubric — Key Requirements

**HTML**
- Valid boilerplate, semantic structure, internal navigation links, all five sections present

**JavaScript**
- Footer copyright year generated dynamically
- Skills list rendered from an array using a loop
- Message form: validates input, displays messages, includes remove buttons
- GitHub repos fetched via the API and displayed on the page

**CSS**
- Flexbox used for layout
- Clean, readable styling throughout

> Full rubric: linked in your lesson materials on Canvas/Slack

<!--
Encourage students to use the rubric as a literal checklist.
If they're not sure about something, that's a great use of work time.
-->

---

# Open API Rubric — Key Requirements

**Structure**
- Separate HTML, CSS, and JavaScript files
- Linked from portfolio nav, with a link back to the portfolio

**JavaScript**
- Two distinct GET requests to two different API endpoints
- Clear navigation so users can switch between the two data views
- Error handling (e.g., a message shown if the fetch fails)

**Presentation**
- Data displayed in a readable, styled format
- Code is clean and organized

> Full rubric: linked in your lesson materials on Canvas/Slack

<!--
The most common gap here is students who built one fetch but not two,
or who have no navigation between endpoints. Flag this proactively.
-->

---

# Submission Checklist

Before you submit, confirm all of this:

- [ ] All open pull requests are merged into `main`
- [ ] Portfolio page meets the Portfolio Rubric
- [ ] Open API page meets the Open API Rubric
- [ ] Code runs without errors in the browser
- [ ] Final project **repository URL** submitted on Canvas
- [ ] Project **demo video** recorded (3–5 min) and uploaded as Unlisted on YouTube
- [ ] Demo video link submitted on Canvas

> When in doubt, open the rubric and go line by line.

<!--
Walk through this checklist out loud. Ask students to give a thumbs up
or drop a number in the chat for how many items they've completed.
This helps you prioritize who needs the most support during work time.
-->

---

# Demo Video — What to Cover

Your 3–5 minute video should walk through:

1. Scroll through your **portfolio** to show layout and styling
2. Demo the **message form** — submit a message, show it on the page, remove it
3. Switch to your **Open API page**
4. Show **both endpoints** loading data with navigation between them
5. Share **what challenged you most** and **what you enjoyed most**

> You can record with Zoom, your computer's screen recorder, or Loom.

<!--
Some students get nervous about the video. Reassure them it's not a performance —
it's just a walkthrough. Imperfect is fine. The goal is to show the work and
practice talking about code, which is a real job skill.
-->

---

# Tips for Finishing Strong

1. **Work from the rubric** — check off each item as you confirm it works
2. **Functionality before polish** — get everything working before tweaking styles
3. **Test in the browser often** — save, refresh, check the console after every change
4. **Use DevTools** — Console tab for JavaScript errors, Elements tab for layout issues
5. **Merge early** — don't wait until the last minute to merge your PRs
6. **Ask for help** — your mentors are here right now, and Slack is always open

> The finish line is closer than it feels.

<!--
Keep the energy positive here. If a student seems stuck or anxious,
this is a good moment to say "let's tackle that together during work time."
-->

---

# Work Session

**The next 25–30 minutes are yours.**

Here's how to make the most of it:

- **Unmute or use the chat** to ask questions anytime
- **Share your screen** if you want debugging help — mentors will jump in
- **Use breakout rooms** if you'd like one-on-one support

If you're already in good shape: help a classmate, or review your demo video script.

<!--
Both mentors should actively circulate during this time.
Check in with each student by name if possible — even a quick "how are you doing
on the submission checklist?" keeps students engaged and surfaces blockers early.
Prioritize students who are behind or haven't started the video yet.
Students who are done can be paired as peer reviewers for each other.
-->

---

# Wrap-Up

**Zoom chat:**

> What's one thing you know now that you didn't know 11 weeks ago?

Take a moment and type it out — we want to read them.

<!--
Read as many responses as time allows. Celebrate each one genuinely.
This is the payoff moment for the whole course — don't rush past it.
Then transition to the closing slide.
-->

---

# What's Next

You've completed **Intro to Programming**!

Once your final project is reviewed and you've passed the course assessment:

- You will officially **graduate** from this course
- You'll be ready to advance to your **next course** in the CTD curriculum
- Keep building, keep asking questions, and stay connected on **Slack**

> The CTD community — your classmates, mentors, and staff — is always here.

<!--
If you know what the next course is, mention it by name.
Remind students to check Slack for the course assessment link if they haven't taken it yet.
-->

---

# Resources

| Resource | What it's for |
|----------|---------------|
| Portfolio Rubric | Full checklist for your portfolio page |
| Open API Rubric | Full checklist for your Open API page |
| MDN Web Docs | Reference for HTML, CSS, and JavaScript |
| GitHub Docs | Help with pull requests and merging |
| Slack `#discussion` | Questions anytime, even after the course |

> Rubric links are in your Lesson 11 materials on Canvas.

<!--
Keep this brief. Students know where to find things at this point.
The main message is: the rubrics are their best friend for submission.
-->

---

<!-- _class: title -->

# Congratulations!

## You are a programmer.

Thank you for an incredible course. We cannot wait to see what you build next.

<!--
Pause here. Let this land.
If there's time, invite each student to unmute for a brief goodbye.
-->
