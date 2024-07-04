## Array: An ordered collection of elements, which can be accessed by their index.
let arr = [1, 2, 3];

# TCP - which stands for Transmission Control Protocol, provides a standard that allows machines to speak to each other. 
TCP based communication allows two machines to establish an open channel for two-way data communication. Once a connection is established, both parties can start sending and receiving data until one of them decides that it's had enough and decides to terminate the connection. Sounds a lot like calling family, doesn't it? In fact, the easiest comparable analogy would actually be a phone call.

## Arrow Function: A shorthand way to write functions using the => syntax.
const add = (a, b) => a + b;

## JSON is a data format that underpins many modern web services. It stands for JavaScript Object Notation, and it's actually a subset of the JavaScript language.

    JSON is built on two structures:

        A collection of name/value pairs.
        An ordered list of values.

    These are universal data structures. Virtually all modern programming languages support them in one form or another. It makes sense that a data format that is interchangeable with programming languages also be based on these structures.

 ## JSON Serialization The process of serialization converts objects (or data structures) into a format that can be stored or transmitted between computers (typically as a string of text). The opposite, going from String → Object is called deserialization.

In JavaScript, we have the JSON object for serializing and deserializing. The Mozilla Developer Network (MDN) provides good documentation on these two important methods:

## JSON.parse()
 
     Parse a string as JSON, optionally transform the produced value and its properties, and return the value.
try in node
     example:
     <!-- const jsonString = '{"a":1, "b":2, "foo":"bar"}';
     const obj = JSON.parse(jsonString); -->

     <!-- Modify an object - 
     delete obj.foo;
     obj -->

     Serialize it back to a string:
     <!-- JSON.stringify(obj);  -->

## JSON.stringify() 
Return a JSON string corresponding to the specified value, optionally including only certain properties or replacing property values in a user-defined manner.



## URL - Uniform Resource Locator

## NEEDLE
const needle = require('needle');
needle.get('http://www.google.com', (error, response, body) => {
  console.log('error:', error); // Print the error if one occurred
  console.log('statusCode:', response && response.statusCode); // Print the response status code if a response was received
  console.log('body:', body); // Print the HTML for the Google homepage.
});


## HTTP - Scheme

The first part of the URL is the scheme, which indicates the protocol that the browser must use to request the resource (a protocol is a set method for exchanging or transferring data around a computer network). Usually for websites the protocol is HTTPS or HTTP (its unsecured version). Addressing web pages requires one of these two, but browsers also know how to handle other schemes such as mailto: (to open a mail client), so don't be surprised if you see other protocols.

## HTTP AUTHORITY
Next follows the authority, which is separated from the scheme by the character pattern ://. If present the authority includes both the domain (e.g. www.example.com) and the port (80), separated by a colon:

    The domain indicates which Web server is being requested. Usually this is a domain name, but an IP address may also be used (but this is rare as it is much less convenient).
    The port indicates the technical "gate" used to access the resources on the web server. It is usually omitted if the web server uses the standard ports of the HTTP protocol (80 for HTTP and 443 for HTTPS) to grant access to its resources. Otherwise it is mandatory.

## HTTP - PAth to resource
/path/to/myfile.html is the path to the resource on the Web server. In the early days of the Web, a path like this represented a physical file location on the Web server. Nowadays, it is mostly an abstraction handled by Web servers without any physical reality.

## HTTP - Parameters
?key1=value1&key2=value2 are extra parameters provided to the Web server. Those parameters are a list of key/value pairs separated with the & symbol. The Web server can use those parameters to do extra stuff before returning the resource. Each Web server has its own rules regarding parameters, and the only reliable way to know if a specific Web server is handling parameters is by asking the Web server owner.

## HTTP Anchor
#SomewhereInTheDocument is an anchor to another part of the resource itself. An anchor represents a sort of "bookmark" inside the resource, giving the browser the directions to show the content located at that "bookmarked" spot. On an HTML document, for example, the browser will scroll to the point where the anchor is defined; on a video or audio document, the browser will try to go to the time the anchor represents. It is worth noting that the part after the #, also known as the fragment identifier, is never sent to the server with the request.

## HTTP - Responses
When a server receives a request from a client, it reads the path and method to figure out what it should do. For example, if the request it receives is something like GET /dogs the server may try to fetch and return all of the data about dogs that it has.
1.200: "Everything went great!"
2.201: "The request has succeeded and a new resource has been created as a result."
3.404: "Resource was not found."
4.500: "The server had an error."
5. 451: , a status code that indicates that the user requested a resource that is not available due to legal reasons.

