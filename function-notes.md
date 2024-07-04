
## Basic Function 
1.Function Keyword: Use the function keyword to declare a function.
2.Function Name: Provide a name for the function, e.g., greet.
3.Parameters: Inside parentheses (), define any parameters the function takes, e.g., name.
4.Function Body: Inside curly braces {}, write the code that the function will execute. This can include statements, expressions, and a return statement if the function returns a value.
<!-- 
const greet = (greet) => {
  return "Hello, " + name + "!"
} -->
<!-- console.log(greet("Alice")); // Output: Hello, Alice! -->


## Function Expression
1.Assign to Variable: Assign an anonymous function to a variable, e.g., add.
2.Function Keyword: Use the function keyword to define the function.
3.Parameters and Body: Define the parameters and function body as usual.

<!-- const add = function(a, b) {
  return a + b;
};
console.log(add(5, 3)); // Output: 8 -->

## Arrow Functions
1.Assign to Variable: Assign an arrow function to a variable, e.g., multiply.
2.Arrow Syntax: Use the arrow => to separate the parameter list from the function body.
3.Parameters and Body: Define the parameters and function body. For single expressions, you can omit the curly braces and the return keyword.

<!-- const multiply = (a, b) => {
  return a + b;
};
console.log(multiply(4, 2)); // Output: 8 -->


## Immediately Invoked Function Expression (IIFE)
1.Define Function: Wrap a function declaration in parentheses.
2.Invoke Immediately: Follow the function declaration with another set of parentheses () to immediately invoke the function.

<!-- (function() {
  console.log("This function runs immediately!");
})(); -->


## Function with Default Parameters
1. Default Parameters: Assign default values to parameters directly in the parameter list.
2.Function Body: Define the function body as usual.

<!-- function greet(name = "Guest") {
  return "Hello, " + name + "!";
} -->
<!-- console.log(greet()); // Output: Hello, Guest!
console.log(greet("Alice")); // Output: Hello, Alice! -->

## Maps method
1. The .map() method creates a new array populated with the results of calling a provided function on every element in the calling array.

Syntax:

array.map(callback(element, index, array), thisArg);

Parameters:
1.callback: Function that is called for every element of the array. Each time callback executes, the returned value is added to the new array.
2.element: The current element being processed in the array.
3.index (optional): The index of the current element being processed.
4.array (optional): The array map was called upon.
5.thisArg (optional): Value to use as this when executing callback.

Example:
<!-- const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(number => number * 2);
console.log(doubled); // Output: [2, 4, 6, 8, 10] -->

## Reduce Method
The .reduce() method executes a reducer function (that you provide) on each element of the array, resulting in a single output value.

Syntax:
<!-- array.reduce(callback(accumulator, currentValue, index, array), initialValue); -->

Parameters:

    callback: Function to execute on each element in the array.

        accumulator: Accumulates the callback's return values. It is the accumulated value previously returned in the last invocation of the callback.

        currentValue: The current element being processed in the array.

        index (optional): The index of the current element being processed.

        array (optional): The array reduce was called upon.

    initialValue (optional): A value to use as the first argument to the first call of the callback. If no initial value is supplied, the first element in the array will be used and skipped.

Example:

<!-- const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
console.log(sum); // Output: 15 -->

## Filter Method

The .filter() method creates a new array with all elements that pass the test implemented by the provided function.

Syntax:
<!-- array.filter(callback(element, index, array), thisArg); -->

Parameters:

    callback: Function that is called for every element of the array. Each time callback returns a truthy value, the current element will be included in the new array.

        element: The current element being processed in the array.

        index (optional): The index of the current element being processed.

        array (optional): The array filter was called upon.

    thisArg (optional): Value to use as this when executing callback.

    Example:

    const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter(number => number % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]

## Summery

.map(): Transforms each element in an array to produce a new array of the same length.

    Use Case: Modifying each element, e.g., converting an array of numbers to their squares.

.reduce(): Reduces the array to a single value by accumulating results.

    Use Case: Summing all numbers in an array.

.filter(): Creates a new array with elements that pass a test.

    Use Case: Filtering out certain elements, e.g., finding all even numbers in an array.