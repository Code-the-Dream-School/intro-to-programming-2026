//----------------------------------
// LESSON 1 BASICS AND FUNCTIONS
//----------------------------------

// This is the coding assignment for the first week of the Intro to Programming course from Code the Dream. The concepts touched on in this assignment include:
//   - The basic syntax of the JavaScript programming language
//   - Basic programming concepts like variables, data types, and conditional statements
//   - Troubleshooting programming problems
//   - Encapsulating code with Functions
//   - Passing Information Into Functions

// In this assignment you will write your own code. Your instructions are listed as "comments", meaning the instructions are grayed out and start with '//' at the beginning of the line of code. Put your answers immediately below the instructions for each question. There are sample console logs for all questions, but be sure to use some of your own values and function inputs as well.

// Make sure you run your code after EVERY question before moving on.
// For each question you should:
// - Write your code
// - Run your code with debugging statements (console.log) so that you can see the output of those statements in the console
// - Make corrections based on the console output 
// - Once you feel the console output is correct, move onto the next question

// ---------- QUESTION 1 ----------
// Declaring and giving string values to variables.
// Create three variables.  Make sure to use camelCase when you are naming your variable - this means all letters are lowercase except for the first letter of words that are in the middle.  This is the accepted standard for JavaScript code.  
// - First variable should be named "firstName" with the value of your first name as a string.  
// - Second variable should be named "lastName" with the value of your last name as a string.  
// - Third variable should be named "country" with the value of the name of the country where you were born as a string.

// EXAMPLE LOG:
//   console.log ("Q1: My first name is ", firstName);
//   console.log ("Q1: My last name is ", lastName);
//   console.log ("Q1: I was born in ", country);

// EXAMPLE OUTPUT:
//   Q1: My first name is Jane
//   Q1: My last name is Doe
//   Q1: I was born in Canada

// PUT YOUR CODE HERE


// ---------- QUESTION 2 ----------
// Declaring and giving numerical values to variables.

// Create four variables.  
// - One named "floatingPoint" with the value of any floating point number you choose.  
// - One named "integer" with the value of any integer number you choose.  
// - One named "negative" with the value of any negative number you choose.  

// OPTIONAL: You'll see "Optional" tasks throughout the course. These are optional, but are encouraged as they help you try your hand at something a little more advanced for the week/assignment/question. 

// OPTIONAL:
// - Create a fourth variable titled "bigNumber" that is 16 or more numbers long. Write your console.log and see if the value displayed in the console matches exactly what you typed.  

// EXAMPLE LOG:
//   console.log ("Q2: This is a floating point number: ", floatingPoint);
//   console.log ("Q2: This is an integer: ", integer);
//   console.log ("Q2: This is a negative number: ", negative);

// EXAMPLE OUTPUT:
//   Q2: This is a floating point number: 3.14
//   Q2: This is an integer: 5
//   Q2: This is a negative number: -6

// PUT YOUR CODE HERE


// ---------- QUESTION 3 ----------
// Assigning boolean values to variables.
// Create two variables.  You can name them anything you want, but it is important to choose meaningful variable names that describe what they contain.  This is all part of making your code readable and understandable.
// - Define the first variable and assign it a value of true.    
// - Define a second variable and assign it a value of false. 

// EXAMPLE LOG:
//   console.log ("Q3: The variable I made true is: ", myTrueVariable);
//   console.log ("Q3: The variable I made false is: ", myFalseVariable);

// EXAMPLE OUTPUT:
//   Q3: The variable I made true is: true
//   Q3: The variable I made false is: false

// PUT YOUR CODE HERE


// ---------- QUESTION 4 ----------
// String Concatenation
// Create a variable that makes a concatenated string out of the variables you made in QUESTION 1. Be sure you're using your Q1 variables and not making new ones.

// There are often multiple ways to solve a problem.
// - First, use the + operator and create a string named firstHelloString that contains "Hello, my name is firstName lastName and I was born in country."
// - Second, use template literals and create a string named secondHelloString that contains the same string.  
 
// EXAMPLE LOG:
//   console.log ("Q4 first: ", firstHelloString); 
//   console.log ("Q4 second: ", secondHelloString); 

// EXAMPLE OUTPUT:
//   Q4 first: Hello, my name is Jane Doe and I was born in Canada. 
//   Q4 second: Hello, my name is Jane Doe and I was born in Canada. 

