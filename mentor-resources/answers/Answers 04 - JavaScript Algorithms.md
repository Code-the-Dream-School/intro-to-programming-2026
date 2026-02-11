``` javascript

//----------------------------------
// LESSON 4 ALGORITHMS
//----------------------------------

// ---------- QUESTION 1 ----------
// Create a function called 'convertTemp' that takes 1 temperatue parameter in celsius and return the temperature in Fahrenheit.  Log both the input and output values

// EXAMPLE LOG:
//    console.log("Q1 convertTemp: ", celsiusTemp, convertTemp(celsiusTemp));
// EXAMPLE OUTPUT:
//    Q1 convertTemp: 0 32

// Call convertTemp with several different celsium temperatures

// PUT YOUR CODE HERE

function convertTemp(celsius) {
  const fahrenheit = (celsius * 9/5) + 32;
  return fahrenheit;
}

// Test cases
console.log ("Q1 convertTemp: ", 0, convertTemp(0));         // Should log: Q1 convertTemp: 0, 32
console.log ("Q1 convertTemp: ", 25, convertTemp(25));       // Should log: Q1 convertTemp: 25,77
console.log ("Q1 convertTemp: ", -10, convertTemp(-10));     // Should log: Q1 convertTemp: -10, 14

// ---------- QUESTION 2 ----------
// Create a function called 'reverseString' that takes 1 string parameter and returns the reverseString.  Use a for loop.  Log both the input and output values.

// EXAMPLE LOG:
//    console.log("Q2 reverseString: ", inputString, reverseString(inputString));
// EXAMPLE OUTPUT:
//    Q2 reverseString: HelloWorld dlroWolleH

// Call reverseString with several different strings.  Make sure it works for an empty string.

// PUT YOUR CODE HERE

function reverseString(str) {
 
 let reversed = '';
  for (let i = str.length - 1; i >= 0; i--) {
    reversed += str[i];
  }
 
 return reversed;
}

// Test cases
console.log ("Q2 reverseString: ", "HelloWorld", reverseString("HelloWorld"));   // Q2 reverseString: HelloWorld dlroWolleH
console.log ("Q2 reverseString: ", "JavaScript", reverseString("JavaScript"));   // Q2 reverseString: JavaScript tpircSavaJ  
console.log ("Q2 reverseString: ", "", reverseString(""));                       // Q2 reverseString: 

// ---------- QUESTION 3 ----------
// Let's make a useful math problem - create a tip calculator!  Create a function named tipCalculator that takes two parameters - billTotal and tipPercentage.   Return the total bill amount

// EXAMPLE LOG:
//    console.log("Q3 tipCalculator: ", billTotal, tipPercentage, tipCalculator (20, .20));
// EXAMPLE OUTPUT:
//    Q3 tipCalculator: 24

// PUT YOUR CODE HERE

// Don't forget your console.logs!

function tipCalculator(billTotal, tipPercentage) {
  const tipAmount = billTotal * tipPercentage;
  const totalAmount = billTotal + tipAmount;
  return totalAmount;
}

// Test cases
console.log("Q3 tipCalculator: ", 50, .20, tipCalculator (50, .20));    // Q3 tipCalculator: 50 0.2 60
console.log("Q3 tipCalculator: ", 80, 0, tipCalculator (80, 0));        // Q3 tipCalculator: 80 0 80 
console.log("Q3 tipCalculator: ", 100, .22, tipCalculator (100, .22));  // Q3 tipCalculator: 100 0.22 122

// ---------- QUESTION 4 ----------
// Create two variables named 'num1' and 'num2' and assign them integer values. Create a function called 'multiplyThese' that takes 2 parameters and returns the product  of the two parameters (as a reminder, a product is the resulting number when two numbers are multiplied together).

// EXAMPLE LOG:
//    console.log("Q4: ", num1, num2, multiplyThese(num1, num2));
// EXAMPLE OUTPUT: 
//    Q4 multiplyThese: 10 10 100

// PUT YOUR CODE HERE

// Create two variables


// Define the function
function multiplyThese(a, b) {
  return a * b;
}

let num1 = 6;
let num2 = 4;

// Call the function and log the result
console.log("Q4 multiplyThese: ", num1, num2, multiplyThese(num1, num2));   // Q4 multiplyThese: 6 4 24

num1 = -10;
num2 = 3;
console.log("Q4 multiplyThese: ", num1, num2, multiplyThese(num1, num2));   // Q4 multiplyThese: -10 3 -30

num1 = -10;
num2 = 0;
console.log("Q4 multiplyThese: ", num1, num2, multiplyThese(num1, num2));   // Q4 multiplyThese: -10 0 0 



function getAverage(a, b) {
  return (a + b) / 2.0;
}


// ---------- QUESTION 5 ----------
// Create a function called 'getAverage' that takes 2 parameters and returns their average.  NOTE: In some programming languages, the types of numbers you use in equations can effect what type of number (integer/floating point) you get as a result.  We suggest using 2.0 instead of 2 as you're calculating the average.

// EXAMPLE LOG:
//    console.log("Q5 getAverage: ", 3, 6, getAverage(3.0, 6.0));
// EXAMPLE OUTPUT: 
//    Q5 getAverage: 3 6 4.5

// PUT YOUR CODE HERE

function getAverage(a, b) {
  return (a + b) / 2.0;
}

// Test cases
console.log("Q5 getAverage: ", 3, 6, getAverage(3.0, 6.0));         // Q5 getAverage: 3 6 4.5
console.log("Q5 getAverage: ", 3.6, 10.3, getAverage(3.6, 10.3));   // Q5 getAverage: 3.6 10.3 6.95
console.log("Q5 getAverage: ", -3, 12, getAverage(-3, 12));         // Q5 getAverage: -3 12 4.5


// ---------- QUESTION 6 ----------
// Create a function named isPrime, that returns true or false based on whether the number is prime or not.
// Hint: To determine if a number is prime, you can check if it's divisible by any number from 2 up to the square root of the number.  0 and 1 are not prime numbers.

// EXAMPLE LOG:
//   console.log("Q6 isPrime: ", number, isPrime(number));
// EXAMPLE OUTPUT: 
//   Q6 isPrime: 12 false

// PUT YOUR CODE HERE
function isPrime(num) {
  if (num <= 1) return false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}

console.log("Q6 isPrime: ", 12, isPrime(12));   // Q6 isPrime: 12 false
console.log("Q6 isPrime: ", 1, isPrime(1));     // Q6 isPrime: 1 false
console.log("Q6 isPrime: ", 0, isPrime(0));     // Q6 isPrime: 0 false 
console.log("Q6 isPrime: ", 2, isPrime(2));     // Q6 isPrime: 2 true
console.log("Q6 isPrime: ", 13, isPrime(13));   // Q6 isPrime: 13 true 
console.log("Q6 isPrime: ", 719, isPrime(719));   // Q6 isPrime: 719 false


// ---------- QUESTION 7 ----------
// Now, using the 'isPrime' function created in the previous question, create another function named 'getPrimesUpTo' that takes an integer as an input and returns an array of all primes up to and including the input number. 
// Be sure to include several test cases

// EXAMPLE LOG:
//   console.log("Q7 getPrimesUpTo: ", number, isPrime(number));
// EXAMPLE OUTPUT:
//   Q7 getPrimesUpTo: 13 [2,3,5,7,11,13]

// PUT YOUR CODE HERE

function getPrimesUpTo(limit) {
  let primes = [];
  for (let i = 2; i <= limit; i++) {
    if (isPrime(i)) {
      primes.push(i);
    }
  }
  return primes;
}

// Test cases
console.log("Q7 getPrimesUpTo: ", 1, getPrimesUpTo(1));    // Q7 getPrimesUpTo: 1 []
console.log("Q7 getPrimesUpTo: ", 13, getPrimesUpTo(13));  // Q7 getPrimesUpTo: 13 [2,3,5,7,11,13]
console.log("Q7 getPrimesUpTo: ", 4, getPrimesUpTo(4));    // Q7 getPrimesUpTo: 13 [2,3]


// ---------- QUESTION 8 ----------
// Now, we're going to write several functions that calculate a student's grade.  
// First, write a function named 'calculateAverage' that takes an input array of scores and calculates a student's average based on those scores.
// Check all of the grades in the array and ignore any values that are not in the range 0 - 100.
// Also, make sure that an empty array or no valid values in the array do not result in an error (hint: make sure you aren't dividing by 0)

// EXAMPLE LOG:
//   console.log("Q8 calculateAverage: ", calculateAverage(scores));
// EXAMPLE OUTPUT:
//   Q8 calculateAverage: 85  // input array let scores = [90, 80, 85];

// PUT YOUR CODE HERE

function calculateAverage(scores) {
  let validScores = [];
  
  for (let i = 0; i < scores.length; i++) {
    let score = scores[i];
    if (score >= 0 && score <= 100) {
      validScores.push(score);
    }
  }

  if (validScores.length === 0) return 0; // Avoid dividing by zero

  let sum = 0;
  for (let i = 0; i < validScores.length; i++) {
    sum += validScores[i];
  }

  return sum / validScores.length;
}

// Test cases

let scores = [90, 80, 85];
console.log("Q8 calculateAverage: ", calculateAverage(scores));   // Q8 calculateAverage: 85 

scores = [80, 0, 90, 95];
console.log("Q8 calculateAverage: ", calculateAverage(scores));   // Q8 calculateAverage: 66.25

scores = [180, 90, 95];
console.log("Q8 calculateAverage: ", calculateAverage(scores));   // Q8 calculateAverage: 92.5

scores = [];
console.log("Q8 calculateAverage: ", calculateAverage(scores));   // Q8 calculateAverage: 0


// ---------- QUESTION 9 ----------
// Now, create a function - getLetterGrade(average) - that takes a grade average and returns a letter grade based on the following scale.  Make sure you test with several averages.
// A: 90–100
// B: 80–89
// C: 70–79
// D: 60–69
// F: below 60

// EXAMPLE LOG:
//   console.log("Q9 getLetterGrade: ", getLetterGrade(95));
// EXAMPLE OUTPUT:
//   Q9 getLetterGrade(95): A

// PUT YOUR CODE HERE


function getLetterGrade(average) {
  if (average >= 90 && average <= 100) return 'A';
  else if (average >= 80) return 'B';
  else if (average >= 70) return 'C';
  else if (average >= 60) return 'D';
  else return 'F';
}

console.log("Q9 getLetterGrade(95): ", getLetterGrade(95));   // Q9 getLetterGrade(95): A
console.log("Q9 getLetterGrade(65): ", getLetterGrade(65));   // Q9 getLetterGrade(65): D
console.log("Q9 getLetterGrade(45): ", getLetterGrade(45));   // Q9 getLetterGrade(45): F


// ---------- QUESTION 10 ----------
// Create a 3rd function named - passed(letterGrade) - that returns true if a student's grade is A, B or C, false otherwise.  Make sure you handle a value other than A,B,C,D or F passed in.
//

// EXAMPLE LOG:
//   console.log("Q10 passed('A'): ", passed('A'));
// EXAMPLE OUTPUT:
//   Q10 passed('A''): true

// PUT YOUR CODE HERE


function passed(letterGrade) {
  return letterGrade === 'A' || letterGrade === 'B' || letterGrade === 'C';
}

console.log("Q10 passed('A'): ", passed('A'));  // Q10 passed('A'): true
console.log("Q10 passed('F'): ", passed('F'));  // Q10 passed('F'): false
console.log("Q10 passed('2'): ", passed('2'));  // Q10 passed('2'): false

// ---------- QUESTION 11 ----------
// Create a function named printClassResult (className, student, scores) that utilizes all three functions to output information on a student.
// Print yes is they have passed and no if they did not.

// EXAMPLE LOG:
//   printClassResult ("History 101", "Jane Doe", [60, 70, 85, 87]);  // no console.log since the logs are in the function
// EXAMPLE OUTPUT:
//   Q11: History 101 - Student:Jane Doe, Average: 75.5, Grade: C, Passed: yes

// PUT YOUR CODE HERE


function printClassResult(className, student, scores) {
  const avg = calculateAverage(scores);
  const grade = getLetterGrade(avg);
  const passing = passed(grade);

  console.log(`Q11: ${className} - Student: ${student}, Average: ${avg.toFixed(2)}, Grade: ${grade}, Passing: ${passing ? "Yes" : "No"}`);

}

printClassResult ("History 101", "Jane Doe", [60, 70, 85, 87]);
printClassResult ("History 101", "Jane Doe", [60, 70, 85, 87, 40, 20]);

// ---------- QUESTION 12 ----------
// Create a function named findMax() that takes an array of numbers and returns the largest number in the array.
// If the array is empty, return null.

// EXAMPLE LOG:
//   console.log("Q12 findMax: ", [3, 7, 2, 9, 5], findMax([3, 7, 2, 9, 5])); 
// EXAMPLE OUTPUT:
//   Q12 findMax: [3, 7, 2, 9, 5] 9

// EXAMPLE LOG:
//   console.log("Q12 findMax: ", [], findMax([]));  //empty array
// EXAMPLE OUTPUT:
//   Q12 findMax: [] null

// PUT YOUR CODE HERE

function findMax(arr) { 
  if(arr.length === 0) {
    return null;
  }

  let max = arr[0];
  for(let i = 0; i < arr.length; i++) {
    if(arr[i] > max) {
      max = arr[i];
    }
  }
  return max;
}
let arr = [3, 7, 2, 9, 5];
console.log("Q12 findMax: ", `${arr}`, findMax(arr));
arr = [];
console.log("Q12 findMax: ", `${arr}`, findMax(arr));

// ---------- QUESTION 13 ----------
// Create a function named factorial that takes a positive integer as input and returns its factorial(the product of all positive integers up to that number).
// If the input is 0, return 1.

// EXAMPLE LOG:
//   console.log("Q13 factorial: ", factorial(4));  
// EXAMPLE OUTPUT:
//   24  //4*3*2*1

// PUT YOUR CODE HERE
function factorial(num) {
  let product = 1;
  if(num == 0) {
    return 1;
  }
  
  for(let i = num; i > 0; i--) {
    product *= i;
  }
  return product;
}
console.log("Q13 factorial: ", factorial(4));  

// ---------- QUESTION 14 ----------
// Create a function named countVowels that takes a string as input and returns the number of vowels (a,e,i,o,u) in the string. Make sure it works for both uppercase and lowercase inputs.
// Print yes is they have passed and no if they did not.

// EXAMPLE LOG:
//   console.log("Q14 countVowels: ", "Hello World", countVowels("Hello World"));
// EXAMPLE OUTPUT:
//   Q14 countVowels: Hello World 3

// PUT YOUR CODE HERE

function countVowels(word) {
  let count = 0;
  const vowels = "aeiouAEIOU";
  for(let i = 0; i < word.length; i++) {
    if(vowels.includes(word[i])) {
      count++;
    }
  }
  return count;
}
console.log("Q14 countVowels: ", "Hello World", countVowels("Hello World"));


```