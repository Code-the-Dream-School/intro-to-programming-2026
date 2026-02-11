//--------------- IMPORTANT!!! ---------------

// IF YOU HAVE NOT READ THE README.md FILE YET, double click on that file in the "Files" panel to the left now and read it before you begin your assignment!

//---------- OVERVIEW AND INSTRUCTIONS ----------

//# JavaScript Objects
// This is the coding assigment for the fourth week of the Intro to Programming course from Code the Dream. The concepts touched on in this assignment include:
//   - Object Basics
//   - Primitive vs Object Types
//   - Object Destructuring
//   - Manipulating Objects

// NOTE: Arrays are a kind of Object in JavaScript (which is why you can reference an element by number and see what string/number/etc. is in that position of the array).  JavaScript Objects also support a different type of array referred to as an associative array.  Rather than an item in the array being addressed by an integer, it is addressed by a string, and allows you to associate a string name with any type of JavaScript value.  It stores a set of key:value pairs, where the key is a string.

// In this assignment you will write your own code. Your instructions are listed as "comments", meaning the instructions are grayed out and start with '//' at the beginning of the line of code. Put your answers immediately below the instructions for each question. As mentioned in the README.md file, you'll need to use console logs for all the questions to check your code output. Using a function in a console.log is very similar to how you were using them with variables last week. To invoke/call the function use the syntax:

//  console.log("Q#: ", functionName(anyInput))

// As always, click the green Run button at the top of the screen to see the output of your called functions in the Console tab to the right of this screen. Check to make sure that the output you get in your Console is the expected output.

// ---------- QUESTION 1 ----------
// Objects are a way to store property:value pairs of data in a variable.  First, create an object called 'myPet'.  Add three properties called 'name', 'species', and 'color' to the 'myPet' object below and assign each of them values.  Use your console.log to print the object.  Use your console.log's to print the values of each property to the console.

// EXAMPLE LOG:
//    console.log("Q1 object: ", myPet);
//    console.log("Q1 name: ", myPet.name);
//    console.log("Q1 species: ", myPet.species);
//    console.log("Q1 color: ", myPet.color);
// EXAMPLE OUTPUT:
//    Q1 object:  {"name":"Teddy","species":"ferret","color":"brown"}
//    Q1 name: Teddy
//    Q1 species: ferret
//    Q1 color: brown

// PUT YOUR CODE HERE
const myPet = { name: "Teddy", species: "ferret", color: "brown" };
console.log("Q1 object: ", myPet);
console.log("Q1 name: ", myPet.name);
console.log("Q1 species: ", myPet.species);
console.log("Q1 color: ", myPet.color);

// ---------- QUESTION 2 Modifying properties ---------
// Now let's see how we can modify the properties. Modify the 'name' property of the 'myPet' object. This name should be different than the value used in Question 1 (e.g. Henry ). Use your console.log's to print the myPet console. Verify the 'name' property is different than the value in Question 1.

// EXAMPLE LOG:
//    console.log("Q2 updated object", myPet);
// EXAMPLE OUTPUT:
//    Q2 updated object:  {"name":"Henry","species":"ferret","color":"brown"}

// PUT YOUR CODE HERE
myPet.name = "Henry";
console.log("Q2 updated object", myPet);

// ---------- QUESTION 3 Looping thru properties ---------
// Now let's see how we can loop thru the properties - this is a common task in JavaScript. Use a for...in loop, a special type of loop in JavasScript designed specifically for iterating over the properties of an object.  See https://www.w3schools.com/js/js_loop_forin.asp for reference.
//  Write a for...in loop that iterates through each property in the myPet object and prints the property name and its value to the console in the following format:
//Q4: propertyName: propertyValue
//Use console.log() inside the loop to display each key-value pair.

// EXAMPLE LOG in the loop - replace <..>  :
//    console.log("Q3: "+ <Supply key here> + ":",  <Supply value here> );
// EXAMPLE OUTPUT:
//    Q3: name: Henry
//    Q3: species: ferret
//    Q3: color: brown

