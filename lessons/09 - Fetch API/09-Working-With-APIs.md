# Working with APIs: A Beginner's Guide

## What is an API?

An **API** (Application Programming Interface) is a way for one program to ask another program for data or to perform an action.

Think of a restaurant. You (your program) don't walk into the kitchen. You give your order to a waiter (the API), who carries it to the kitchen (the server) and brings back your food (the response). The menu tells you what you're allowed to ask for. An API's documentation is that menu.

When you check the weather on your phone, the app is almost certainly asking a weather API for the data.

## Key Terms

| Term | Meaning | Example |
| --- | --- | --- |
| **Endpoint** | The specific web address (URL) you send a request to | `https://api.example.com/v1/users` |
| **Request** | The message you send to the API | "Give me the weather for London" |
| **Response** | What the API sends back, usually as JSON | `{"city": "London", "temp": 14}` |
| **JSON** | A text format for structured data: labels paired with values | `{"name": "Ana", "age": 34}` |
| **Header** | Extra information sent with a request, such as who you are or what format you want | `Accept: application/json` |
| **Query parameter** | An option added to the end of a URL after a `?` | `...?unitGroup=metric` |
| **API key** | A unique code that identifies you to the service | Like a library card number |

### Request methods: what do you want to do?

| Method | Purpose |
| --- | --- |
| **GET** | Retrieve data (looking something up) |
| **POST** | Create something new |
| **PUT** | Replace an existing item entirely |
| **PATCH** | Change part of an existing item |
| **DELETE** | Remove an item |

When you're starting out, you will use **GET** most of the time.

### Status codes: how did it go?

Every response includes a three-digit number telling you the result.

| Range | Meaning | Common examples |
| --- | --- | --- |
| **2xx** | Success | `200 OK` |
| **3xx** | Redirect (go to another address) | `301 Moved Permanently` |
| **4xx** | Your request had a problem | `400 Bad Request`, `401 Unauthorized` (missing or bad key), `403 Forbidden` (not allowed), `404 Not Found`, `429 Too Many Requests` |
| **5xx** | The server had a problem | `500 Internal Server Error` |

A useful rule: **4xx means check your request; 5xx means it's probably not your fault.**

### Authentication: proving who you are

Many APIs require a key so the provider can control access and limit how much each person uses. (Some public APIs need no key at all.) Keys are sent in one of two ways, and the documentation tells you which:

- **In a header**, which is the more secure and common approach for professional APIs.
- **In the URL as a query parameter**, which is simpler but riskier, since URLs can end up in browser history and server logs.

Some APIs use **OAuth** instead, a system that lets one service act on your behalf without sharing your password (like "Log in with Google"). You won't need it for this guide.

**Treat your API key like a password.** Don't share it, post it online, or paste it into code you might publish.

## The 5-Step Workflow

The process is the same whatever programming language you use.

| Step | What to do | Tips |
| --- | --- | --- |
| **1. Read the docs** | Find the API's documentation. Look up the endpoints, required parameters, and usage limits. | Search for "\[service name\] API documentation" or look for a developer portal. |
| **2. Get credentials** | Create a free account and generate an API key. | Store the key in an environment variable, not directly in your code. |
| **3. Test manually** | Send one request by hand before writing any code. | You can use a browser. |
| **4. Parse the response** | Turn the JSON text into data your program can use, and pick out the fields you need. | Most languages have a built-in JSON tool. |
| **5. Handle errors** | Plan for failures: bad connections, missing data, rate limits. | Always check the status code before using the data. |

## Example: Weather Data

### Step 1 - Read the Docs
We'll use the free [Visual Crossing Timeline Weather API](https://www.visualcrossing.com/resources/documentation/weather-api/timeline-weather-api/). 

### Step 2 - Get Credentials

Create a free Visual Crossing account. Your key appears on your account page. It is a long string of letters and numbers unique to you, which lets the service track how much data you request.

### Step 3a - Test manually. First, try it without a key.

Paste this into your browser:

```
https://weather.visualcrossing.com/VisualCrossingWebServices/rest/services/timeline/london
```

You'll see an error like this:

```
No session or key found.
```

That's the API saying, "I don't know who you are." This is a `401`-type error: a problem with the request, not the server.

### Step 3b: Test manually. Now, try it with a key.

Visual Crossing takes the key as a query parameter. Add `?key=` followed by your key, and replace `YOUR_API_KEY` below with your own:

```
https://weather.visualcrossing.com/VisualCrossingWebServices/rest/services/timeline/london?key=YOUR_API_KEY
```

Here is a shortened version of what comes back (the actual response is much longer):
```json
{ "queryCost":1,
  "latitude":51.5072,
  "longitude":-0.1275,
  "resolvedAddress":"london",
  "address":"london",
  "timezone":"Europe/London",
  "tzoffset":1.0,
  "description":"Cooling down with no rain expected.",
  "days":[
    {"datetime":"2026-10-02",
    "datetimeEpoch":1790895600,
    "tempmax":70.1,
    "tempmin":52.0,
    "temp":60.7,
    }
  ]
}
```

Notice the structure. The curly braces `{}` hold labeled values, and the square brackets `[]` hold a list. The `days` list contains one entry per day, and each day has its own labeled values.

### Steps 4 and 5: Parse the Response and Handle Errors

We will cover this later in the lesson!
