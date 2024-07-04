## pythontutor.com


##  BASICS
// Variable declaration
let x = 10;
const y = 20;
var z = 30; // var is function-scoped, let and const are block-scoped

// Data types
let number = 42;               // Number
let string = "Hello, world!";  // String
let boolean = true;            // Boolean
let array = [1, 2, 3];         // Array
let object = { key: "value" }; // Object
let undefinedVar;              // Undefined
let nullVar = null;            // Null

// Comments
// Single-line comment
/*
  Multi-line comment
*/
## String manipulation

1. Concatenation -Combining multiple strings into one.

2. Substring Extraction - Extracting a portion of a string.
  --slice(start, end): Extracts a section of a string and returns it as a new string.
  --substring(start, end): Similar to slice, but does not accept negative indices.
  --substr(start, length): Extracts a substring starting from start of length length.

3.  Changing Case - to upper or lower
  
4.  Trimming - Removing whitespace from the beginning and end of a string.
   --trim(): Removes whitespace from both ends of a string.
   --trimStart() / trimLeft(): Removes whitespace from the beginning.
   --trimEnd() / trimRight(): Removes whitespace from the end.

5.  Replacing Substrings - ****Replacing parts of a string with another string.
  --replace(searchValue, newValue): Replaces the first occurrence of searchValue with newValue.
  -- replaceAll(searchValue, newValue): Replaces all occurrences of searchValue with newValue.

  example let str = "Hello World";
let newStr = str.replace("World", "Universe");  // "Hello Universe"
let newStrAll = str.replaceAll("o", "O");  // "HellO WOrld"

6. Splitting and Joining - Splitting a string into an array and joining an array into a string.
 -- split(separator): Splits a string into an array of substrings.
  --join(separator): Joins all elements of an array into a string.

  let str = "Hello World";
let arr = str.split(" ");  // ["Hello", "World"]
let joined = arr.join(" ");  // "Hello World"

7.  Searching - Finding the position of a substring or checking for its existence.
   --indexOf(substring): Returns the index of the first occurrence of substring.
   --lastIndexOf(substring): Returns the index of the last occurrence of substring.
   --includes(substring): Checks if the string contains substring.

   let str = "Hello World";
let position = str.indexOf("World");  // 6
let lastPosition = str.lastIndexOf("o");  // 7
let contains = str.includes("Hello");  // true



## fUNCTIONS

// Function declaration
function add(a, b) {
  return a + b;
}

// Function expression
const subtract = function(a, b) {
  return a - b;
};

// Arrow function
const multiply = (a, b) => a * b;

// Callback function
function greet(name, callback) {
  console.log("Hello, " + name);
  callback();
}

greet("Alice", () => console.log("Welcome!"));


## CONTROL FLOW

// If-else
if (x > y) {
  console.log("x is greater than y");
} else if (x < y) {
  console.log("x is less than y");
} else {
  console.log("x is equal to y");
}

// Switch-case
let day = 2;
switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  default:
    console.log("Another day");
}

// For loop
for (let i = 0; i < 5; i++) {
  console.log(i);
}

// While loop
let count = 0;
while (count < 5) {
  console.log(count);
  count++;
}

// Do-while loop
do {
  console.log(count);
  count++;
} while (count < 5);


## ARRAYS

let fruits = ["apple", "banana", "cherry"];

// ## Accessing elements
console.log(fruits[0]); // "apple"

// Adding elements
fruits.push("date"); // ["apple", "banana", "cherry", "date"]

// Removing elements
fruits.pop(); // ["apple", "banana", "cherry"]
fruits.shift(); // ["banana", "cherry"]
fruits.unshift("apple"); // ["apple", "banana", "cherry"]

// Iterating over arrays
fruits.forEach((fruit) => console.log(fruit));

// Mapping arrays
let upperFruits = fruits.map((fruit) => fruit.toUpperCase());
console.log(upperFruits); // ["APPLE", "BANANA", "CHERRY"]

// Filtering arrays
let filteredFruits = fruits.filter((fruit) => fruit !== "banana");
console.log(filteredFruits); // ["apple", "cherry"]

// Reducing arrays
let total = [1, 2, 3, 4].reducconst swapper = function (key1, object1, key2, object2) {
  console.log("Swap!");

  // Put your solution here

  console.log("object1: ", object1);
  console.log("object2: ", object2);
};

swapper("a", { a: 1, b: 2, c: 3 }, "c", { a: 4, b: 3, c: 5 });
swapper("b", { a: 8, b: 7, c: 6 }, "d", { a: 5, b: 1, c: 2, d: 12 });
swapper("c", { a: 1, b: 3, c: 3, d: 7 }, "c", { a: 4, b: 0, c: 5 });

    console.log("Hello, my name is " + this.name);
  },
};

// Accessing properties
console.log(person.name); // "John"
console.log(person["age"]); // 30

// Adding/updating properties
person.job = "Developer";
person.age = 31;

// Deleting properties
delete person.job;

// Iterating over properties
for (let key in person) {
  console.log(key + ": " + person[key]);
}

