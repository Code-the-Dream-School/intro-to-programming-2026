---
marp: true
theme: default
paginate: true
header: "Code the Dream — Intro to Programming"
footer: "Lesson 10: Open API"
---

# Lesson 10: Open API

**Mentor Session Slide Deck**

Topics: Open APIs, Reading Documentation, API Keys, Planning Your Project

---

# This Week is Different

Previous weeks: "Here's what to learn and exactly what to build."

**This week**: "Here are some APIs — pick one and build something creative."

You're choosing your own API, designing your own page, and making **two distinct API calls**. This is the most independence you've had in the course — and it's great practice for real-world development.

---

# What is an Open API?

An **open (or public) API** provides free access to data:

| API | Data You Get |
|-----|-------------|
| Open-Meteo | Weather forecasts, temperature, conditions |
| Swapi.Tech | Star Wars characters, planets, films |
| TheDogAPI | Dog breeds, images, facts |
| TheCatAPI | Cat breeds, images, facts |
| ARTIC | Artwork from the Art Institute of Chicago |
| Marvel | Characters, comics, series info |

Each has its own **documentation** that tells you how to request data.

---

# Reading API Documentation

Every API doc tells you:

1. **Base URL**: The starting point for all requests
   - Example: `https://api.open-meteo.com/v1/forecast`

2. **Endpoints**: Specific paths for different data
   - Example: `/breeds` for dog breeds, `/images/search` for random images

3. **Parameters**: Options you add to customize your request
   - Example: `?latitude=35.99&longitude=-78.90&current_weather=true`

4. **Response format**: What the data looks like (usually JSON)

---

# What is an API Key?

Some APIs require a **key** to identify who's making requests:

```javascript
const API_KEY = "your-unique-key-here";
const url = `https://api.thedogapi.com/v1/breeds?api_key=${API_KEY}`;
```

**How to get one**: Sign up on the API's website → they give you a key.

**Where to put it**: Depends on the API — sometimes in the URL, sometimes in a header. Check the docs!

For this class, it's fine to store the key in a constant in your JS file.

---

# Planning Your Two API Calls

The assignment requires **two distinct calls** that display different data.

**Example with a weather API**:
1. Call 1: Current temperature and weather condition
2. Call 2: 7-day forecast

**Example with TheDogAPI**:
1. Call 1: Random dog image
2. Call 2: List of dog breeds with details

**Before you code**: Plan what data you want and find the right endpoints in the docs.

---

# Setting Up Your Second Page

Your Open API project lives alongside your portfolio:

```
my-project/
├── index.html          ← Portfolio
├── openapi.html        ← Open API page (new!)
├── css/
│   ├── index.css
│   └── openapi.css     ← (new!)
├── js/
│   ├── index.js
│   └── openapi.js      ← (new!)
```

**Link them together** with navigation:
```html
<!-- In index.html nav -->
<a href="openapi.html">Open API</a>

<!-- In openapi.html nav -->
<a href="index.html">Portfolio</a>
```

---

# A Fetch Example with a Real API

```javascript
async function getRandomDog() {
    try {
        let response = await fetch("https://dog.ceo/api/breeds/image/random");
        let data = await response.json();

        let img = document.createElement("img");
        img.src = data.message;
        img.alt = "A random dog";
        img.style.maxWidth = "400px";

        document.querySelector("#dog-container").appendChild(img);
    } catch (error) {
        console.error("Could not fetch dog:", error);
    }
}

getRandomDog();
```

Notice: the image URL is inside `data.message` — you find this by reading the docs or logging the response!

---

# Debugging API Calls

When your fetch isn't working:

1. **`console.log` the response**: What did you actually get back?
   ```javascript
   let data = await response.json();
   console.log(data);  // See the full response structure
   ```

2. **Check the URL**: Copy it into your browser's address bar — does it return JSON?

3. **Check the console for errors**: Network errors, CORS issues, or JSON parsing failures

4. **Check the API docs**: Are you using the right endpoint? Missing a required parameter?

---

# Discussion: Plan Your Project

**Take 5 minutes to answer these questions**:

1. Which API are you using? Why?
2. What are your two distinct API calls?
3. What data will each call return?
4. How will you display the data on the page?
5. What will your page look like? (Sketch a quick wireframe)

**Share with a partner**: Give each other feedback on the plan. Is it clear? Is it achievable this week?

---

# Key Takeaways

- **Open APIs** provide free data you can use in your projects
- **Read the docs** to find the base URL, endpoints, parameters, and response format
- Some APIs need an **API key** — get one from the provider's website
- Your project needs **two distinct fetch calls** displaying different data
- **Link your pages** with navigation so users can go back and forth
- **Plan before you code**: know what data you want and where to find it

**Next week**: Final Project — polish both pages and present your work!
