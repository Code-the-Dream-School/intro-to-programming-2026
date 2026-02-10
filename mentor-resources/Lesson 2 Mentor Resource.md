# Lesson 2 Mentor Resource: JavaScript Loops and Arrays

## Lesson Overview
This week students learn about loops (`for`, `while`) and arrays. They also learn about scope and begin working with Git by installing it, setting it up, and cloning their GitHub repository to their local machine. The assignment focuses on writing functions that use loops to iterate, and working with arrays — creating them, accessing elements, comparing them, and transforming them. The classic "FizzBuzz" problem appears as Q14.

This lesson builds directly on Lesson 1's variables, conditionals, and functions. Loops and arrays together unlock the ability to process collections of data, which is a pattern students will use for the rest of the course.

---

## Group Mentor Sessions

### Explore Session

**Warm-Up** (5-10 minutes)
- Ask a review question: "Can someone explain what a function is and why we use them?" or "What's the difference between `let` and `const`?"
- Or pose a scenario: "Imagine you need to print 'Hello' 1,000 times. How would you do it without copying and pasting?"

**I Do** (~15 minutes)
- Demo a `for` loop in a code editor: show the three parts (initialization, condition, increment) and walk through what happens on each iteration.
- Show how to create an array and access elements by index. Emphasize that arrays are zero-indexed.
- Briefly demonstrate a useful array method like `.push()` or `.length`.

**We Do** (15-20 minutes)
- Present a problem: "Given an array of numbers, how would we find the sum?" Work through it together, asking students to suggest each step.
- Discussion: "What happens if our loop condition is always true? What if we forget to increment?" Let students predict, then demonstrate an infinite loop (and how to stop it).
- If using breakout rooms: give each group a small challenge, like "Write pseudocode for a function that counts the vowels in a string." Rotate to check in and ask "What does your loop need to track?"

**You Do** (15-20 minutes)
- Have students write a function that takes an array and returns only the even numbers (similar to assignment Q11). They can share their approach.
- Or have students attempt FizzBuzz in pseudocode first, then translate to code.

**Wrap-Up** (5-10 minutes)
- Ask: "What's one thing about loops or arrays that clicked for you today?"
- Preview next week: JavaScript objects — a way to group related data together using key-value pairs.
- Remind students about the Git setup: cloning their repo is part of this week's work.

---

### Apply Session

**Warm-Up** (5-10 minutes)
- Ask: "Has anyone tried cloning their GitHub repository yet? How did it go?"
- Quick review: "What are the three parts of a `for` loop?"

**I Do** (~15 minutes)
- Pull up the assignment and walk through Q1 (`repeat` function) to show the loop pattern: set up the loop, do something inside, and make sure it stops.
- Demo Q6 (arrayChecker) to show how to check if an array is empty using `.length`.
- Show the terminal commands for cloning a repository if students need a refresher.

**We Do** (15-20 minutes)
- Work through Q9 (compareArrays) together. This is a more complex function that trips up many students. Walk through the logic step by step: check lengths first, then loop through and compare each element.
- Ask students to predict: "What should this function return if we pass two empty arrays?"

**You Do** (15-20 minutes)
- Give students time to work on the assignment, especially the harder questions (Q9, Q14 FizzBuzz, Q15 scope).
- For students who finish early: challenge them to explain the scope question (Q15) to a partner.

**Wrap-Up** (5-10 minutes)
- Ask: "What was the trickiest part of this week's assignment?"
- Remind students about the Git cloning task and point them to the video resource if they haven't done it yet.
- Point ahead: next week they'll learn about objects, which combine multiple pieces of data into one structure.

---

## 1:1 Session Guide

- **Build rapport**: Check in on how the student is feeling about the course so far. Is the pacing comfortable? Are they finding the resources helpful?
- **Check understanding**: Ask the student to walk you through one of their loop-based functions. Can they explain what happens on each iteration?
- **Encourage independence**: If a student's loop isn't working, ask "What value does your loop variable have at the start? What about after the first iteration?" Help them trace through the logic.
- **Goal-setting**: If a student is struggling, help them prioritize which assignment questions to focus on. The core skills are in Q1-Q6 and Q10.
- **Common sticking points this week**:
  - Off-by-one errors in loops (starting at 0 vs 1, using `<` vs `<=`)
  - Confusing array index with array value
  - FizzBuzz: checking "divisible by both" before checking individually
  - Scope: understanding why a variable declared inside a function isn't accessible outside
  - Git setup: SSH key configuration can be tricky — direct students to the Odin Project guide