// Method
person.greet(); // "Hello, my name is John"

## Finding the median in an array 
o find the median of an array using a function in JavaScript, you can follow these steps:

    Sort the array.
    Determine if the array length is odd or even.
    If odd, return the middle element.
    If even, return the average of the two middle elements.

    const median = function(arr) {
  // Step 1: Sort the array
  let sorted = arr.slice().sort((a, b) => a - b);

  // Step 2: Calculate the middle index
  let mid = Math.floor(sorted.length / 2);

  // Step 3: Determine if the array length is odd or even
  if (sorted.length % 2 === 0) {
    // Step 4: If even, return the average of the two middle elements
    return (sorted[mid - 1] + sorted[mid]) / 2;
  } else {
    // Step 5: If odd, return the middle element
    return sorted[mid];
  }
};

// Example usage:
console.log(median([6, 2, 3, 4, 9, 6, 1, 0, 5])); // Output: 4
console.log(median([1, 2, 3, 4, 5])); // Output: 3
console.log(median([1, 2, 3, 4, 5, 6])); // Output: 3.5




## ARROW FUNCTIONS

// Arrow function with no parameters
const sayHello = () => console.log("Hello!");

// Arrow function with one parameter
const double = (n) => n * 2;object
  return result;
};
##  USING ARROW FUNCTION TO ACCESS OBJECT
const people = [
  { name: 'Alice', age: 25 },
  { name: 'Bob', age: 30 },
  { name: 'Charlie', age: 35 }
];

const adults = people.filter(person => person.age >= 30);

console.log(adults); 
// Output: [ { name: 'Bob', age: 30 }, { name: 'Charlie', age: 35 } ]



## ES6 FEATURES

// Template literals
let name = "Alice";
console.log(`Hello, ${name}!`); // "Hello, Alice!"

// Destructuring
    If odd, return the middle element.
    If even, return the average of the two middle elements.

    const median = function(arr) {
  // Step 1: Sort the array
  let sorted = arr.slice().sort((a, b) => a - b);
  ame: "Bob", age: 25 };
let { name, age } = person;
console.log(name, age); // "Bob" 25

let arr = [1, 2, 3];
let [first, second, third] = arr;
console.log(first, second, third); // 1 2 3

// Default parameters
function greet(name = "Guest") {
  console.log(`Hello, ${name}!`);
}
greet(); // "Hello, Guest!"

// Spread operator
let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];
console.log(arr2); // [1, 2, 3, 4, 5]

let obj1 = { a: 1, b: 2 };
let obj2 = { ...obj1, c: 3 };
console.log(obj2); // { a: 1, b: 2, c: 3 }

// Rest parameters
function sum(...nums) {
  return nums.reduce((acc, num) => acc + num, 0);
}
console.log(sum(1, 2, 3)); // 6

// Classes
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

let alice = new Person("Alice", 30);
alice.greet(); // "Hello, my name is Alice"

## PROMISES - Provide a more structured approach to handling asynchronous operations and avoid callback hell.

// Creating a promise
const myPromise = new Promise((resolve, reject) => {
  let success = true; // Change to false to see the reject case
  if (success) {
    resolve("Promise resolved!");
  } else {
    reject("Promise rejected!");
  }
});

// Handling a promise
myPromise
  .then((message) => {
    console.log(message); // "Promise resolved!"
  })
  .catch((error) => {
    console.log(error); // "Promise rejected!"
  });


## ASYNC/AWAIT - Built on promises, providing a cleaner and more readable way to write asynchronous code.

// Async function
async function fetchData() {
  try {
    let response = await fetch("https://api.example.com/data");
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}

fetchData();


## MODULES

// Exporting a function (export.js)
export const greet = (name) => {
  console.log(`Hello, ${name}!`);
};

// Importing a function (import.js)
import { greet } from './export.js';
greet('Alice'); // "Hello, Alice!"

## Accessing objects 

# Creating Objects
const person = {
  name: "John",
  age: 30,
  city: "New York"
};

# Using the new Object() Syntax:
const person = new Object();
person.name = "John";
person.age = 30;
person.city = "New York";

# Accessing Object Properties

Dot Notation:

console.log(person.name); // Output: John
console.log(person.age);  // Output: 30

# Bracket Notation:

console.log(person["name"]); // Output: John
console.log(person["age"]);  // Output: 30


# Adding or Modifying Properties

Dot Notation:
person.name = "Jane";  // Modifying an existing property
person.gender = "male"; // Adding a new property

# Bracket Notation:

person["name"] = "Jane"; // Modifying an existing property
person["gender"] = "male"; // Adding a new property


# Deleting Properties

delete person.age;
console.log(person.age); // Output: undefined

# Accessing Nested Objects

const student = {
  name: "Alice",
  age: 22,
  address: {
    city: "Seattle",
    state: "WA"
  }
};

console.log(student.address.city); // Output: Seattle
console.log(student["address"]["state"]); // Output: WA


# Iterating Over Properties objects

Using for...in Loop:

for (let key in person) {
  if (person.hasOwnProperty(key)) {
    console.log(key + ": " + person[key]);
  }
}
// Output:
// name: Jane
// city: New York
// gender: male
 
 # Using Object.keys():

 Object.keys(person).forEach(key => {
  console.log(key + ": " + person[key]);
});
// Output:
// name: Jane
// city: New York
// gender: male


## Using Object.entries():

Object.entries(person).forEach(([key, value]) => {
  console.log(key + ": " + value);
});
// Output:
// name: Jane
// city: New York
// gender: male


## Checking for Property Existence

Using in Operator:

console.log("name" in person); // Output: true
console.log("age" in person);  // Output: false


## Using hasOwnProperty() Method:

console.log(person.hasOwnProperty("name")); // Output: true
console.log(person.hasOwnProperty("age"));  // Output: false

## Using Spread Operator (...):

const copiedPerson = { ...person };

## Merging Objects

Using Object.assign():
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };
const returnedTarget = Object.assign(target, source);

