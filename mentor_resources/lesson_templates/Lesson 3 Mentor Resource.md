# Lesson 3 Mentor Resource: JavaScript Objects

**Resources:**
* [How to use this template, and tips on holding effective mentor sessions](https://github.com/reidrussom/intro-to-programming-2026/tree/main/mentor-resources)
* [CTD AI Reviewer](https://ai-review.codethedream.org/)
* [Link to slide decks](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides)

## Lesson Overview
This week students learn about JavaScript objects: creating them, accessing and modifying properties, iterating over them with `for...in`, adding methods, using constructors, and working with the built-in `Date` object. On the Git side, students learn to commit changes and push them to their remote repository. The assignment has students build pet objects, write comparison functions, use `this` keyword, and work with dates.

Objects are a critical data structure that students will use heavily when they get to the DOM, Fetch API, and working with JSON data later in the course. This is also where students complete a key part of the Git workflow — committing and pushing.

## Group Mentor Sessions

### Explore Session

**Warm-Up** (5-10 minutes)
- Review question: "What's the difference between an array and a variable that holds a single value? When would you use an array?"
- Or pose a scenario: "Imagine you want to store information about a pet — its name, species, and color. How would you do that with what we've learned so far? Is there a better way?"

**I Do** (~15 minutes) – **check out the [slides](https://github.com/reidrussom/intro-to-programming-2026/tree/main/slides) for this portion!**
- Demo creating an object with properties. Show dot notation and bracket notation for accessing values.
- Show how to add, modify, and delete properties.
- Briefly demo a `for...in` loop to iterate over an object's properties.

**We Do** (15-20 minutes)
- Discussion: "How are objects different from arrays? When would you choose one over the other?"
- Work through an example together: create an object representing a student (name, grade, enrolled), then write a method on it that returns a description string using `this`.
- If using breakout rooms: have each group create an object representing something (a movie, a recipe, a game character) and practice accessing properties. Rotate to prompt groups: "Can you add a method to your object?"

**You Do** (15-20 minutes)
- Have students create a constructor function for a `Book` (or similar) with 3 properties, then create 2 instances and log them.
- Or have students try writing a function that compares two objects (a preview of assignment Q8).

**Wrap-Up** (5-10 minutes)
- Check for understanding: "What does the `this` keyword refer to inside an object method?"
- Preview next week: algorithms and callbacks — learning to break problems into steps and pass functions as arguments.
- Remind students about the Git commit/push workflow.

### Apply Session

**Warm-Up** (5-10 minutes)
- Ask: "How did the Git commit and push go? Did anyone run into issues?"
- Quick question: "How do you access the value of a property called 'name' on an object called 'myPet'?"

**I Do** (~15 minutes)
- Pull up the assignment and walk through Q1-Q2 (creating and modifying the myPet object).
- Demo the `for...in` loop for Q3, showing how the loop variable holds the property name (key), not the value.
- Walk through the Git steps: `git checkout -b lesson-3`, making changes, `git add .`, `git commit -m "message"`, `git push origin lesson-3`.

**We Do** (15-20 minutes)
- Work through Q4 (adding a `describe` method) together. Ask: "How do we access the object's own properties from inside a method?" Introduce `this` if students haven't seen it.
- Work through Q7 (constructor function) together, as this is a new concept.

**You Do** (15-20 minutes)
- Give students time to work on remaining questions, especially Q8 (comparing objects) which requires combining loops and conditionals.
- For students who finish early: challenge them to add a method to the `Dog` constructor that returns a description.

**Wrap-Up** (5-10 minutes)
- Ask: "What surprised you about how objects work?"
- Remind students to push their work and prepare for next week.
- Point ahead: algorithms and pseudocode — learning to plan before coding.

## 1:1 Session Guide

- **Build rapport**: By week 3, you should have a sense of the student's pace. Check in: "How are you feeling about the workload?"
- **Check understanding**: Ask the student to explain the difference between an array and an object. Can they articulate when to use each?
- **Encourage independence**: If a student is confused about `this`, ask them to explain what they think it refers to, then help them test their theory with a console.log.
- **Goal-setting**: Help the student identify whether Git or objects is the bigger challenge, and focus accordingly.
- **Common sticking points this week**:
  - Understanding `for...in` — the loop variable is the key, not the value
  - The `this` keyword — students may try to use the object name directly instead
  - Constructor functions — the `new` keyword and how it creates instances
  - Git: understanding the difference between local and remote, and the commit/push sequence
  - Deleting properties with `delete` keyword
