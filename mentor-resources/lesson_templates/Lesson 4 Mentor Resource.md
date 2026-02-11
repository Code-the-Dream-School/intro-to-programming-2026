# Lesson 4 Mentor Resource: JavaScript Algorithms

## Lesson Overview
This week students learn about algorithms (step-by-step problem-solving), pseudocode, and callbacks. On the Git side, students learn about pull requests — creating, submitting, merging, and pulling updates back to their local repo. This completes the full Git workflow. The assignment covers practical algorithm functions (temperature conversion, string reversal, tip calculator, prime number checking, grade calculation) and introduces callbacks through a simulated button push.

This is a pivotal week. Students are combining everything they've learned (variables, conditionals, loops, arrays, objects, functions) to solve more complex, multi-step problems. The pseudocode approach is especially important to reinforce here.

---

## Group Mentor Sessions

### Explore Session

**Warm-Up** (5-10 minutes)
- Pose a real-world scenario: "How would you explain to someone who has never cooked how to make a peanut butter and jelly sandwich? Write out the steps." This connects directly to the lesson content on algorithms.
- Or ask: "What's the hardest problem you've had to solve in this course so far? How did you approach it?"

**I Do** (~15 minutes)
- Explain what an algorithm is using everyday examples (the lesson provides several: making a sandwich, following a recipe, using GPS).
- Demo the pseudocode approach: take a problem like the tip calculator and write out the steps in plain English as comments before writing any code.
- Briefly introduce callbacks: "A callback is just a function you pass to another function to be called later." Show a simple example.

**We Do** (15-20 minutes)
- Give students a problem (e.g., "Write an algorithm to determine if a word is a palindrome") and work through the pseudocode together before writing any code.
- Discussion: "Why is it helpful to write pseudocode before jumping into code? Has anyone tried this approach?"
- If using breakout rooms: have each group write pseudocode for the `reverseString` or `isPrime` function. Rotate and ask "What's the first step? How do you know when you're done?"

**You Do** (15-20 minutes)
- Have students pick one of the assignment problems they haven't started and write pseudocode for it first, then translate to code.
- Or have students explain the callback concept back: "Can someone give me an example of when you'd want to pass a function to another function?"

**Wrap-Up** (5-10 minutes)
- Ask: "What is one problem-solving strategy you learned this week that you want to keep using?"
- Preview next week: HTML — they'll start building actual web pages.
- Remind students about the pull request process: this is how their assignments get reviewed.

---

### Apply Session

**Warm-Up** (5-10 minutes)
- Ask: "How did creating your first pull request go? Any questions about the process?"
- Quick question: "What's pseudocode, and why might it be useful?"

**I Do** (~15 minutes)
- Pull up the assignment and demonstrate the pseudocode-to-code approach on Q1 (convertTemp) or Q3 (tipCalculator).
- Walk through the pull request and merge workflow, showing how to merge on GitHub and pull back to the local machine.

**We Do** (15-20 minutes)
- Work through Q6-Q7 (isPrime and getPrimesUpTo) together. These are the most complex algorithmic problems. Walk through the logic: "How do we check if a number is prime? What numbers do we need to test?"
- Work through Q8-Q11 (the grade calculator chain) to show how functions can call other functions.

**You Do** (15-20 minutes)
- Give students time to work on remaining assignment questions, especially Q12-Q13 (callbacks).
- For students who finish early: challenge them to explain how Q13 (simulateButtonPush) demonstrates the callback pattern.

**Wrap-Up** (5-10 minutes)
- Ask: "Which assignment question taught you the most?"
- Remind students to create and submit their pull request.
- Point ahead: HTML Basics — they'll transition from pure JavaScript to building web pages.

---

## 1:1 Session Guide

- **Build rapport**: This is week 4 and the content is getting more challenging. Check in on the student's confidence and motivation.
- **Check understanding**: Ask the student to pick one of their functions and walk you through the algorithm step by step. Can they explain their logic without looking at the code?
- **Encourage independence**: If a student is stuck on an algorithm, don't give them the code. Ask: "What's the first thing your function needs to do? Then what? How do you know when to stop?" Guide them to write pseudocode first.
- **Goal-setting**: If the student is finding the algorithms challenging, help them focus on Q1-Q5 first (the more straightforward functions) before tackling Q6-Q11.
- **Common sticking points this week**:
  - The `isPrime` function: students may forget to handle 0 and 1, or may not know the square root optimization
  - The grade calculator chain (Q8-Q11): understanding how to call one function from another
  - Callbacks: understanding that you pass the function itself (without parentheses), not the result of calling it
  - Pull requests: understanding the merge and pull-back workflow
  - Forgetting to `return` values from functions (console.log is not the same as return)