// PUT YOUR CODE HERE


// ---------- QUESTION 5 ----------
// JavaScript Math
// Define two variables:
// - One to contain the floating point number minus the integer from Q2.
// - The second to contain the integer plus the negative number from Q2. 

// EXAMPLE LOG:
//   console.log ("Q5 subtract: ", subtractionVariable); 
//   console.log ("Q5 add: ", additionVariable); 

// EXAMPLE OUTPUT:
//   Q5 subtract: 2.87 
//   Q5 add: 5

// PUT YOUR CODE HERE


// ---------- QUESTION 6 ----------
// String Methods
// Define four variables:
// - One named "nameLength" containing the length of your first name 
// - One named "firstInitial" containing the first letter of your first name
// - One named "lastInitial" containing the LAST letter of your first name
// - One named "capitalize" containing your first name in all capital letters
// Use the firstName variable from QUESTION 1.

// OPTIONAL: 
// - Create a variable named "weirdInitials". Using string methods, have weirdInitials result in the value of the LAST letters of any first and last names. Both these letters should also be capitalized in "weirdInitials".  Example: "Sally Smith"'s weird initials should be "YH" and "Jose Rodriguez"'s inititals should be "EZ"

// EXAMPLE LOG:
//   console.log ("Q6 nameLength: ", nameLength); 
//   console.log ("Q6 firstInitial: ", firstInitial); 
//   console.log ("Q6 lastInitial: ", lastInitial); 
//   console.log ("Q6 capitalize: ", capitalize); 

// EXAMPLE OUTPUT:
//   Q6 nameLength: 4 
//   Q6 firstInitial: J 
//   Q6 lastInitial: e 
//   Q6 capitalize: JANE 

// PUT YOUR CODE HERE


// ---------- QUESTION 7 ----------
// Logic Constructs
// - Declare a variable named 'answer'.  
// - Create a conditional if-then-else statement that assigns the value true to 'answer' if the  integer from Q2 is greater than 10 and assigns it false if it is not.

// OPTIONAL: 
// - Define a new variable named 'stretchAnswer'
// - Make an if-then-else if-else statement that assigns 'stretchAnswer' the value of "less than" if the integer from Q2 is less than 10, "equal to" if it's equal, and "greater than" if it's greater.
// What type is each of your variables?  You can find out by logging typeof(variable).

// EXAMPLE LOG:
//   console.log ("Q7 answer: ", answer);
//   console.log ("Q7 answer type: ", typeof(answer));

//   console.log ("Q7 stretchAnswer: ", stretchAnswer);  
//   console.log ("Q7 stretchAnswer type: ", typeof(stretchAnswer));

// EXAMPLE OUTPUT:
//   Q7 answer: true
//   Q7 answer type: boolean
//   Q7 stretchAnswer: greater than
//   Q7 stretchAnswer type: string

// PUT YOUR CODE HERE


// ---------- QUESTION 8 ----------
// More Logic!
// - Declare a variable called "age"
// - Assign it the value of your age in years
// - Create a conditional statement that will log the phrase "Age is just a number!" if your age is less than or equal to 30 and "Young at heart!" if your age is greater than 30.

// OPTIONAL: Combine your skills!  Use template literals to log your name in this phrase: "Sally, age is just a number!" or "Jose, you're young at heart!" replacing these examples (Sally and Jose) with your first name instead.

// EXAMPLE LOG:
//   Your logs will be part of the if-then-else
//   console.log ("Q8: ", "Age is just a number!");
//   console.log ("Q8: ", "Young at heart!");

// EXAMPLE OUTPUT:
//  Only one of these should be logged
//  Q8: Age is just a number!
//  Q8: Young at heart!

// PUT YOUR CODE HERE


// ---------- QUESTION 9 ----------
// - Declare a variable named "exampleNum".  
// - Give it the value of a floating point number with 4 decimal places.  
// - Using a Number method round it to the nearest two decimal place. HINT: Look up the Number method toFixed().
// - Example if the number is 21.4572, exampleNum should become 21.46.

// EXAMPLE LOG:
//   console.log ("Q9 exampleNum before round: ", exampleNum);
//   console.log ("Q9 exampleNum after round: ", exampleNum);

