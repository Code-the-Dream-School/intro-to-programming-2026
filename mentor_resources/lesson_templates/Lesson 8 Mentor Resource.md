# Lesson 8 Mentor Resource: Asynchronous Programming and Promises

**Resources:**
* [How to use this template, and tips on holding effective mentor sessions](https://github.com/reidrussom/intro-to-programming-2026/tree/main/mentor-resources)
* [CTD AI Reviewer](https://ai-review.codethedream.org/)
* [Link to slide decks](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides)

## Lesson Overview
This week is primarily conceptual. Students learn the difference between synchronous and asynchronous code, why asynchronous programming matters for web applications, and how promises work as a way to handle async operations. The lesson revisits callbacks (from Lesson 4) and explains how promises improve on them. Students don't write promises from scratch — the focus is on understanding the concept as a foundation for next week's Fetch API lesson. There is no heavy coding assignment this week; the assignment focuses on the form and message functionality from the DOM lesson.

This is one of the more abstract weeks. Students may struggle because there's less hands-on coding and the concepts are harder to visualize. Connecting async programming to real-world analogies is key.

---

## Group Mentor Sessions

### Explore Session

**Warm-Up** (5-10 minutes)
- Pose a scenario: "Imagine you're at a restaurant. You order food, then sit and wait. Is that synchronous or asynchronous? Now imagine you order food and check your phone while waiting — which is that?"
- Or ask: "Has anyone ever had a website freeze while loading? Why do you think that happens?"

**I Do** (~15 minutes) - **check out the [slides](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides) for this portion!**
- Explain synchronous vs. asynchronous code using the lesson's analogies:
  - Synchronous: phone calls, face-to-face conversations (blocking — you wait for a response)
  - Asynchronous: text messages, emails (non-blocking — you send and continue with your day)
- Show the synchronous and asynchronous flow diagrams from the lesson.
- Explain promises at a high level: "A promise is JavaScript's way of saying 'I don't have the answer yet, but I promise I'll give it to you when I do — or tell you if something went wrong.'"

**We Do** (15-20 minutes)
- Discussion: "Why can't web applications just wait for everything synchronously? What would happen if your browser froze every time it loaded an image or fetched data?"
- Walk through the three states of a promise together: pending, fulfilled, rejected. Use a real-world analogy: ordering a package online (pending = shipped, fulfilled = delivered, rejected = lost in transit).
- If using breakout rooms: have each group come up with their own real-world analogy for synchronous vs. asynchronous and for promises. Rotate and ask "Can you explain why your example is async?"

**You Do** (15-20 minutes)
- Have students review the Odin Project lesson on asynchronous code and summarize the key points in their own words.
- Or have a student-led discussion where small groups teach each other what they understood from the reading.

**Wrap-Up** (5-10 minutes)
- Check for understanding: "Can someone explain what a promise is in one sentence?"
- Preview next week: the Fetch API — they'll actually use promises to get data from a server. This is where async programming becomes hands-on.
- Reassure students: "It's okay if promises feel abstract right now. Next week you'll see them in action."

---

### Apply Session

**Warm-Up** (5-10 minutes)
- Ask: "How are you feeling about the async/promises concept? What part makes sense? What's confusing?"
- Quick review: "What's the difference between synchronous and asynchronous code?"

**I Do** (~15 minutes)
- Show a simple promise example (even though students won't write their own yet). Walk through `.then()` and `.catch()` syntax.
- Remind students about callbacks from Lesson 4 and explain how promises are an improvement: "Instead of nesting callbacks inside callbacks, promises let us chain `.then()` calls."
- Preview the Fetch API syntax that they'll use next week so students can see where this is heading.

**We Do** (15-20 minutes)
- Since this week is lighter on coding, use this time to review and strengthen students' DOM skills from last week.
- Pull up a student's portfolio (with permission) and work through any issues with the form or message functionality together.
- Or do a code review exercise: show a DOM manipulation code snippet with a few bugs and have students identify the issues.

**You Do** (15-20 minutes)
- Give students time to finish or polish their DOM assignment work (form, messages, remove buttons, styling).
- Encourage students to look ahead at the portfolio rubric to start planning final touches.

**Wrap-Up** (5-10 minutes)
- Ask: "Does the idea of 'I'll get back to you later' for code make more sense now?"
- Point ahead: Fetch API next week — they'll make their first API call and display real data on their portfolio.

---

## 1:1 Session Guide

- **Build rapport**: This is a conceptual week, and some students may feel lost without a concrete assignment. Normalize this: "This is one of those weeks where the reading is more important than the coding."
- **Check understanding**: Ask the student to explain synchronous vs. asynchronous in their own words. Can they give an example of each?
- **Encourage independence**: If the student is behind on the DOM assignment, use this week as catch-up time. Prioritize getting the form functionality working.
- **Goal-setting**: Since the coding load is lighter, suggest the student use this week to review the portfolio rubric and plan what they still need to do.
- **Common sticking points this week**:
  - The abstract nature of promises: students may not see why this matters until next week
  - Confusing callbacks with promises: "Aren't they the same thing?"
  - Not understanding the `.then()` chain pattern
  - Still working through DOM issues from last week (the form, event listeners, remove buttons)