// PUT YOUR CODE HERE
for (let key in myPet) {
  console.log("Q3: " + key + ":", myPet[key]);
}

// ---------- QUESTION 4 ----------
//Let’s explore how to work with object data inside a function. Your task is to define a method called describe on the myPet object. This method should take no parameters and return a sentence using a template literal that describes your pet using its properties.

//Add a method named describe to the myPet object.
//Inside the method, use a template literal to construct a sentence using the name, color, and species properties.
//Use console.log() to display the result in the format shown below.

// EXAMPLE LOG:
//    console.log("Q4: ", myPet.describe());
// EXAMPLE OUTPUT:
//Q4: Teddy is a brown ferret.

//Stretch goal: Use "this" keyword.  Instead of referencing the object name directly (e.g., myPet.name), update your method to use the this keyword to access the object's properties. This makes your method more flexible and reusable.

// PUT YOUR CODE HERE
myPet.describe = function () {
  return `${myPet.name} is a ${myPet.color} ${myPet.species}.`;
};
console.log("Q4: ", myPet.describe());

myPet.describev1 = function () {
  return `${this.name} is a ${this.color} ${this.species}.`;
};
console.log("Q4 v1: ", myPet.describev1());

//---------- QUESTION 5 ----deleting a property------
//Using myPet, remove the property color.  Verify the deletion by checking whether the myPet object still has a property named color.  It returns true if the property exists and false otherwise

// EXAMPLE LOG:
//     console.log("Q5", "Color property deleted:", !myPet.hasOwnProperty('color'));
// EXAMPLE OUTPUT:
//Q5 Color property deleted: true

delete myPet.color;
console.log("Q5", "Color property deleted:", !myPet.hasOwnProperty('color'));


//---------- QUESTION 6 ----array of objects, for each------
//Create a variable named pets and assign it an array containing three pet objects. Each object should include three properties: name, species, and color with appropriate values. Then, define a function called printPets that uses the forEach method to loop through the array and log each pet’s details to the console. Note: console.log is called within the function

//EXAMPLE CALL:
//   const pets = [
//     { name: "WillBe", species: "bird", color:"gray"},
//     { name: "Oshie", species: "cat", color: "multi" },
//     { name: "Sunny", species: "dog", color: "black" } ]
//
//  Call the function with the pets array
//        console.log ("Q6:");
//        printPets(pets);

// EXAMPLE OUTPUT:
//Q6:
//{ name: 'WillBe', species: 'bird', color: 'gray' }
//{ name: 'Oshie', species: 'cat', color: 'multi' }
//{ name: 'Sunny', species: 'dog', color: 'black' }

// PUT YOUR CODE HERE

function printPets(pets) {
  //Iterating over the array and printing each pet's details
  pets.forEach((pet) => {
    console.log(pet);
  });
}
const pets = [
  { name: "WillBe", species: "bird", color: "gray" },
  { name: "Oshie", species: "cat", color: "multi" },
  { name: "Sunny", species: "dog", color: "black" },
];
console.log("Q6:");
printPets(pets);

//---------- QUESTION 7 --- Write a construction function to create Pet objects------
//Write a JavaScript constructor function named Dog that defines a blueprint for creating Dog objects. Each Dog object should include the following properties: name, breed, and age. Using this constructor, create two distinct Dog instances (dog1 and dog2) with different values for each property. Finally, use console.log() to display both Dog instances in the console.

//EXAMPLE CALL:
// Creating new Dog instances
//let dog1 = new Dog("Kroger", "greyhound", 8);
//let dog2 = new Dog("Destiny","shepherd" , 14);

// Displaying the Dog instances
//console.log("Q7", dog1);
//console.log("Q7", dog2);

// EXAMPLE OUTPUT:
//Q7: Dog { name: 'Kroger', breed: 'greyhound', age: 8 }
//Q7: Dog { name: 'Destiny', breed: 'shepherd', age: 14 }


// PUT YOUR CODE HERE
function Dog (name, breed, age){
  this.name = name;
  this.breed = breed;
  this.age = age;
}