// EXAMPLE OUTPUT:
//   Q9 exampleNum before round: 21.4572
//   Q9 exampleNum after round: 21.46

// PUT YOUR CODE HERE



// ---------- QUESTION 10 ----------
// Functions
// - Create a function titled 'assignMessageString'.  Functions also use camelCase as a naming convention.  Because functions represent actions, their names should usually begin with a verb.  
// - Inside the function, declare a variable named 'message' and assign it the string "Welcome to Code the Dream!".  Return the 'message' variable.

// EXAMPLE LOG:
//    console.log("Q10: ", assignMessageString());
// EXAMPLE OUTPUT:
//    Q10: Welcome to Code the Dream!

//PUT YOUR CODE HERE

// ---------- QUESTION 11 ----------
// Another function
// - Create a function called 'combineStrings'.  
// - Inside the function, declare two variables named 'string1' and 'string2'.  
// - Assign them the strings 'Good' and 'Evening' respectively.  Return the two strings concatenated with a space in between.

// EXAMPLE LOG:
//    console.log("Q11: ", combineStrings());
// EXAMPLE OUTPUT:
//    Q11: Good Evening

//PUT YOUR CODE HERE

// ---------- QUESTION 12 ----------
// Parameters
// - Create a function called 'useParams' that takes one parameter and returns that parameter with all letters capitalized.

// EXAMPLE LOG:
//    console.log("Q12: ", useParams("hello"));
// EXAMPLE OUTPUT:
//    Q12: HELLO

// PUT YOUR CODE HERE

// ---------- QUESTION 13 ----------
// - Create two variables named 'word1' and 'word2' and assign them any strings you want.  
// - Then, create a function called 'biggestStringLength' that takes word1 and word2 as parameters and returns the length of the longer string. 
// - If they are of equal length, just return that length.  

// OPTIONAL:
// - Test your function with an empty string as one of the inputs, and see what happens in that situation.

// EXAMPLE LOG:
//   console.log("Q13: ", biggestStringLength(word1, word2));
// EXAMPLE OUTPUT: (if your word1 was 'Code' and word2 was 'Dream')
//   Q13: 5

// PUT YOUR CODE HERE


// ---------- QUESTION 14 ----------
// Random Number Generator
// - Create a function named "returnRandomNum" which will return a random integer between 1 and 3 inclusive (1, 2 or 3)

//  You'll want to use the following methods:
// - Math.random() which returns a number between 0 and 1 (greater or equal to 0, less than 1)
// - Math.floor() rounds a number down to the nearest whole integer
// - For example: Math.floor(Math.random() * 10) returns a random integer between 0 and 9 (both included)
// - HINT: you'll need to adjust the range above. 'Math.random() * 3' gives a range from 0 up
//   to but not including 3. Math.floor() of that gives a whole number from 0 to 2. Think about
//   what you need to add to shift that range so it becomes 1 to 3 instead of 0 to 2.

// EXAMPLE LOG:
//   Log this several times so you see different numbers being logged
//   console.log ("Q14 random number: ", returnRandomNum());
//   console.log ("Q14 random number: ", returnRandomNum());
//   console.log ("Q14 random number: ", returnRandomNum());


// EXAMPLE OUTPUT:
//   Q14 random number: 1
//   Q14 random number: 3
//   Q14 random number: 1

// PUT YOUR CODE HERE


// ---------- QUESTION 15 ----------
// Magic8Ball
// - Create a function named "shakeMagic8Ball" that will return one of the strings described below
// - Using the random number function created in Q14, code the logic for a Magic 8 Ball 
// - If your random number is 1, return the phrase "It is certain"
// - If it is 2, return "Perhaps"
// - If it is 3, return "Absolutely not"

// EXAMPLE LOG:
//   Log this several times so you see different answers being logged
//   console.log ("Q15 Magic 8 Ball: ", shakeMagic8Ball());

// EXAMPLE OUTPUT:
//   Q15 Magic 8 Ball: It is certain
//   Q15 Magic 8 Ball: Perhaps
//   Q15 Magic 8 Ball: Absolutely not

// PUT YOUR CODE HERE

// ---------- GITHUB TASK ----------

// In this week's lesson content, you created your first GitHub repository. Confirm that your GitHub profile has a repository that:
// - Is named with your name and class name.
// - Is public.
// - Contains a blank README.md file

