# Lesson 10 - Open API

This week, you'll explore a public API of your choice and build a new page using what you've learned.

## 10.1 Open Source
"Open Source" means that the source code of something is freely available and can be redistributed and modified. Some APIs are free to access without signing up or paying — often called 'open' or 'public' APIs. This is different from open source, which means the code itself is publicly available. This week, you'll use one of these free APIs to practice what you've learned. We have identified several options of open source APIs, which are services that allow you to use their data without paying for access.  

Use one of the following open source APIs to create a page that makes two distinct calls to the API and displays the returned data. 

*For Example:* if using Open-Meteo, the weather API, you could display (1) the temperature and (2) the weather condition.  Take a look at the options below and decide which one(s) interest you the most.

### Open Source API options:

You may use any of these. The dog and cat APIs include clear fetch examples in their documentation.
 
* [Open-Meteo](https://open-meteo.com/) – a weather API
* [Swapi.Tech](https://www.swapi.tech/) – an API about Star Wars films
* [Marvel](https://developer.marvel.com/) – an API about the Marvel fandom
* [ARTIC](https://api.artic.edu/docs/#introduction) – an art API from the Art Institute of Chicago
* [TheDogAPI](https://thedogapi.com/) or the [TheCatAPI](https://thecatapi.com/) – APIs about (you guessed it!) Dogs or Cats
* [Soccer](https://api-sports.io/documentation/football/v3) - a sports data API

## 10.2 API Keys and Security

Some APIs require an **API Key**. An API Key is a unique identifier, similar to a password, that authenticates your application to an API. The service provider generates it and uses it to track usage and enforce limits. API keys are separate from user authentication. The service provider generates your API key and uses it to track access and usage. 

**Watch this short video on API Keys:**

[API Key Video](https://www.youtube.com/watch?v=xoriGNUNF7E)

This video mentions that you should keep API Keys private and protected.  In this case, it is fine to create a constant to hold the key.

### AI Learning Prompt: Predict-then-Check
Study this logic based on how API keys work: If you make a fetch request to a service that requires an API key, but you forget to include the key in your URL or header:
1. Predict what the server will send back as a response.
2. Explain to an AI chatbot why you think the server will react that way.
3. Ask: "Is my understanding of API authentication correct?".
4. Try to make a call to an API (like Marvel or Open-Meteo) without your key and see if your prediction was right.

## 10.3 Final Project Open API Requirements

For your Open API page, you will code an additional html, css and javascript file.  These can reside in the same directories as your current files. To link this page to your portfolio, add a link to the HTML file in your nav bar:

``` html
<nav>
  <ul> 
    <li><a href="openapi.html">About</a></li> 
  </ul> 
</nav> 
```

You will also  create another nav bar on your open api page.  Make sure there is an option to get back to your home page from there!

### Below is the rubric for the Open API portion of your final project:

[Open API Rubric](https://github.com/Code-the-Dream-School/intro-to-programming-2026/wiki/Open-API-Rubric)

### AI Learning Prompt: Scaffold Removal
As you experiment with different APIs, you may run into issues with data structures or connecting your new files. Use these prompts to help you troubleshoot while keeping responsibility for the code.

**Example Prompt for an Error:**
> "I'm trying to display the data I fetched from the Star Wars API, but the screen says '[object Object]' instead of the character names. Here is my code: [paste code]. Can you ask me 3 questions that will help me figure out how to access the specific properties inside the returned object?".

**Example Prompt for a Hint:**
> "I'm stuck on how to create a navigation bar on my new page that leads back to my home page. Can you give me 3 high-level hints for how to structure the file paths in my <a> tags without giving me the final answer?".

## 😄 Great work on Lesson 10!
As you move on to the weekly coding assignment, make sure to re-check the final project rubric.
