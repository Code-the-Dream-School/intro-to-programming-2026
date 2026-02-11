# Lesson 10 Mentor Resource: Open API

**Resources:**
* [How to use this template, and tips on holding effective mentor sessions](https://github.com/reidrussom/intro-to-programming-2026/tree/main/mentor-resources)
* [CTD AI Reviewer](https://ai-review.codethedream.org/)
* [Link to slide decks](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides)

## Lesson Overview
This week students explore open-source APIs and build a second page for their project. They choose from several API options (weather, Star Wars, Marvel, art, dogs/cats, soccer), learn about API keys, and create a new HTML/CSS/JS file that makes two distinct API calls and displays the returned data. They also link this new page to their portfolio via navigation. This is a creative, open-ended assignment that lets students apply everything they've learned.

This lesson is designed to give students autonomy and ownership. It's less prescriptive than previous weeks, which can be both exciting and intimidating. Mentors should help students pick an API, plan their approach, and troubleshoot issues without over-directing.

---

## Group Mentor Sessions

### Explore Session

**Warm-Up** (5-10 minutes)
- Ask: "Which of the API options sounds most interesting to you? Has anyone already picked one?"
- Or: "What kind of data would you love to be able to pull into a website?"

**I Do** (~15 minutes) - **check out the [slides](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides) for this portion!**
- Walk through the list of available APIs. Briefly show the documentation for 2-3 of them (e.g., Open-Meteo for simplicity, TheDogAPI for fun).
- Explain what an API key is and why some APIs require one. Show how to get a key from one of the APIs.
- Demo making a fetch call to one of the APIs and exploring the returned data in the console.

**We Do** (15-20 minutes)
- Discussion: "How do you figure out what URL to use and what data you'll get back?" Walk through reading API documentation together using one of the listed APIs.
- Help students brainstorm what two distinct API calls they want to make. For example, with a weather API: current temperature and weekly forecast.
- If using breakout rooms: group students by which API they chose and have them explore the documentation together and plan their two API calls. Rotate and ask "What endpoint are you using? What does the response look like?"

**You Do** (15-20 minutes)
- Have students start setting up their new page: create the HTML file, CSS file, and JS file.
- Challenge: "Can you make your first fetch call and log the response to the console?"

**Wrap-Up** (5-10 minutes)
- Ask: "What API did you pick and what are you planning to display?"
- Remind students to link the new page to their portfolio via the nav bar.
- Point ahead: next week is the final project week — finishing touches on both pages.

---

### Apply Session

**Warm-Up** (5-10 minutes)
- Ask: "How is the Open API project going? Has anyone gotten data to display on their page?"
- Quick question: "What are the two distinct API calls you're making?"

**I Do** (~15 minutes)
- Demo a common pattern: fetching data, parsing it, and displaying it in the DOM.
- Show how to handle API keys: storing them in a constant and including them in the request.
- Walk through linking the new page to the portfolio using a `<nav>` element with `<a>` tags, including a link back to the home page.

**We Do** (15-20 minutes)
- Troubleshoot together. Common issues at this stage:
  - API returns unexpected data format: look at the response in the console and trace the path to the data you need
  - CORS issues: some APIs don't allow browser requests directly
  - API key not working: check the docs for how it needs to be included (query parameter vs. header)
- Review a student's code (with permission) and work through any bugs as a group.

**You Do** (15-20 minutes)
- Give students focused work time on their Open API page. This is the most independent assignment so far.
- Mentors should circulate and help with specific issues rather than general instruction.

**Wrap-Up** (5-10 minutes)
- Quick progress check: where is everyone? Do they have data displaying?
- Remind students to review both rubrics (portfolio and Open API) before next week.
- Point ahead: final project week — polish and submit.

---

## 1:1 Session Guide

- **Build rapport**: This is a creative week. Ask the student why they chose their API and what they're excited to build.
- **Check understanding**: Ask the student to show you their fetch calls. Can they explain the URL they're using and what data they expect back?
- **Encourage independence**: This is the most open-ended assignment. Resist the urge to design the page for them. Instead, ask: "What do you want the user to see? How would you organize that on the page?"
- **Goal-setting**: Help the student set specific milestones: "By the end of today, try to have your first API call displaying data. Then work on the second call."
- **Common sticking points this week**:
  - Choosing an API: analysis paralysis. Help them pick one and start.
  - Reading API documentation: students may not know how to find the right endpoint or understand query parameters
  - API keys: not knowing where to put them (in the URL, in a header, etc.)
  - Displaying data: forgetting to navigate the JSON response to the right level (e.g., `data.results[0].name` vs. just `data`)
  - Linking pages: the `<a href="openapi.html">` pattern for navigating between pages in the same project