// Creating new Dog instances
let dog1 = new Dog("Kroger", "greyhound", 8);
let dog2 = new Dog("Destiny","shepherd" , 14);

// Displaying the Dog instances
console.log("Q7:", dog1);
console.log("Q7:", dog2);


//---------- QUESTION 8 --- Write a function that compares two objects-----
//Write a function that compares two Dog instances objects and checks if they have the same keys and values. Write a function called areObjectsEqual(obj1, obj2) that returns true if both objects have the same keys and values, and false otherwise. 
//Reuse:
// - dog1 from question 7
// - dog2 from question 7
// Then, create:
// - dog3: an object with the same keys and values as dog1.
// - dog4: an object based on dog1 but with one additional key.

// Use console.log() to test your function with various object comparisons.
//EXAMPLE CALL:
//console.log("Q8: Are objects equal - different values:", areObjectsEqual(dog1, dog2)); 
//console.log("Q8: Are objects equal? - same key and values:", areObjectsEqual(dog1, dog3)); 
//console.log("Q8: Are objects equal? - different keys:", areObjectsEqual(dog1, dog4)); 

// EXAMPLE OUTPUT:
//Q8: Are objects equal - different values: false
//Q8: Are objects equal? - same key and values: true
//Q8: Are objects equal? - different keys: false

// PUT YOUR CODE HERE
let dog3 = new Dog("Kroger", "greyhound", 8);
let dog4 = new Dog("Destiny","shepherd" , 14);
dog4.extraproperty = "extra";

// Step 2: Function to compare objects
function areObjectsEqual(obj1, obj2) {
  const keys1 = Object.keys(obj1);
  const keys2 = Object.keys(obj2);

  // Check if number of keys is the same
  if (keys1.length !== keys2.length) {
    return false;
  }

  // Check if values for each key are the same
  for (let key of keys1) {
    if (obj1[key] !== obj2[key]) {
      return false;
    }
  }

  return true;
}

// Step 3: Test the function
console.log("Q8: Are objects equal - different values:", areObjectsEqual(dog1, dog2)); 
console.log("Q8: Are objects equal? - same key and values:", areObjectsEqual(dog1, dog3)); 
console.log("Q8: Are objects equal? - different keys:", areObjectsEqual(dog1, dog4)); 


//---------- QUESTION 9 --- Date object for current date-----
//Learn how to use the built-in Date object in JavaScript to retrieve and display the current date. See https://www.w3schools.com/js/js_dates.asp as a reference. Create a variable called currentDate. Assign it the value of a new Date() object.

//EXAMPLE CALL:
//console.log("Q9: Current Date:", currentDate);

// EXAMPLE OUTPUT: Note Time will differ, below is an example only
//Q9: Current Date: 2025-09-13T23:47:23.858Z 

// PUT YOUR CODE HERE
// Step 1: Create a Date object
const currentDate = new Date();

// Step 2: Log the full date
console.log("Q9: Current Date:", currentDate);

//---------- QUESTION 10 --- Date object for current date year, month, date-----
//Use JavaScript's Date object to retrieve specific parts of the current date. Using the currentDate from Question 9, write three separate lines of code to extract:

//The year using .getFullYear()
//The month using .getMonth() (remember: months are zero-indexed!)
//The day using .getDate()
//Use console.log() to display each value with a descriptive label.

//EXAMPLE CALL:
//console.log("Q10 Year:", year);
//console.log("Q10 Month:", month);
//console.log("Q10 Day:", day);

// EXAMPLE OUTPUT: Note Time will differ, below is an example only
//Q10 Year: 2025
//Q10 Month: 9
//Q10 Day: 13

// PUT YOUR CODE HERE
// Extract and log the year, month, and day
const year = currentDate.getFullYear();
const month = currentDate.getMonth() + 1; // Add 1 to adjust for zero-indexing
const day = currentDate.getDate();

console.log("Q10 Year:", year);
console.log("Q10 Month:", month);
console.log("Q10 Day:", day);


