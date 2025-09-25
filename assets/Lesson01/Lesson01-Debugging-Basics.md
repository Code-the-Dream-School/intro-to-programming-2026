Software debugging is the process of finding and fixing errors (bugs) in computer programs. It is a crucial (and large) part of software development. Proper debugging ensures programs function as intended and are reliable.

The most basic method of debugging is to log data directly from your program. You will use these logs to see what the code you have written is actually doing.

In programming, a console is a text-based interface used for interacting with a computer program or operating system. It allows users to input commands and receive output, often in the form of text, directly from the program. This interface is also commonly used for debugging and troubleshooting code.

Console windows are also knows as terminal windows. You will also sometimes hear the term command-line interface (CLI) which means you are typing commands to interact with the program or system.

We will talk a little more about console windows in future lessons, but for now, all you need to know is that when you run the command:

```javascript
console.log("string to log")
```
The data located between the parenthesis is logged to the console window which is part of the embedded/interactive assignment on the javascript lesson pages.

The AI Assignment Reviewer IS NOT a substitute for debugging your program. The reviewer will give you valuable information on things that might be wrong in your code, but is not the same as actually debugging your code.

## Basic techniques to find and fix errors in JavaScript code.

Debugging is extremely important because it helps **catch errors early**, improves code reliability, and helps in understanding code flow. 

When writing code, it is possible for code to be prone to many errors:  
- **Syntax errors** occur when you have typos in code or miss brackets.  
- **Reference errors** occur when you refer to undefined variables.  
- **Type errors** occur when you use incorrect operations on values.  
- **Logical errors** happen when code runs but produces the wrong results.

In order to successfully debug, there are many tools we can utilize:  
- **console.log()** can be used for checking variable values and program flow.  
- **console.error()** allows us to see the error messages.  
- **debugger;** allows us to pause code execution and inspect variables.

We should also follow tips and best practices for debugging:  
- Test code incrementally because managing small chunks is easier than debugging the entire code at once.  
- Use descriptive variable names for easier debugging.  
- Comment out parts of code to isolate problems.  
- Read error messages carefully and try to understand what they indicate.

### Examples

**Example 1: Checking variable values**
```javascript
let firstName = "Rubaina";
let lastName = "Roshan";
let fullName = firstName + lastName; // Forgot the space

// Debugging output
console.log("Full Name:", fullName); // Output will show the missing space
```
