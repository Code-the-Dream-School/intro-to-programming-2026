---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 8: Asynchronous Programming and Promises"
---

# Lesson 8: Async Programming & Promises

**Mentor Session Slide Deck**

Topics: Synchronous vs. Asynchronous, Why Async Matters, Promises

---

# Two Ways Code Can Run

**Synchronous** — one thing at a time, in order:

```
Start Task A → Finish Task A → Start Task B → Finish Task B
```

**Asynchronous** — start a task, keep going, come back to it later:

```
Start Task A → Start Task B → Finish Task A → Finish Task B
```

JavaScript on the web uses **both** — and knowing when is key.

---

# Real-World Analogies

**Synchronous** (blocking):
- A **phone call**: you stop what you're doing and talk until it's done
- A **drive-through**: you wait in line until it's your turn

**Asynchronous** (non-blocking):
- A **text message**: send it, do other things, respond when the reply comes
- **Ordering delivery**: place the order, go about your day, eat when it arrives

**Discussion**: Can you think of other examples of each?

---

# Why Does This Matter for the Web?

Imagine loading a webpage that needs to:
1. Show the page layout ✅ (fast — it's local)
2. Fetch the user's profile photo from a server 📸 (slow — network request)
3. Load the latest news from an API 📰 (slow — network request)

**Synchronous approach**: page freezes while waiting for #2 and #3 🥶

**Asynchronous approach**: page loads immediately, images and data fill in as they arrive ✅

---

# The Problem with Callbacks

Remember callbacks from Lesson 4? They work, but can get messy:

```javascript
// "Callback hell" — nested callbacks are hard to read
getData(function(data) {
    processData(data, function(result) {
        saveData(result, function(response) {
            displayMessage(response, function() {
                console.log("Done!");
            });
        });
    });
});
```

Each step depends on the previous one, creating a **pyramid of doom**. 😱

---

# Promises: A Better Way

A **Promise** is JavaScript's way of saying:

> "I don't have the result yet, but I **promise** I'll give it to you when I do — or tell you if something went wrong."

Three states:
| State | Meaning | Analogy |
|-------|---------|---------|
| **Pending** | Still working on it | Package is shipped |
| **Fulfilled** | Success! Here's the result | Package delivered ✅ |
| **Rejected** | Something went wrong | Package lost ❌ |

---

# How Promises Look

```javascript
// Instead of nested callbacks:
getData()
    .then(function(data) {
        return processData(data);
    })
    .then(function(result) {
        return saveData(result);
    })
    .then(function(response) {
        displayMessage(response);
    })
    .catch(function(error) {
        console.error("Something went wrong:", error);
    });
```

**Flat and readable** — each `.then()` runs after the previous step completes.

---

# Anatomy of `.then()` and `.catch()`

```javascript
someAsyncOperation()
    .then(function(result) {
        // Runs if the promise is FULFILLED (success)
        console.log("Success:", result);
    })
    .catch(function(error) {
        // Runs if the promise is REJECTED (failure)
        console.log("Error:", error);
    });
```

- `.then()` = "When this succeeds, do this next"
- `.catch()` = "If anything in the chain fails, handle it here"

**Think of it as**: Try → Then → Then → Catch

---

# A Real-World Promise Chain

Ordering food delivery (as a promise chain):

```javascript
placeOrder("pizza")
    .then(function(confirmation) {
        console.log("Order confirmed:", confirmation);
        return waitForDelivery(confirmation);
    })
    .then(function(delivery) {
        console.log("Food arrived:", delivery);
        return enjoy(delivery);
    })
    .catch(function(problem) {
        console.log("Something went wrong:", problem);
        return orderFromSomewhereElse();
    });
```

Each step waits for the previous one to finish before running.

---

# Preview: `async/await`

Next week you'll learn a **cleaner syntax** for promises:

```javascript
async function getFood() {
    try {
        let confirmation = await placeOrder("pizza");
        let delivery = await waitForDelivery(confirmation);
        enjoy(delivery);
    } catch (problem) {
        console.log("Something went wrong:", problem);
    }
}
```

This does the **exact same thing** as the `.then()` chain — it just reads more like synchronous code. More on this next week!

---

# Discussion Activity

**Scenario**: You're building a weather app. When the user opens it, you need to:

1. Get the user's location
2. Fetch the weather data for that location
3. Display the weather on the screen

**Discuss in groups**:
- Which of these steps depends on a previous step?
- Which step might fail? What would you want to happen if it does?
- Is this synchronous or asynchronous? Why?

---

# Key Takeaways

- **Synchronous** code runs one step at a time — simple, but blocks everything
- **Asynchronous** code starts tasks and continues without waiting — essential for the web
- **Promises** represent a future value: pending → fulfilled or rejected
- **`.then()`** chains handle success; **`.catch()`** handles errors
- Promises solve "callback hell" by keeping code **flat and readable**

**Next week**: The Fetch API — you'll use promises to get real data from APIs!