console.log(target); // Output: { a: 1, b: 4, c: 5 }
console.log(returnedTarget); // Output: { a: 1, b: 4, c: 5 }


#  Using Spread Operator (...):
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };
const merged = { ...target, ...source };

console.log(merged); // Output: { a: 1, b: 4, c: 5 }

## METHODS

Methods are actions that can be performed on objects. They are stored as function properties.

    let person = {
        firstName: "John",
        lastName : "Doe",
        fullName : function() {
            // 'this' refers to the 'person' object
            return this.firstName + " " + this.lastName;
        }
    };
    
    console.log(person.fullName()); // Outputs: John Doe

 # The `this` keyword in JavaScript refers to the "owner" of the function, or the object where the function is a method. In the `fullName` method above, `this` refers to the `person` object. 

 # Built-in Methods - JavaScript has several built-in methods available for different types of data:
 
 # Strings -
      let str = "Hello, world!";
      let result = str.toUpperCase(); // Converts the string to uppercase
      console.log(result); // Outputs: HELLO, WORLD!

  # Arrays -
        let arr = ['Apple', 'Banana', 'Mango'];
      let result = arr.join(', '); // Combines the array elements into a string
      console.log(result); // Outputs: Apple, Banana, Mango

 # Numbers -
     let num = 3.14159;
    let result = num.toFixed(2); // Formats the number to use 2 decimal places
    console.log(result); // Outputs: 3.14

  # The prototype Property - JavaScript methods can also be added to objects via the prototype property. This allows you to add new methods to constructor functions:
     function Person(first, last, age) {
      this.firstName = first;
      this.lastName = last;
      this.age = age;
    }
    
    // Add a fullName method to the Person constructor
    Person.prototype.fullName = function() {
      return this.firstName + " " + this.lastName;
    };
    
    var myFriend = new Person("Bill", "Gates", 63);
    console.log(myFriend.fullName()); // Outputs: Bill Gates

## RECURSION - Recursion is an alternative to traditional looping that allows you to do the same thing, just in a slightly different way. Recursion isn't necessarily a better way of doing this, it's just a different way of doing this. # Any problem that you can solve with a for loop, you can solve with recursion, and vice versa.
 
 compass example: 

 function countEvenToTwelve(num) {
  if (num <= 12) {
    console.log(num);
    countEvenToTwelve(num + 2);
  }
 }
 countEvenToTwelve(0);
 ## Wow! What's going on here?

 ## On line 505 this function is calling itself! That's bad right? Won't that crash my program?

 ## Nope! That's recursion in a nutshell: A function that calls itself until it doesn't.

 ##  Let me explain. A recursive function will call itself to execute code over and over again, kind of like a loop. And like a loop, it has to stop calling itself at some point so that it doesn't keep repeating forever.

 ## As long as number <= 12, the function continues to call itself to repeat the code over and over again. As soon as number > 12, the function stops calling itself and the "looping" ends.

 ## Each time countEvenToTwelve calls itself, on line 4, it passes in a different input value. In this case, each time the function is called, number will be 2 more than it was the last time. So the first time the function is called, number is equal to 0. The second time it's called, number is equal to 2, and so on. Instead of incrementing the number directly, like in the loop, the function calls itself again with a modified input parameter. Every time the function calls itself, number gets bigger and bigger. This is important, because the function will only stop calling itself when number is greater than 12.


 ## This concept of a function calling itself inside itself can seem a little weird and jarring at first. If you've ever done this accidentally, your app probably crashed. How come this works? Why doesn't the function call itself forever?

 ## Every recursive function must stop calling itself at some point, otherwise it will just continue to call itself forever, like an infinite loop. The following function never stops calling itself.
 Recursion is a tool you can use as an alternative to traditional iteration using for and while loops.

    Every recursive function must have a base case and a recursive case.
    Each recursive call should break down the current problem into a smaller, simpler one.
    The recursive calls must eventually reach the smallest version of the problem, the base case.
    The base case is when the problem can be solved without further recursion.

