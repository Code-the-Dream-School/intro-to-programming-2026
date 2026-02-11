---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 11: Final Project"
---

# Lesson 11: Final Project

**Mentor Session Slide Deck**

Topics: Rubric Review, Final Polish, Project Demo Prep, Celebration

---

# You Made It! 🎉

**Week 1**: "What's a variable?"

**Week 11**: You've built a **portfolio website** with:
- Styled HTML/CSS layout
- Dynamic JavaScript (DOM manipulation)
- Form handling with events
- API integration (GitHub repos + Open API)

That's real web development. Let's make sure it shines.

---

# This Week's Goals

1. **Finish** any remaining work on your portfolio and Open API pages
2. **Review** both rubrics to make sure you meet all requirements
3. **Record** a 3-5 minute demo video of your project
4. **Submit** your final project and recording

No new concepts this week — it's all about **polish and presentation**.

---

# Portfolio Rubric Checklist

Does your portfolio include:

- [ ] HTML boilerplate with title and meta tags
- [ ] Your name in an `<h1>`
- [ ] About, Experience, and Connect sections
- [ ] Navigation that links to each section
- [ ] Skills section populated from a JavaScript array
- [ ] Projects section populated from GitHub API fetch
- [ ] Message form with submit, display, and remove functionality
- [ ] Footer with your name and current year (from JavaScript)
- [ ] CSS styling (colors, fonts, layout, Flexbox)

---

# Open API Rubric Checklist

Does your Open API page include:

- [ ] Separate HTML, CSS, and JS files
- [ ] Two distinct API calls to your chosen API
- [ ] Data from both calls displayed on the page
- [ ] Navigation linking to your portfolio page (and back)
- [ ] Styled with CSS
- [ ] Error handling for failed API calls

**Review the full rubrics** for details on each requirement.

---

# Peer Review Activity

**Pair up** and check each other's projects:

1. Open your partner's portfolio page in a browser
2. Walk through the rubric checklist — does everything work?
3. Click every nav link — do they jump to the right section?
4. Submit a test message in the form — does it display? Can you remove it?
5. Check the Projects section — are GitHub repos loading?
6. Navigate to the Open API page — do both API calls display data?
7. Navigate back — does the link work?

**Give feedback**: What looks great? What's missing or broken?

---

# Common Last-Minute Fixes

| Issue | Quick Fix |
|-------|-----------|
| Nav links don't work | Check `href="#sectionId"` matches the `id` attribute exactly |
| Skills/Projects not showing | Check the browser console for JS errors |
| Form refreshes the page | Make sure `event.preventDefault()` is the first line in your handler |
| Footer shows wrong year | Use `new Date().getFullYear()`, not a hardcoded number |
| Open API data not loading | Log the response to see what you're getting back |
| CSS not applying | Check the `<link>` tag `href` path |

---

# Recording Your Demo

Your 3-5 minute video should show:

1. **Portfolio walkthrough**: Scroll through to show layout and styling
2. **Form demo**: Submit 1-2 messages, show remove functionality
3. **Navigate** to your Open API page
4. **Open API walkthrough**: Show both API endpoints displaying data
5. **Navigate** back to your portfolio
6. **Reflect**: What was the most challenging part? What did you enjoy most?

**Recording options**: Zoom (personal meeting), screen recorder (Mac/Windows built-in), or Loom.

---

# Tips for a Great Demo

- **Practice once** before recording — it doesn't need to be perfect!
- **Talk about your choices**: "I chose this API because..." or "I'm proud of how this section turned out because..."
- **It's okay to mention challenges**: "The form was tricky because..." shows self-awareness
- **Keep it to 3-5 minutes** — focused and concise
- **Upload as Unlisted on YouTube** so only people with the link can see it

---

# Reflection: Your Growth

**Think about**:

- What concept was the hardest to learn? How did you push through?
- What are you most proud of building?
- What would you do differently if you started over?
- What do you want to learn next?

**Share with the group**: One highlight and one challenge from the course.

---

# Submission Checklist

- [ ] All open pull requests are **merged** into main
- [ ] Portfolio meets rubric requirements
- [ ] Open API page meets rubric requirements
- [ ] Demo video is **recorded** (3-5 minutes)
- [ ] Video is **uploaded** to YouTube (Unlisted)
- [ ] Assignment submission form is filled out with repo link and video link
- [ ] Assessment is completed (emailed separately)

---

# What's Next?

You now have a foundation in:
- **JavaScript** — variables, functions, loops, objects, DOM, async, APIs
- **HTML & CSS** — structure, style, layout, Flexbox
- **Git & GitHub** — version control, branching, pull requests
- **Problem-solving** — pseudocode, debugging, reading documentation

These are the same tools professional web developers use every day. You're ready for the next step — whatever course or path you choose.

**Congratulations!** 🎉
