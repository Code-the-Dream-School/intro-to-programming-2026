``` javascript
//----------------------------------
// LESSON 2 LOOPS AND ARRAYS
//----------------------------------

//# JavaScript Loops and Arrays
// This is the coding assigment for the second week of the Intro to Programming course from Code the Dream. The concepts touched on in this assignment include:
//   - Simplify Repetitive Tasks with Loops
//   - Working with ‘for’ Loops
//   - Understanding Arrays

// In this assignment you will write your own code. Your instructions are listed as "comments", meaning the instructions are grayed out and start with '//' at the beginning of the line of code. Put your answers immediately below the instructions for each question. As mentioned in the Welcome to week 2 information to the right, you'll need to use console logs for all the questions to check your code output. Using a function in a console.log is very similar to how you were using them with variables last week. To invoke/call the function use the syntax:

//  console.log("Q#: ", functionName(anyInput))

// ---------- QUESTION 1 ----------
// Write a function called 'repeat' that takes 1 integer parameter and, using a for or while loop, prints out the string "Hello World!" to the console the same number of times as the parameter. NOTE: for this question, since your console log should be inside your function, you only need to call/invoke the function after you write it rather than call/invoke it inside of a console.log.

// EXAMPLE "LOG":
//    repeat(3);
// EXAMPLE OUTPUT:
//    Hello World!
//    Hello World!
//    Hello World!

// PUT YOUR CODE HERE
function repeat(integerNumber) {
  for (let i = 0; i < integerNumber; i++) {
    console.log("Hello World!");
  }
}

console.log("Q1: ");
repeat(3);

// ---------- QUESTION 2 ----------
// Write a function called 'pyramidCounting' that takes 1 integer parameter and returns the sum of all of the numbers between 0 and the parameter.

// EXAMPLE LOG:
//    console.log("Q2: ", pyramidCounting(4));
// EXAMPLE OUTPUT:
//    Q2: 10
// The mathematical explanation of this is 0+1+2+3+4 = 10.

//PUT YOUR CODE HERE

function pyramidCounting(num) {
  let sum = 0;
  for (let i = 0; i <= num; i++) {
    sum += i;
  }
  return sum;
}
console.log("Q2: ", pyramidCounting(4));

// ---------- QUESTION 3 ----------
// Write a function called 'noVowels' that take a string parameter and removes vowels from that string using a loop.

// EXAMPLE LOG:
//    console.log("Q3: ", noVowels(adventurous));
// EXAMPLE OUTPUT:
//    Q3: dvntrs

// PUT YOUR CODE HERE

//Example 1
const vowels = "aeiouAEIOU";

function noVowels(stringParameter) {
  let newString = "";

  for (i = 0; i < stringParameter.length; i++) {
    let isAVowel = false;

    for (j = 0; j < vowels.length; j++) {
      if (stringParameter[i] === vowels[j]) {
        isAVowel = true;
        break;
      }
    } //for

    if (!isAVowel) {
      newString = newString + stringParameter[i];
    } //if
  } //for

  return newString;
} //noVowels

console.log("Q3: ", noVowels("adventurous"));
console.log("Q3: ", noVowels("bc"));
console.log("Q3: ", noVowels("ao"));
console.log("Q3: ", noVowels(""));

//Example 2
function noVowels1(str) {
  let result = "";
  for (let i = 0; i < str.length; i++) {
    let char = str[i].toLowerCase();
    if (
      char !== "a" &&
      char !== "e" &&
      char !== "i" &&
      char !== "o" &&
      char !== "u"
    ) {
      result += str[i];
    }
  }
  return result;
}

console.log("Q3: ", noVowels1("Hello World"));

// ---------- QUESTION 4 ----------
// Write a function called 'vowelCount' that takes 1 string parameter and returns the number of vowels in that string.

// EXAMPLE LOG:
//    console.log("Q4: ", vowelCount('I love to code.'));
// EXAMPLE OUTPUT:
//    Q4: 6

// PUT YOUR CODE HERE
//Example 1
function vowelCount(aString) {
  let vowels = "aeiouAEIOU";
  let count = 0;
  for (let i = 0; i < aString.length; i++) {
    if (vowels.includes(aString[i])) {
      count++;
    } //if
  } //for
  return count;
} //function

console.log("Q4: ", vowelCount("I love to code."));
console.log("Q4: ", vowelCount("BCD"));
console.log("Q4: ", vowelCount("AAA"));

//Example 2
function vowelCount(str) {
  let count = 0;
  for (let i = 0; i < str.length; i++) {
    let char = str[i].toLowerCase();
    if (
      char === "a" ||
      char === "e" ||
      char === "i" ||
      char === "o" ||
      char === "u"
    ) {
      count++;
    }
  }
  return count;
}

console.log("Q4: ", vowelCount("Hello World"));

// ---------- QUESTION 5 ----------
// Write a function called 'numOfOdds' that takes 1 integer parameter and returns the number of odd numbers between 0 and that number, including the number if it's odd. (Hint: Use the modulo operator)

// EXAMPLE LOG:
//    console.log("Q5: ", numOfOdds(15));
// EXAMPLE OUTPUT:
//    Q5: 8

// PUT YOUR CODE HERE
function numOfOdds(num) {
  let count = 0;
  for (let i = 0; i <= num; i++) {
    if (i % 2 !== 0) {
      count++;
    }
  }
  return count;
}

console.log("Q5: ", numOfOdds(10));

// ---------- QUESTION 6 ----------
// Create two variables named 'empty' and 'full'.  Assign an empty array to the 'empty' variable and any array of strings or numbers to the 'full' variable.  Write a function called 'arrayChecker' that returns true if the array passed as a parameter is empty and false if not.  Check both the 'empty' and 'full' variables to make sure they are returning the expected values.

// EXAMPLE LOGS:
//    console.log("Q6 empty: ", arrayChecker(empty));
//    console.log("Q6 not empty: ", arrayChecker(full));
// EXAMPLE OUTPUTS:
//    Q6 empty: true
//    Q6 not empty: false

// PUT YOUR CODE HERE

const empty = [];
let full = ["dream", 19, "code", 24, 180];

function arrayChecker(anArray) {
  let check = true;
  if (anArray.length != 0) {
    check = false;
  }
  return check;
}
console.log("Q6 empty: ", arrayChecker(empty));
console.log("Q6 not empty: ", arrayChecker(full));

// ---------- QUESTION 7 ----------
// Write a function called 'getElementAt' that takes an array parameter and an integer parameter.  The function should return the element in the array at the given number index or 'null' if it doesn't exist.  Use your 'full' variable from Question 6 to test.

// EXAMPLE LOGS:
//    console.log("Q7: ", getElementAt(full, 2));
//    console.log("Q7: ", getElementAt(full, 7));
// EXAMPLE OUTPUT: (if the array assigned to variable 'full' is ["dream", 19, "code", 24, 180])
//    Q7: code
//    Q7: null

//Example 1
function getElementAt(anArray, anInteger) {
  let result = anArray.at(anInteger);
  if (result === undefined) {
    result = null;
  }
  return result;
}

console.log("Q7: ", getElementAt(full, 2));
console.log("Q7: ", getElementAt(full, 7));
console.log("Q7", getElementAt(empty, 1));

//Example 2
function getElementAtv2(arr, index) {
  if (index >= 0 && index < arr.length) {
    return arr[index];
  } else {
    return null;
  }
}
console.log("Q7: ", getElementAtv2(full, 2));
console.log("Q7: ", getElementAtv2(full, 7));
console.log("Q7", getElementAt(empty, 1));

// ---------- QUESTION 8 ----------
// Write a function called 'insertInArray' that takes an array parameter, makes a NEW array with the value '0' inserted at the second position in the NEW array.  The function should return the NEW array.  Use your 'full' variable from Question 6 to test.  NOTE: Assigning an array to a new variable does not make a copy, it's another reference to the same array.  To make a copy you can use the slice() method as in this example:
// let newArray = originalArray.slice()
// LEARNING MOMENT: Also console log the variable 'full' to compare the new array to the original.

// EXAMPLE LOG:
//    console.log("Q8: ", insertInArray(full));
//    console.log("original array: ", full);
// EXAMPLE OUTPUT: (if the array assigned to variable 'full' is ["dream", 19, "code", 24, 180])
//    Q8: ["dream", 0, 19, "code", 24, 180]
//    original array: ["dream", 19, "code", 24, 180]

// PUT YOUR CODE HERE
function insertInArray(anArray) {
  let startArray = anArray.slice(0, 1);
  startArray.push(0);

  let endArray = anArray.slice(1, anArray.length);

  const newArray = startArray.concat(endArray);

  return newArray;
}

console.log("Q8: ", insertInArray(full));

// ---------- QUESTION 9 ----------
// Write a function called 'compareArrays' that takes two Array parameters (containing numbers or strings only) and returns true if they are equal, false if not.  The purpose of this function should be to look at each element of the two arrays and compare them, returning false when they either hit two items that don't match, or returning false if the two arrays themselves are different lengths. You can test this with the 'empty' and 'full' variables from Question 6, and/or you can create a variable called 'compare' and assign it an array identical to 'full' to compare those.  To further test your function's accuracy, create a new variable called 'part' that is a partial copy of the 'full' variable and test that as well.

// REMEMBER: In JavaScript, 1 === '1' is false, but 1 == '1' is true. You'll need to use the triple equals operator which is more strict because it compares data type.

// EXAMPLE LOG:
//    console.log("Q9 same: ", compareArrays(full, compare));
// EXAMPLE OUTPUT: (if both arrays assigned to variable 'full' and 'compare' are ["dream", 19, "code", 24])
//    Q9 same: true

// EXAMPLE LOG:
//    console.log("Q9 different: ", compareArrays(full, empty));
// EXAMPLE OUTPUT: (if using variables from Question 6)
//    Q9 different: false

// EXAMPLE LOG:
//    console.log("Q9 partial: ", compareArrays(full, part));
// EXAMPLE OUTPUT: (if 'full' variable is ["dream", 19, "code", 24] and if 'part' variable is ["dream", 19, "code"])
//    Q9 different: false

//Solution 1
function compareArrays(arr1, arr2) {
  if (arr1.length !== arr2.length) {
    return false;
  }

  for (let i = 0; i < arr1.length; i++) {
    if (arr1[i] !== arr2[i]) {
      return false;
    }
  }

  return true;
}

// Testing with 'empty' and 'full' variables from Question 6
console.log("Q9 - empty and full: ", compareArrays(empty, full));

// Creating a variable 'compare' as a copy of 'full' array
let compare = [...full];
console.log("Q9 - full and compare: ", compareArrays(full, compare));

// Creating a variable 'part' as a partial copy of 'full' array
let part = full.slice(0, 2);
console.log("Q9 - full and part: ", compareArrays(full, part));

//Example 2
//if order matters
const compareArraysV1 = (arr1, arr2) =>
  arr1.length == arr2.length && arr1.every((el, i, arr) => arr[i] === arr2[i]);
let compare1 = ["dream", 19, "code", 24];
console.log("Q9 Example 2 if order matters: ", compareArraysV1(full, compare1));


//Example 3 if order does not matter
const count = (el, arr) => arr.filter((ele) => ele === el).length;
const compareArraysV2 = (arr1, arr2) =>
  arr1.length == arr2.length &&
  arr1.every(
    (el, i, arr) =>
      arr.filter((ele) => ele === el).length ==
        arr2.filter((ele) => ele === el).length && arr2.includes(el)
  );
full = ["dream", 19, 24, "code"];
compare = ["dream", 19, "code", 24];
console.log(
  "Q9 Example 3 if order does not matter: ",
  compareArraysV2(full, compare1)
);

// ---------- QUESTION 10 ----------
// Create a variable called 'numbers' and assign it an array with at least 3 numbers as elements (example: [10, 3, 4]).  Write a function called 'calculateTotal' that takes one array parameter and loops through the array in order to return the sum of all the array elements.
// STRETCH GOAL: use the `reduce()` method

// EXAMPLE LOG:
//    console.log("Q10: ", calculateTotal(numbers));
// EXAMPLE OUTPUT: (if the array assigned to variable 'numbers' is [3, 4, 2 ,8])
//    Q10: 17

// PUT YOUR CODE HERE
//Example 1
let numbers = [3, 4, 2 ,8]; // Create a variable called 'numbers' and assign it an array with at least 3 numbers

function calculateTotal(arr) {
  let total = 0; // Initialize a variable 'total' to store the sum

  for (let i = 0; i < arr.length; i++) {
    total += arr[i]; // Add each element of the array to 'total'
  }

  return total; // Return the sum of all array elements
}

// Testing with the 'numbers' array
console.log("Q10 - Total: ", calculateTotal(numbers));

//Example 2 with reduce
const calculateTotal1 = (arr) => arr.reduce((acc, el) => acc + el, 0);
console.log("Q10 - Total:", calculateTotal1(numbers));

// ---------- QUESTION 11 ----------
// Write two functions called 'findEvens' and 'findOdds' that each take one array parameter and each returns a NEW Array of all the even or odd numbers as indicated.  NOTE: Assigning an array to a new variable does not make a copy, it's another reference to the same array.  To make a copy you can use the slice() method as in this example:
// let newArray = originalArray.slice()
// STRETCH GOAL: use the `filter()` method

// EXAMPLE LOG:
//    console.log("Q11 evens: ", findEvens([10,2,3,19,7,6,93]));
//    console.log("Q11 odds: ", findOdds([10,2,3,19,7,6,93]));
// EXAMPLE OUTPUT:
//    Q11 evens: [10,2,6]
//    Q11 odds: [3,19,7,93]

// PUT YOUR CODE HERE
const findEvens = (arr) => arr.filter((el) => !(el % 2));
const findOdds = (arr) => arr.filter((el) => el % 2);
let arr208 = [10, 2, 3, 19, 7, 6, 93];
console.log("Q11 evens: ", findEvens(arr208));
console.log("Q11 odds: ", findOdds(arr208));

// ---------- QUESTION 12 ----------
// Write a function called 'makeSquares' that takes one array parameter and returns a NEW Array with the squared values of each of the numbers.  NOTE: Assigning an array to a new variable does not make a copy, it's another reference to the same array.  To make a copy you can use the slice() method as in this example:
// let newArray = originalArray.slice()
// STRETCH GOAL: use the `map()` method

// EXAMPLE LOG:
//    console.log("Q12: ", makeSquares([2,5,8]));
// EXAMPLE OUTPUT:
//    Q12: [4,25,64]

// PUT YOUR CODE HERE

//Example 1
function makeSquaresV1(arr) {
  return arr.map((el) => el ** 2);
}
console.log("Q12 Example 1: ", makeSquaresV1([2, 5, 8]));

//Example 2
const makeSquaresV2 = (arr) => arr.map((el) => el ** 2);
console.log("Q12 Example 2: ", makeSquaresV2([2, 5, 8]));

// ---------- QUESTION 13 ----------
// Write a function called 'displaySkills' that takes an array of string values that correspond to skills that you have.
// Iterate through the array and display each skill.

// EXAMPLE CALL:
//    const skills = ["JavaScript", "HTML", "CSS", "Adobe Photoshop", "GitHub"];
//    displaySkills(skills);
// EXAMPLE OUTPUT:
//    Javascript
//    HTML
//    CSS
//    Adobe Photoshop
//    GitHub

// PUT YOUR CODE HERE
const skills = ["JavaScript", "HTML", "CSS", "Adobe Photoshop", "GitHub"];

function displaySkills(skillList) {

  for (let i = 0; i < skillList.length; i++) {
    console.log(skillList[i]);
  }

}

displaySkills(skills);



// ---------- QUESTION 14 ----------
// Back in the "old days", the early 2000s, this was a famous technical interview question. Write a function definition that takes NO parameters. The function will loop from 1 to 15 and return an array of numbers. While looping, the function will check if the current value in the loop is divisible by 3, by 5, or by both. If the current value in the loop is divisible by 3, the function will add the string "fizz" to an array. If the current value in the loop is divisible by 5, the function will add the string "buzz" to the array. If the current value in the loop is divisible by both, the function will add the value "fizzbuzz" to the array. If the number isn't divisible by 3, 5, OR both, it will add the number to the array.  The function will return the array of values.

// EXAMPLE LOG:
//    console.log("Q13: ", fizzBuzz();
// EXAMPLE OUTPUT:
//    Q14: [1,2,'fizz',4,'buzz','fizz',7,8,'fizz','buzz',11,'fizz',13,14,'fizzbuzz']

// PUT YOUR CODE HERE

// Example 1
function fizzBuzzV2() {
  let result = [];
  for (let i = 1; i <= 15; i++) {
    result.push(
      !(i % 3) && !(i % 5)
        ? "fizzbuzz"
        : !(i % 3)
        ? "fizz"
        : !(i % 5)
        ? "buzz"
        : i
    );
  }
  return result;
}
console.log("Q13 Example 1: ", fizzBuzzV2());

// Example 2
function fizzBuzzV3() {
  return Array.from(Array(15)).map((_, i) =>
    !((i + 1) % 3) && !((i + 1) % 5)
      ? "fizzbuzz"
      : !((i + 1) % 3)
      ? "fizz"
      : !((i + 1) % 5)
      ? "buzz"
      : i + 1
  );
}
console.log("Q13 Example 2: ", fizzBuzzV3());

// ---------- QUESTION 15 ----------
// Write a function called testScope that shows the difference between global, function and block scope.
// Create 3 variables - 
//   let globalVar = "globarVar";
//   let functionVar = "functionVar";
//   let blockVar = "blockVar";
// Place the variables correctly in your code and log them.
// Also, place 2 log statements for the functionVar and blockVar that are commented out, but would result in an error if uncommented - because the variable they are referencing is out of scope.

// PUT YOUR CODE HERE
let globalVar = "globalVar";

function testScope() {
  let functionVar = "functionVar";

  for (let i = 0; i <= 1; i++) {
    let blockVar = "blockVar";
    console.log(globalVar);
    console.log(functionVar);
    console.log(blockVar);
  }

  // console.log(blockVar); // Uncommenting this line would cause an error
}

testScope();

```