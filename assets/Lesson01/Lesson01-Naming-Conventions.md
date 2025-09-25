
Naming and style conventions are a set of widely accepted guidelines for naming variables, functions, classes and other identifiers. They are used to improve code readability and maintainability.

https://www.w3schools.com/js/js_conventions.asp

It is also important to consider the readability of your code when you are naming variables and functions. Avoid abbreviations unless they are commonly known. **i** and **j** are widely used as loop counters and array indices.

Well-named variables help both the original developer and others understand what the code is doing without needing to decipher vague or cryptic labels. For example, a variable named totalPrice is far more informative than one named tp, instantly conveying its purpose. Descriptive names reduce confusion, make debugging easier, and allow for more efficient collaboration among a team of developers.

### Naming Conventions
- Use **camelCase** for variables and functions such as `firstName` and `messageString()`. 
- Use **PascalCase** for class names like `ShoppingCart`. 
- Use the **UPPER_SNAKE_CASE** for constants like `MAX_USERS`
- Avoid using single-letter names except for loop counters like `i`, `j`, or `k`.
- All names should start with letters.

### Function Names
Function names should describe the functionality of the function, hence should be verbs. For example, `calculateSum()` means the function calculates the sum and `sendEmail()` sends email. Also, functions that return either true or false, can start with '**is**', '**has**', or '**can**', for example, `isValid()` or `hasPermission()`.

### Code Readability
- Use `let` and `const` instead of `var`
- Keep consistent indentation and spacing. Many editors have code formatters which will help keep your code consistent. 
- Use template literals for combining strings rather than the `+` operator. 
- Avoid magic numbers by giving meaningful names to constants. 
- Comment your code to explain why something is done rather than what it does.