## HTTP HEADERS

As we mentioned earlier, HTTP requests and responses are made up of lots of components. However, you only need to worry about a few of them right now. For the requests, it's enough to understand the path and method. For the responses, you only need to consider the status code and body. Both requests and responses also let a programmer inject extra information into them as "headers", which is a key-value way of storing data in a request or response. There are many reasons for why we would add headers, but we won't explore that until next week's project.
After the server has tried to perform the requested action, it sends a response back to the client. The response contains all kinds of useful information, but we'll look at two important bits here:

## HTTP Response Body\

The response will also usually contain some data, such as the data the client originally requested. This data is stored in a part of the response which is called the body. The body may store data in many kinds of formats, such as text and images. For our purposes, the body will often contain webpages (HTML) or data encoded in JSON, which we'll learn about later on.



## HTTP is a protocol used to read and write "resources" (data) in a simple text-based manner. It started off as being mostly used for HTML documents, but today it's used for all sorts of documents, like JavaScript files, CSS, and anything else that our browser is capable of downloading (PDFs, etc.). 
When a client wants to communicate with a server, either the final server or an intermediate proxy, it performs the following steps:

    1. Open a TCP connection: The TCP connection is used to send a request, or several, and receive an answer. The client may open a new connection, reuse an existing connection, or open several TCP connections to the servers.
 1.  
    2. Send an HTTP message: HTTP messages (before HTTP/2) are human-readable. With HTTP/2, these simple messages are encapsulated in frames, making them impossible to read directly, but the principle remains the same. For example: 
    
    3.Read the response sent by the server

    4. Close or reuse the connection for further requests

## HTTP Methods -
1.GET: used to "get" some data from the server
2.POST: usually used to create some new data
3.PUT: generally used for editing exisitng data on the server
4.DELETE: used to delete some existing data

## HTTP FLOW - HTTP is a request-response based protocol. A client makes a request to an HTTP server, immediately also sending a message asking for a specific resource, which the server sends down as a response. A server cannot send a response to a client if the client has not first sent a request.

## HTTP 
    Caching: How documents are cached can be controlled by HTTP. The server can instruct proxies and clients about what to cache and for how long. The client can instruct intermediate cache proxies to ignore the stored document.
    Relaxing the origin constraint: To prevent snooping and other privacy invasions, Web browsers enforce strict separation between websites. Only pages from the same origin can access all the information of a Web page. Though such a constraint is a burden to the server, HTTP headers can relax this strict separation on the server side, allowing a document to become a patchwork of information sourced from different domains; there could even be security-related reasons to do so.
    Authentication: Some pages may be protected so that only specific users can access them. Basic authentication may be provided by HTTP, either using the WWW-Authenticate and similar headers, or by setting a specific session using HTTP cookies.
    Proxy and tunneling: Servers or clients are often located on intranets and hide their true IP address from other computers. HTTP requests then go through proxies to cross this network barrier. Not all proxies are HTTP proxies. The SOCKS protocol, for example, operates at a lower level. Other protocols, like ftp, can be handled by these proxies.
    Sessions: Using HTTP cookies allows you to link requests with the state of the server. This creates sessions, despite basic HTTP being a state-less protocol. This is useful not only for e-commerce shopping baskets, but also for any site allowing user configuration of the output.


## Boolean: A data type with two possible values: true and false.

let isTrue = true;

## Callback Function: A function passed as an argument to another function, which is executed after some operation has been completed.
# A callback function is a function that is passed as an argument to another function, to be “called back” at a later time. A function that accepts other functions as arguments is called a higher-order function, which contains the logic for when the callback function gets executed. It’s the combination of these two that allow us to extend our functionality.
function greet(name, callback) {
  console.log('Hello, ' + name);
  callback();
}

function createQuote(quote, callback){ 
  var myQuote = "Like I always say, " + quote;
  callback(myQuote); // 2
}

function logQuote(quote){
  console.log(quote);
}

createQuote("eat your vegetables!", logQuote); // 1


## Class: A blueprint for creating objects with predefined properties and methods.
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}


## Closure: A feature where an inner function has access to variables in its outer scope, even after the outer function has finished executing.
function outer() {
  let outerVar = 'I am outside!';
  function inner() {
    console.log(outerVar);
  }
  return inner;
}


# Destructuring: A syntax for extracting values from arrays or objects into distinct variables.

let [a, b] = [1, 2]; // Array destructuring
let {name, age} = {name: 'Alice', age: 25}; // Object destructuring


## Event: An action or occurrence recognized by software, often generated by user interactions like clicks, key presses, etc.

