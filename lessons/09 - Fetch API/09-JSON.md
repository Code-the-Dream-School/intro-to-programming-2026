# JSON

JSON (JavaScript Object Notation) is a plain-text format for representing structured data. It is the most common way for web servers and browsers to exchange data. Despite the name, it isn't limited to JavaScript. Nearly every programming language can read and write it.

The key idea is that JSON is text. A server can't send a JavaScript object over the internet, but it can send a string that describes one, and JSON is the agreed format for that description.

**Example:**

```json
{
  "name": "Ada",
  "age": 36,
  "isStudent": false,
  "skills": ["math", "programming"],
  "address": {
    "city": "London",
    "zip": null
  }
}
```

## JSON Rules

JSON has a small set of strict rules:

- Data is built from key-value pairs inside curly braces `{ }` (an object) or ordered lists inside square brackets `[ ]` (an array).
- Keys must be strings in double quotes. `{"name": "Ada"}` is valid, but `{name: "Ada"}` is not.
- Strings must use double quotes. Single quotes are invalid.
- No trailing commas. `[1, 2, 3,]` is invalid.
- No comments, and no functions. JSON describes data only.

### The six value types, with an example of each

- **String**: `"hello"`
- **Number**: `42`, `3.14`, `-7`
- **Boolean**: `true`, `false`
- **Null**: `null`
- **Object**: `{"key": "value"}`
- **Array**: `[1, "two", false]`

Objects and arrays can nest inside each other to any depth, which is how JSON represents complex data like a list of users, each with an address and a list of orders.

Anything outside these six types, such as `undefined`, functions, dates, or `NaN`, can't be represented directly. Dates, for example, are usually stored as strings like `"2026-10-01T12:00:00Z"`.

## JSON versus a JavaScript object

They look similar, which is a common source of confusion, but they are different things.

A JavaScript object is a live value in memory:

```javascript
const user = { name: 'Ada', age: 36 };
```

JSON is a string of text that describes data:

```javascript
const json = '{"name":"Ada","age":36}';
```

You can access `user.name`, but you can't do `json.name`, because `json` is just a string.

## Built-in JavaScript methods for JSON

To move between the two, JavaScript provides two built-in methods:

- **`JSON.stringify()`** turns a JavaScript value into a JSON string. You use it when sending data.

```javascript
const user = { name: 'Ada', age: 36 };
const json = JSON.stringify(user);
console.log(json); // '{"name":"Ada","age":36}'
```

- **`JSON.parse()`** turns a JSON string back into a JavaScript value. You use it when receiving data.

```javascript
const json = '{"name":"Ada","age":36}';
const user = JSON.parse(json);
console.log(user.name); // 'Ada'
```

If the string isn't valid JSON, such as one with single quotes or a trailing comma, `JSON.parse()` throws an error, so it's worth wrapping it in `try...catch` when the source is unreliable.

```javascript
try {
  const user = JSON.parse("{'name': 'Ada'}"); // single quotes are invalid
} catch (error) {
  console.error('Invalid JSON:', error.message);
}
```

## Reading nested data

The weather response from the previous topic is a good example of nested data. An object holds an array (`days`), and the array holds more objects. You reach into it with dots for objects and square brackets with an index for arrays:

```javascript
const weather = JSON.parse(`{
  "resolvedAddress": "london",
  "days": [
    { "datetime": "2026-10-02", "temp": 60.7 }
  ]
}`);

console.log(weather.resolvedAddress); // 'london'
console.log(weather.days[0].temp);    // 60.7
```

Read `weather.days[0].temp` from left to right: the `weather` object, its `days` array, the first item in that array, and that item's `temp` value.

## How JSON connects to fetch

When you call `response.json()`, fetch is doing the equivalent of `JSON.parse` for you. It reads the response body (JSON text) and gives you a JavaScript object. When you send data, you do the reverse yourself:

```javascript
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ title: 'Hello', userId: 1 })
});
```

`JSON.stringify` converts your object to text for the body, and the `Content-Type: application/json` header tells the server how to interpret it.

## Common mistakes

- **Forgetting to parse.** A string of JSON is not an object. If `data.name` is `undefined`, check whether you still have a string.
- **Parsing twice.** `response.json()` already parses the body, so calling `JSON.parse` on its result throws an error.
- **Invalid syntax.** Single quotes, unquoted keys, and trailing commas are the usual culprits. A tool like [jsonlint.com](https://jsonlint.com) or your editor's formatter will point out the problem.
- **Expecting everything to survive a round trip.** `JSON.stringify` drops `undefined` and function values, turns `Date` objects into strings, and can't handle circular references.

## AI Learning Prompt: Retrieval Practice

1. Without looking back, explain in your own words the difference between a JavaScript object and JSON, and what `JSON.parse()` and `JSON.stringify()` each do.
2. Open your preferred AI chatbot and share your explanation.
3. Ask it to tell you what you got right and where your understanding could be improved.

**Example Prompt:**
> "I just learned about JSON. Here's my understanding: the difference between a JavaScript object and JSON is [your explanation]. I think JSON.parse does [your explanation] and JSON.stringify does [your explanation]. What did I get right, and what should I refine?"