// Submit the link to the GitHub repository in the URL2 field in your assignment submission form.
// NO CODE FOR THIS TASK

---

<details>
<summary>Rubric (for AirHub reviewer and mentors)</summary>

### Required Deliverables/Tasks

- **Intro note** — Example console.log message text throughout (e.g., `"Q1: My first name is "`) is illustrative only; do not fail a student for phrasing log messages differently. Where a question states an exact required phrase or return value (Q4, Q8, Q10, Q11, Q15), that phrase is graded exactly — see below.
- **Q1** — Variables `firstName`, `lastName`, `country`. Use exactly as written (later tasks depend on these names). Values are the student's own name/birth country — Example, adapt to your own.
- **Q2** — Variables `floatingPoint`, `integer`, `negative`. Use exactly as written (later tasks depend on these names). Values are the student's own numbers — Example, adapt to your own.
- **Q3** — Two boolean variables, one `true` and one `false`. Names are the student's choice — Example, any descriptive name is fine.
- **Q4** — Variables `firstHelloString` (built with `+`) and `secondHelloString` (built with a template literal), both reusing the Q1 variables (not new values). The sentence pattern "Hello, my name is [firstName] [lastName] and I was born in [country]." is required — use exactly as written; the name/country values inside it are the student's own from Q1.
- **Q5** — Two variables holding (floatingPoint − integer) and (integer + negative) from Q2. The assignment text does not specify names for these (only the example log does) — Example, any reasonable variable names are acceptable; do not fail for not using `subtractionVariable`/`additionVariable`.
- **Q6** — Variables `nameLength`, `firstInitial`, `lastInitial`, `capitalize`, all derived from the Q1 `firstName`. Use exactly as written. Note: `lastInitial` is the last letter of the **first** name, not the last name — do not fail a student for using firstName here.
- **Q7** — Variable `answer`, set via if/else comparing Q2's `integer` to 10. Use exactly as written.
- **Q8** — Variable `age` (student's own age — Example). Conditional must log the exact phrase `"Age is just a number!"` (age ≤ 30) or `"Young at heart!"` (age > 30) — use exactly as written.
- **Q9** — Variable `exampleNum`, a floating-point number with 4 decimal places, rounded to 2 decimals using `toFixed()`. Use exactly as written (name); the number itself is the student's own — Example.
- **Q10** — Function `assignMessageString`, with internal variable `message` set to `"Welcome to Code the Dream!"`, returned. Use exactly as written (name and returned string).
- **Q11** — Function `combineStrings`, with internal variables `string1` and `string2` assigned `'Good'` and `'Evening'` respectively, returned concatenated with a space. Use exactly as written — these values are required, not the student's choice.
- **Q12** — Function `useParams` taking one parameter and returning it fully capitalized. Use exactly as written (function name); the example call `useParams("hello")` is illustrative only.
- **Q13** — Variables `word1`/`word2` (any strings — Example), and function `biggestStringLength(word1, word2)` returning the length of the longer string (or the shared length if equal). Use exactly as written (names).
- **Q14** — Function `returnRandomNum` returning a random integer 1–3 inclusive. Use exactly as written.
- **Q15** — Function `shakeMagic8Ball`, using the Q14 function, returning `"It is certain"` (1), `"Perhaps"` (2), or `"Absolutely not"` (3). Use exactly as written (function name and returned phrases).
- **GitHub Task** — A public GitHub repository named with the student's name and the class name, containing a blank `README.md`, submitted as a link in the URL2 field. This is verified by the submitted link, not by code — do not look for or require code for this task.

### Optional Deliverables/Tasks

Do not fail a student for omitting any of these. The assignment marks all of them as "Optional" (originally "Stretch Goal").

- **Q2** — Variable `bigNumber`, 16+ digits long, checked against console output for precision loss.
- **Q6** — Variable `weirdInitials`: the capitalized last letters of any first/last name pair.
- **Q7** — Variable `stretchAnswer` using if/else-if/else against 10 ("less than"/"equal to"/"greater than"), plus `typeof` logging for `answer` and `stretchAnswer`.
- **Q8** — A template-literal version of the phrase that includes the student's own first name (e.g., "Sally, age is just a number!") — the example names are illustrative only.
- **Q13** — Testing `biggestStringLength` with an empty string as one of the inputs.

</details>
