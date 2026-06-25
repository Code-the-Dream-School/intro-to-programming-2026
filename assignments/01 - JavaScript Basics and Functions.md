
``` javascript

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
// - Once you feel the console output is correct, move onto the next questions

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

// STRETCH GOAL: You'll see "Stretch Goal"s throughout the course. Stretch Goals are optional, but are encouraged as they help you try your hand at something a little more advanced for the week/assignment/question. 

// STRETCH GOAL:
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

// STRETCH GOAL: 
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

// STRETCH GOAL: 
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
//   Q7 answer type: string

// PUT YOUR CODE HERE


// ---------- QUESTION 8 ----------
// More Logic!
// - Declare a variable called "age"
// - Assign it the value of your age in years
// - Create a conditional statement that will log the phrase "Age is just a number!" if your age is less than or equal to 30 and "Young at heart!" if your age is greater than 30.

// STRETCH GOAL: Combine your skills!  Use template literals to log your name in this phrase: "Sally, age is just a number!" or "Jose, you're young at heart!" replacing these examples (Sally and Jose) with your first name instead.

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

// STRETCH GOAL: Achieve the same results as Q10 using Math methods instead of Number methods. HINT: you may need to alter the variable over a series of calculations/method uses.

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
// - Stretch your skills by making an empty string and seeing what happens in that situation.

// EXAMPLE LOG:
//   console.log("Q13: ", biggestStringLength(word1, word2));
// EXAMPLE OUTPUT: (if your word1 was 'Code' and word2 was 'Dream')
//   Q13: 5

// PUT YOUR CODE HERE


// ---------- QUESTION 14 ----------
// Random Number Generator
// - Create a function named "returnRandomNum"
// - Inside your function declare a variable "randomNum" to hold the value returned from a random number generator
// - Use Math.random() which returns a number between 0 and 1 (greater or equal to 0, less than 1)
// - 'Math.random() * 10' gives a range from 0 up to but not including 10
// - Math.floor() rounds a number down to the nearest whole integer
// - Math.floor(Math.random() * 10) returns a random integer between 0 and 9 (both included)
// - return a randomNum from the function that is between 1 and 3

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
// - If your random number is 1, console.log the phrase "It is certain"
// - If it is 2, console.log "Perhaps"
// - If it is 3, console.log "Absolutely not"

// EXAMPLE LOG:
//   Log this several times so you see different answers being logged
//   console.log ("Q15 Magic 8 Ball: ", shakeMagic8Ball()");

// EXAMPLE OUTPUT:
//   Q15 Magic 8 Ball: It is certain
//   Q15 Magic 8 Ball: Perhaps
//   Q15 Magic 8 Ball: Absolutely not

// PUT YOUR CODE HERE


```