element.addEventListener('click', function() {
  console.log('Element clicked!');
});


## Fetch API: An interface for making HTTP requests in web browsers.

fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data));


## Function Expression: A way to define a function within an expression.

const add = function(a, b) {
  return a + b;
};


## Hoisting: JavaScript's default behavior of moving declarations to the top of the current scope.

(function() {
  console.log('IIFE!');
})();


## Immediately Invoked Function Expression (IIFE): A function that is executed immediately after its definition.

(function() {
  console.log('IIFE!');
})();


## Import/Export: Keywords used to import and export modules in JavaScript.

Import/Export: Keywords used to import and export modules in JavaScript.

## JSON (JavaScript Object Notation): A lightweight data-interchange format that is easy for humans to read and write, and easy for machines to parse and generate.

let obj = {name: 'Alice', age: 25};
let jsonString = JSON.stringify(obj);
let jsonObj = JSON.parse(jsonString);


## Let: A keyword used to declare a block-scoped variable.

let x = 10;


## Map: An array method that creates a new array with the results of calling a provided function on every element in the array.

let arr = [1, 2, 3];
let doubled = arr.map(num => num * 2); // [2, 4, 6]


## Object: A collection of key-value pairs. Object-Oriented Programming (OOP): A programming paradigm based on the concept of objects, which can contain data and methods.

let obj = {name: 'Alice', age: 25};



## Promise: An object representing the eventual completion or failure of an asynchronous operation.

let promise = new Promise((resolve, reject) => {
  // Async operation
});

## Rest Parameters: Allows a function to accept an indefinite number of arguments as an array.

function sum(...nums) {
  return nums.reduce((acc, num) => acc + num, 0);
}


## Spread Operator: Expands an array or object into individual elements

let arr = [1, 2, 3];
let newArr = [...arr, 4, 5]; // [1, 2, 3, 4, 5]

let obj = {a: 1, b: 2};
let newObj = {...obj, c: 3}; // {a: 1, b: 2, c: 3}


##  Template Literals: String literals allowing embedded expressions.

let name = 'Alice';
let greeting = `Hello, ${name}!`;


## This: A keyword referring to the current execution context.

function greet() {
  console.log(this.name);
}

## Var: A keyword used to declare a variable with function scope.

var x = 10;


## While Loop: A control flow statement that allows code to be executed repeatedly based on a given boolean condition.

While Loop: A control flow statement that allows code to be executed repeatedly based on a given boolean condition.

## Yield: A keyword used in generator functions to pause and resume their execution.

function* generator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = generator();
console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
console.log(gen.next().value); // 3


## Automated Testing
Automated testing is the practice of writing code to programmatically test the actual code we want to write.

It offers several benefits over manual testing:

    it saves testing time (by not having to perform manual tests over and over)
    it saves debugging time (by catching bugs earlier)
    it makes it easier to program (because we don't need to keep the entire application in our heads, just the part that we're working on... if we break something, our tests will let us know)
    it makes it easier to come back to a program after some time (programmers forget things, but tests do not)
    it makes it easier to work together (we wrote some widget and know how it works, but our team-mates probably don't; our tests will catch bugs introduced by others on our team, and vice versa)
    it acts as documentation (readings tests is a great way to learn about how code is meant to be used)
    it improves the quality of our code (writing code that is easy to test often requires us to change how our code is structured -- for the better)


## Unit Testing
We've been writing assertions for some of our code, so let's take some time to talk about automated testing more formally.

Writing automated tests for our code is an incredibly powerful programming practice that allows us to benefit from code that is more reliable and easy to refactor, and requires us to spend less time debugging. In this reading, we are going to take a quick look at why testing is useful, and what an automated test actually is.

In short, we will:

    understand what unit tests are.
    understand why unit tests are useful and important.


## BDD Behavior Driven Development
BDD or Behavior Driven Development is a process that emerged from test-driven development in 2006. The topic of BDD covers the entire life cycle of the app development process, from planning the project to writing the code.

BDD encourages you to specify the behaviour of your app in terms of user stories which are broken down into scenarios that can be built and tested.

The Topic of BDD is big enough that entire books have been written on the subject, but for today, we're just interested in one part of BDD, testing with BDD frameworks.

## Mocha vs Chai
Mocha gives us the describe and it functions. Each it is a test, and each test should have at least one assertion.

Chai is an assertion library. It gives us assertion functions so that we no longer have to use our assertEqual and other assertion functions that we implemented previously. Chai assertion functions are deliberately designed to play nice with testing frameworks like Mocha.
