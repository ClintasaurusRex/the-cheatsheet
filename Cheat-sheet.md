
# JavaScript Basics and Advanced Concepts

## pythontutor.com

### BASICS

#### Variable declaration
```javascript
let x = 10;
const y = 20;
var z = 30; // var is function-scoped, let and const are block-scoped

## Data types

let number = 42;               // Number
let string = "Hello, world!";  // String
let boolean = true;            // Boolean
let array = [1, 2, 3];         // Array
let object = { key: "value" }; // Object
let undefinedVar;              // Undefined
let nullVar = null;            // Null

## String Manipulation:

Concatenation - Combining multiple strings into one.

## Substring Extraction - Extracting a portion of a string.

    slice(start, end): Extracts a section of a string and returns it as a new string.

    let str = "Hello, world!";
    let sliceStr = str.slice(0, 5);        // "Hello"

    substring(start, end): Similar to slice, but does not accept negative indices.

    let substringStr = str.substring(0, 5);// "Hello"
    let substrStr = str.substr(0, 5);      // "Hello"


    substr(start, length): Extracts a substring starting from start of length length.

## Changing Case - Convert to upper or lower case.

let upperStr = str.toUpperCase();  // "HELLO, WORLD!"
let lowerStr = str.toLowerCase();  // "hello, world!"


## Trimming - Removing whitespace from the beginning and end of a string.

    trim(): Removes whitespace from both ends of a string.

    let trimStr = "  Hello, world!  ";
    let trimmedStr = trimStr.trim();      // "Hello, world!"

    trimStart() / trimLeft(): Removes whitespace from the beginning.

  let trimmedStartStr = trimStr.trimStart(); // "Hello, world!  "
  
  trimEnd() / trimRight(): Removes whitespace from the end.

  let trimmedEndStr = trimStr.trimEnd();     // "  Hello, world!"

## #Replacing Substrings - Replacing parts of a string with another string.

let str = "Hello World";
let newStr = str.replace("World", "Universe");  // "Hello Universe"
let newStrAll = str.replaceAll("o", "O");       // "HellO WOrld"


    replace(searchValue, newValue): Replaces the first occurrence of searchValue with newValue.

let str = "Hello World";
let newStr = str.replace("World", "Universe");  // "Hello Universe"
let newStrAll = str.replaceAll("o", "O");  // "HellO WOrld"

    replaceAll(searchValue, newValue): Replaces all occurrences of searchValue with newValue.


## Splitting and Joining - Splitting a string into an array and joining an array into a string.

let str = "Hello World";
let arr = str.split(" ");  // ["Hello", "World"]
let joined = arr.join(" ");  // "Hello World"

## Searching - Finding the position of a substring or checking for its existence.

let str = "Hello World";
let position = str.indexOf("World");  // 6
let lastPosition = str.lastIndexOf("o");  // 7
let contains = str.includes("Hello");  // true


## Function Decleration----------------------------------------------------------------------

A function declaration is a way to define a function using the function keyword. The function is declared with a name, and it can be called by that name within the scope it was defined.
Characteristics:

    Hoisting: Function declarations are hoisted to the top of their containing scope, meaning they can be called before they are defined in the code.
    Naming: Function declarations must have a name.

// Function declaration
function add(a, b) {
  return a + b;
}

console.log(add(2, 3)); // Output: 5


## Function expression-----------------------------------------------------------------------

Function Expression

A function expression involves creating a function and assigning it to a variable. The function can be anonymous (without a name) or named.
Characteristics:

    Not Hoisted: Function expressions are not hoisted, so they cannot be called before they are defined in the code.
    Flexibility: Can be anonymous or named, and can be used as arguments to other functions or assigned to object properties.

    const functionName = function(parameters) {
  // function body
};

// Function expression
const subtract = function(a, b) {
  return a - b;
};

console.log(subtract(5, 2)); // Output: 3

In this example, the subtract function is defined using a function expression and assigned to the variable subtract. It can only be called after the assignment.
Key Differences

    Hoisting:
        Function declarations are hoisted.
        Function expressions are not hoisted.

    Naming:
        Function declarations must have a name.
        Function expressions can be anonymous or named.

    Usage:
        Function declarations are more suitable when defining standard functions that are used throughout the code.
        Function expressions are useful when defining functions in a more dynamic or inline manner, such as callbacks.

## Example to Illustrate Hoisting------------------

// Using function declaration before it's defined
console.log(multiply(2, 3)); // Output: 6

function multiply(a, b) {
  return a * b;
}

// Using function expression before it's defined
console.log(divide(6, 2)); // Error: divide is not a function

const divide = function(a, b) {
  return a / b;
};
Sure! Here’s an explanation of function declarations and function expressions in JavaScript, with examples.
Function Declaration

A function declaration is a way to define a function using the function keyword. The function is declared with a name, and it can be called by that name within the scope it was defined.
Characteristics:

    Hoisting: Function declarations are hoisted to the top of their containing scope, meaning they can be called before they are defined in the code.
    Naming: Function declarations must have a name.

Syntax:

javascript

function functionName(parameters) {
  // function body
}

Example:

javascript

// Function declaration
function add(a, b) {
  return a + b;
}

console.log(add(2, 3)); // Output: 5

In this example, the add function is defined using a function declaration. It can be called before or after its declaration in the code because it is hoisted.
Function Expression

A function expression involves creating a function and assigning it to a variable. The function can be anonymous (without a name) or named.
Characteristics:

    Not Hoisted: Function expressions are not hoisted, so they cannot be called before they are defined in the code.
    Flexibility: Can be anonymous or named, and can be used as arguments to other functions or assigned to object properties.

Syntax:

javascript

const functionName = function(parameters) {
  // function body
};

Example:

javascript

// Function expression
const subtract = function(a, b) {
  return a - b;
};

console.log(subtract(5, 2)); // Output: 3

In this example, the subtract function is defined using a function expression and assigned to the variable subtract. It can only be called after the assignment.
Key Differences

    Hoisting:
        Function declarations are hoisted.
        Function expressions are not hoisted.

    Naming:
        Function declarations must have a name.
        Function expressions can be anonymous or named.

    Usage:
        Function declarations are more suitable when defining standard functions that are used throughout the code.
        Function expressions are useful when defining functions in a more dynamic or inline manner, such as callbacks.

Example to Illustrate Hoisting

javascript

// Using function declaration before it's defined
console.log(multiply(2, 3)); // Output: 6

function multiply(a, b) {
  return a * b;
}

// Using function expression before it's defined
console.log(divide(6, 2)); // Error: divide is not a function

const divide = function(a, b) {
  return a / b;
};

In this example:

    The multiply function works even when called before its declaration due to hoisting.
    The divide function causes an error when called before its definition because function expressions are not hoisted.

Understanding these differences helps in choosing the appropriate function definition method based on the needs of your code.

## Arrow function

const multiply = (a, b) => a * b;

## Arrow function with one parameter

const double = (n) => n * 2;

## Using arrow function to access object

const people = [
  { name: 'Alice', age: 25 },
  { name: 'Bob', age: 30 },
  { name: 'Charlie', age: 35 }
];

const adults = people.filter(person => person.age >= 30);

console.log(adults); 
// Output: [ { name: 'Bob', age: 30 }, { name: 'Charlie', age: 35 } ]


## Callback function

function greet(name, callback) {
  console.log("Hello, " + name);
  callback();
}

greet("Alice", () => console.log("Welcome!"));

## Callback Functions in JavaScript

A callback function is a function that is passed as an argument to another function and is executed after some operation has been completed. Callbacks are a way to ensure that certain code doesn’t execute until another code has already finished execution. This is especially useful in asynchronous programming, such as handling events or performing network requests.
Characteristics:

    Function as an Argument: A callback is a function passed as an argument to another function.
    Executed Later: The callback is not executed immediately but rather at a later time, typically after the completion of some task.

    function greet(name, callback) {
  console.log("Hello, " + name);
  callback();
}

function showMessage() {
  console.log("Welcome!");
}

greet("Alice", showMessage);

// Output:
// Hello, Alice
// Welcome!

## Control Flow ------------------------------------------------
If-else

if (x > y) {
  console.log("x is greater than y");
} else if (x < y) {
  console.log("x is less than y");
} else {
  console.log("x is equal to y");
}

Switch-case


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

For loop

for (let i = 0; i < 5; i++) {
  console.log(i);
}

While loop


let count = 0;
while (count < 5) {
  console.log(count);
  count++;
}

Do-while loop

do {
  console.log(count);
  count++;
} while (count < 5);

## Creating and Accessing elements

let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // "apple"

## Adding elements

fruits.push("date"); // ["apple", "banana", "cherry", "date"]


## Removing elements

fruits.pop(); // ["apple", "banana", "cherry"]
fruits.shift(); // ["banana", "cherry"]
fruits.unshift("apple"); // ["apple", "banana", "cherry"]

## Iterating over arrays

fruits.forEach((fruit) => console.log(fruit));


## Mapping arrays

let upperFruits = fruits.map((fruit) => fruit.toUpperCase());
console.log(upperFruits); // ["APPLE", "BANANA", "CHERRY"]


## Filtering arrays

let total = [1, 2, 3, 4].reduce((acc, num) => acc + num, 0);
console.log(total); // 10

## Objects-----------------------------------------------------------------------------------

## Creating Objects

const person = {
  name: "John",
  age: 30,
  city: "New York",
  greet: function() {
    console.log("Hello, my name is " + this.name);
  },
};

## Accessing properties

console.log(person.name); // "John"
console.log(person["age"]); // 30


## Adding/updating properties

person.job = "Developer";
person.age = 31;


# Deleting properties

delete person.job;


## Iterating over properties

for (let key in person) {
  console.log(key + ": " + person[key]);
}

## Finding the Median in an Array

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


