
# You can see all projects in action here

[Projects](https://www.vanillajavascriptprojects.com/)

# Required apps/plugins:
- VS code
- prettier
- Live preview
- Emmet(optional: for abbrev)


# JS
[Basic Intro](#basic-intro)

[Inline Javascript](#inline-javascript)

[Internal Javascript](#internal-javascript)
External Javascript
Helper Methods
const, let, var
String Concatenation
Implicit Type Conversion


## Basic Intro<a name="1"></a>
- JavaScript (JS) is a lightweight, interpreted, or `just-in-time compiled` programming language with `first-class functions`. 
    - In computing, just-in-time (JIT) compilation (also dynamic translation or run-time compilations) is a way of executing computer code that involves compilation during execution of a program (at run time) rather than before execution.
    - First-class functions means when functions in that language are treated like any other variable. For example, in such a language, a function can be passed as an argument to other functions, can be returned by another function and can be assigned as a value to a variable.

- JavaScript is a `prototype-based, multi-paradigm, single-threaded, dynamic language, supporting object-oriented, imperative, and declarative` (e.g. functional programming) styles.
    - Prototype-based programming is a style of object-oriented programming in which classes are not explicitly defined, but rather derived by adding properties and methods to an instance of another class or, less frequently, adding them to an empty object.
    - In multi-paradigm, one can write code in procedural, object oriented, functional or imperative manner.
    - JavaScript is an asynchronous and concurrent programming language. It's single-threaded like sync, but also non-blocking like async.
        - So at its base, JavaScript is a synchronous language. This means that code in JavaScript runs in a particular sequence of instructions given in the program. However, JavaScript also has non-blocking and asynchronous features, which allow it to handle multiple tasks and events simultaneously without waiting for previous operations to complete. 
        - So while JavaScript may be synchronous at its core, it does have the ability to work in an asynchronous and non-blocking manner when needed.
        - It's not possible for a programming construct to be both single-threaded like synchronous code and non-blocking like asynchronous code, as these two concepts are fundamentally opposed to each other.
        - However, there is a technique called "event-driven programming" that can give the impression of being both single-threaded and non-blocking. 
        - Event-driven programming is a programming paradigm where the program responds to events, such as user input or network activity, by executing event handlers. In this model, the program is single-threaded, meaning that only one event handler can be executing at a time. However, the program is also non-blocking because event handlers are typically short-lived and don't block the execution of the program.
    - JavaScript is a dynamically typed and loosely typed language, meaning that it doesn't require variable types to be declared explicitly, and the type of a variable can change at runtime. 
    - Imperative code focuses on writing an explicit sequence of commands to describe how you want the computer to do things, and declarative code focuses on specifying the result of what you want.
- The JavaScript code can interact with the HTML document's structure, manipulate the DOM (Document Object Model), and add dynamic behavior to the web page.
## Inline Javascript<a name="2"></a>
- Inline JavaScript refers to the practice of embedding JavaScript code directly into HTML markup. 
- While this approach can be convenient, it can also make code difficult to maintain and debug.
- When you include JavaScript code inline in an HTML file, the code is executed by the web browser as it parses the HTML file. 
- Here's a step-by-step overview of how inline JavaScript works:
    1. The web browser parses the HTML file and encounters the inline JavaScript code.
    2. The browser creates a global execution context for the JavaScript code.
    3. The JavaScript code is executed in the context of the current document, meaning that it has access to the document object and can manipulate the DOM.
    4. As the JavaScript code executes, it can create and manipulate HTML elements, modify the text of existing elements, and respond to user events like button clicks.
    5. Once the JavaScript code has finished executing, the browser continues parsing the HTML file and rendering the web page.
Example
        ```js
        <!DOCTYPE html>
        <html>
        <head>
            <title>Inline JavaScript Example</title>
        </head>
        <body>
            <h1>Inline JavaScript Example</h1>
            <button onclick="alert('Hello, world!')">Click me</button>
        </body>
        
        </html>
        ```

- Best Practices:
    - Avoid inline scripts for larger scripts
    - Avoid using inline event handlers: While it's technically possible to use inline event handlers, it's generally considered bad practice. Instead, use the addEventListener method to bind event handlers to elements.
    - Consider performance: Inline scripts can impact the performance of your web page, especially if you have many of them. To minimize this impact, make sure that your code is well-optimized and try to avoid excessive DOM manipulation.
- Exrta: https://stackoverflow.com/questions/10607847/how-does-inline-javascript-in-html-work/10607992#10607992


## Internal Javascript 
- Internal JavaScript, also known as embedded JavaScript, refers to JavaScript code that is included in the <script> tags within an HTML file. 
- The code is placed within the ```<head>``` or ```<body>``` section of the HTML document, and it's executed by the web browser as it loads the page.

```html
        <!DOCTYPE html>
        <html>
        <head>
            <title>Internal JavaScript Example</title>
            <script>
                function showAlert() {
                    alert('Hello, world!');
                }
            </script>
        </head>
        <body>
            <h1>Internal JavaScript Example</h1>
            <button onclick="showAlert()">Click me</button>
        </body>
        </html>
```
```html
        <!DOCTYPE html>
        <html>
        <head>
            <title>Internal JavaScript Example</title>
            <script>
                function showAlert() {
                    alert('Hello, world!');
                }
            </script>
        </head>
        <body>
            <h1>Internal JavaScript Example</h1>
            <button onclick="showAlert()">Click me</button>
            <script defer src="scripts.js"></script>
        </body>
        </html>
```
- Here are some best practices for using internal JavaScript:
    - Place the script tags at the bottom of the page: To make sure that the HTML content loads first, it's generally a good practice to place the <script> tags at the bottom of the <body> section. This allows the HTML content to be displayed to the user while the JavaScript loads and executes.
    - Keep the JavaScript code small: Since the JavaScript code is embedded directly in the HTML file, it can make the file size larger and slower to load. To avoid this, it's best to keep the JavaScript code small and focused on a specific task.
    - Minify the JavaScript code: Minifying the JavaScript code can help reduce the file size and improve performance. There are several tools available online that can minify JavaScript code, such as UglifyJS or Google Closure Compiler.
    - Use the defer or async attributes: If you need to include larger scripts, you can use the defer or async attributes on the <script> tag. The defer attribute tells the browser to load the script in the background, and execute it after the page has finished loading. The async attribute tells the browser to load the script in the background, but execute it as soon as it's downloaded, even if the rest of the page hasn't finished loading.

## External Javascript
- External JavaScript is JavaScript code that is stored in a separate file with a .js extension, and referenced in an HTML document using a <script> tag with a src attribute. Provides reusability of the code so that it can be used across multiple pages, making it easier to maintain and update the code.
- Here are some best practices for using external JavaScript:
    - Use a separate file for each module: To make it easier to manage the code and avoid conflicts.
    - Name the file appropriately: The name of the JavaScript file should reflect the functionality or purpose of the code within the file.
    - Place the script tag at the bottom of the page.
    - Minify the JavaScript code.
    - Use the defer or async attributes.

## Helper Methods

parseInt() - Converts a string to an integer. For example, parseInt('123') would return the number 123.

parseFloat() - Converts a string to a floating-point number. For example, parseFloat('3.14') would return the number 3.14.

toFixed() - Formats a number with a specified number of decimal places. For example, 123.456.toFixed(2) would return the string '123.46'.

slice() - Extracts a portion of a string and returns it as a new string. For example, 'hello world'.slice(0, 5) would return the string 'hello'.

join() - Joins the elements of an array into a string, using a specified separator. For example, ['apple', 'banana', 'orange'].join(', ') would return the string 'apple, banana, orange'.

indexOf() - Searches an array for a specified element, and returns the index of the first occurrence. For example, [1, 2, 3].indexOf(2) would return the number 1.

filter() - Creates a new array with all elements that pass a specified test. For example, [1, 2, 3, 4, 5].filter((num) => num % 2 === 0) would return the array [2, 4].

map() - Creates a new array with the results of calling a function on each element of the original array. For example, [1, 2, 3].map((num) => num * 2) would return the array [2, 4, 6].

reduce() - Applies a function to each element of an array to reduce it to a single value. For example, [1, 2, 3, 4, 5].reduce((acc, num) => acc + num) would return the number 15.


## const, let, var

- const: Declares a variable that cannot be reassigned. The value of a const variable cannot be changed once it is set

- let: Declares a variable that can be reassigned. The value of a let variable can be changed after it is set. let is block-scoped, meaning it is only accessible within the block it was declared in.

- var: Declares a variable that can be reassigned. The value of a var variable can be changed after it is set. var is function-scoped, meaning it is accessible within the function it was declared in, or the global scope if it was declared outside of a function.

## String Concatenation

```js
const firstName = 'John';
const lastName = 'Doe';
const fullName = firstName + ' ' + lastName;
console.log(fullName); // Output: John Doe
```
Template literals are a way to concatenate strings and variables in a more convenient and readable way in JavaScript.
```js
    const message = `My name is ${name}, I am ${age} years old, and I work as a ${occupation}.`;

    const message = `This is a
    multi-line
    string.`;

    console.log(message);
    // Output:
    // "This is a
    // multi-line
    // string."
```
```js
const fruits = ['apple', 'banana', 'orange'];
const fruitString = fruits.join(', ');
console.log(fruitString); // Output: apple, banana, orange
```
## Implicit Type Conversion

- Implicit type conversion, also known as type coercion
```js
//Number to String
const num = 42;
const str = 'The answer is ' + num;
console.log(str); // Output: The answer is 42

// String to Number
const strNum = '42';
const numNum = strNum * 1;
console.log(numNum); // Output: 42

// Boolean to Number
const bool = true;
const numBool = bool + 1;
console.log(numBool); // Output: 2
```
## Data Types
    
- Primitive data types:

    a. Number: Represents numeric values, including integers and floating-point numbers.

    b. String: Represents text values, enclosed in single or double quotes.

    c. Boolean: Represents true or false values.

    d. Null: Represents a deliberate non-value or absence of any object value.

    e. Undefined: Represents the value of a variable that has been declared but has not been assigned a value.

    f. Symbol: Represents a unique identifier, used in ES6 and later.

- Complex data types:

    a. Object: Represents a collection of related data values, stored as key-value pairs. Objects can contain properties and methods, which are accessed using dot notation or bracket notation.

    b. Array: Represents a collection of ordered data values, stored as numbered elements. Arrays can be accessed using indexing, and have built-in methods for manipulation.

    c. Function: Represents a reusable block of code that performs a specific task. Functions can be defined and invoked using various syntax options, and can accept parameters and return values.

    d. Date: Represents a specific point in time, stored as a number of milliseconds since January 1, 1970.

    e. RegExp: Represents a regular expression, used for matching patterns in strings.

    f. Map and Set: Represent collections of values that can be iterated over and manipulated in various ways. These are introduced in ES6 and later.

## Arrays

1. Creating an array:
```js
const myArray = [1, 2, 3, 4, 5];
```
2. Alternatively, an empty array can be created and filled with values later:
```js
const myArray = [];
myArray.push(1);
myArray.push(2);
myArray.push(3);
```
3. Accessing array elements: Array elements can be accessed using bracket notation and an index, starting from 0:
```js
const myArray = [1, 2, 3, 4, 5];
```
4. Modifying array elements: Array elements can be modified using bracket notation and an index:
```js
const myArray = [1, 2, 3, 4, 5];
myArray[2] = 'three';
```
5. Array length: The length of an array can be accessed using the length property:
```js
const myArray = [1, 2, 3, 4, 5];
console.log(myArray.length); // Output: 5
```
6. Adding elements to an array: Elements can be added to the end of an array using the push() method:
```js
const myArray = [1, 2, 3, 4, 5];
myArray.push(6);
console.log(myArray); // Output: [1, 2, 3, 4, 5, 6]
```
7. Alternatively, elements can be added to the beginning of an array using the unshift() method:
```js
const myArray = [1, 2, 3, 4, 5];
myArray.unshift(0);
console.log(myArray); // Output: [0, 1, 2, 3, 4, 5]
```
8. Removing elements from an array: Elements can be removed from the end of an array using the pop() method:
```js
const myArray = [1, 2, 3, 4, 5];
myArray.pop();
console.log(myArray); // Output: [1, 2, 3, 4]
```
9. Elements can be removed from the beginning of an array using the shift() method:
```js
const myArray = [1, 2, 3, 4, 5];
myArray.shift();
console.log(myArray); // Output: [2, 3, 4, 5]
```
10. splice(index, count, element1, element2, ..., elementN): This method adds or removes elements from the array at the specified index.
```js
const arr = [1, 2, 3, 4];
arr.splice(1, 2, 5, 6);
console.log(arr); // [1, 5, 6, 4]
```
11. slice(startIndex, endIndex): This method returns a portion of the array, starting from the specified start index and ending at the specified end index (excluding the element at the end index).
```js
const arr = [1, 2, 3, 4];
const subArray = arr.slice(1, 3);
console.log(subArray); // [2, 3]
```

## Functions

1. Declaring a Function:
```js
    function greet(name) {
    console.log(`Hello, ${name}!`);
    }
```
2. Invoking a Function:
```js    
    greet("John"); // Output: Hello, John!
```
3. Parameters and Arguments: Parameters are variables declared in the function signature, while arguments are the actual values passed to the function when it's invoked:
```js
    function multiply(a, b) {
    return a * b;
    }
    const result = multiply(2, 3); // arguments are 2 and 3
    console.log(result); // Output: 6
```
4. Return:
```js
    function multiply(a, b) {
    return a * b;
    }
    const result = multiply(2, 3);
    console.log(result); // Output: 6
```
5. Function Expressions: A function expression is a function that's assigned to a variable or a constant and is not declared using the function keyword:
```js
    const greet = function(name) {
    console.log(`Hello, ${name}!`);
    };
    greet("John"); // Output: Hello, John!
```
6. Arrow Functions: An arrow function is a shorthand way to declare a function using the => arrow notation:
```js
    const multiply = (a, b) => {
    return a * b;
    };
    const result = multiply(2, 3);
    console.log(result); // Output: 6
```
## Objects
- In JavaScript, an object is a collection of properties, where each property is a key-value pair.
- Creating an Object:
```js
    const person = {
    name: "John",
    age: 30,
    city: "New York"
    };
```
- Accessing Object Properties:
```js    
    console.log(person.name); // Output: John
    console.log(person["age"]); // Output: 30
```
- Adding and Modifying Object Properties:
```js
    person.gender = "Male"; // Add a new property
    person.age = 32; // Modify an existing property
```
- Deleting Object Properties:
```js
    delete person.city;
```
- Object Methods:
```js
    const person = {
    name: "John",
    age: 30,
    city: "New York",
    sayHello: function() {
        console.log(`Hello, my name is ${this.name}!`);
    }
    };
    person.sayHello(); // Output: Hello, my name is John!
```
- Object Constructors: Objects can also be created using constructors, which are functions that are used to create new objects
```js 
    function Person(name, age, city) {
    this.name = name;
    this.age = age;
    this.city = city;
    this.sayHello = function() {
        console.log(`Hello, my name is ${this.name}!`);
    }
    }
    const person = new Person("John", 30, "New York");
    person.sayHello(); // Output: Hello, my name is John!
```
## Equality

-  There are two types of equality operators: == and ===. The == operator is used to test for abstract equality, while the === operator is used to test for strict equality.
- The == operator compares two values for equality after converting both values to a common type. This type conversion is known as type coercion. 
```js
  console.log(1 == "1");    // true
  console.log(true == 1);   // true
  console.log(null == undefined); // true
  console.log(null == 0);   // false
  console.log(false == ""); // true
```
- The === operator compares two values for equality without converting their types
```js
    console.log(1 === "1");    // false  
    console.log(true === 1);   // false
  console.log(null === undefined); // false
  console.log(null === 0);   // false
  console.log(false === ""); // false
```

## String Properties and Methods
```js
const str = "hello";
```
String Properties:
    - length: 
```js    
    str.length
```
    - constructor: This property returns a reference to the string's constructor function.
```js
    str.constructor
```
String Methods:
    - toUpperCase()
    - toLowerCase()
    - charAt(index)
    - concat(str1, str2, ..., strN)
    - indexOf(searchValue, startIndex)
    - replace(searchValue, replaceValue)
    - substring(startIndex, endIndex)

## Value vs Reference
- In JavaScript, variables can hold either primitive values or reference values. 

Primitive Values:
- Primitive values in JavaScript include strings, numbers, booleans, null, and undefined. 
```js    
    let x = 5; // x holds the primitive value 5
    let y = x //The value of x is copied to y and stored in a new memory location. Any changes to y will not affect the value of x.
```
Reference Values:
- Reference values in JavaScript include objects and arrays.
```js
    let obj1 = {name: "John", age: 30}; // obj1 holds a reference to an object
    let obj2 = obj1; // obj2 also holds a reference to the same object as obj1
```

## Null and Undefined
- undefined is a primitive value that is automatically assigned to variables that have been declared but have not yet been assigned a value. For example:
```js    
    let x; // x is undefined
```
- null, on the other hand, is an explicitly assigned value that represents the intentional absence of any object value. 
```js
    let x=null
```
- null is considered an object type, while undefined is a primitive value.

## Truthy and Falsy
- A truthy value is a value that evaluates to true when coerced into a boolean. Examples of truthy values in JavaScript include:
    Non-empty strings: "hello", "0", "false"
    Numbers other than 0: 1, 3.14, -42
    Objects and arrays: {}, []
    true

- On the other hand, a falsy value is a value that evaluates to false when coerced into a boolean. Examples of falsy values in JavaScript include:
    undefined
    null
    false
    0
    NaN
    "" (empty string)

## Variable Lookup
- Variable lookup in JavaScript refers to the process of finding the value of a variable based on its name and scope.
- When JavaScript encounters a variable name, it searches for the value of that variable in a series of nested scopes until it either finds the value or determines that the variable is undefined.
- If the variable is not found in any scope, JavaScript considers the variable to be undefined and throws a ReferenceError.

## Callback Functions, Higher Order Functions

Callback Functions
    - A callback function is a function that is passed as an argument to another function and is executed inside that function. 
    - Callback functions are commonly used in asynchronous programming, where the code needs to wait for some action to complete before executing the callback function.

Higher Order Functions
- A higher-order function is a function that takes one or more functions as arguments, and/or returns a function as its result. 
```js
    function repeat(n, action) {
    for (let i = 0; i < n; i++) {
        action(i);
    }
    }

    function logNumber(n) {
    console.log(n);
    }

    repeat(5, logNumber);
```
## Array Iterators

- In JavaScript, arrays come with a set of built-in methods, known as iterators, that allow you to easily loop through the elements of an array and perform operations on them. 
- These methods include forEach(), map(), filter(), reduce(), find(), and many more.

## forEach
- The forEach() method is used to loop over an array and perform a function on each element. 
- It takes a callback function as an argument that will be executed once for each element in the array.
```js
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(function(number) {
  console.log(number);
});

//Using forEach() with an Arrow Function
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(number => {
  console.log(number);
});

//Using forEach() with an Index
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(function(number, index) {
  console.log(`Index ${index}: ${number}`);
});

//Using forEach() with an Object
const person = {
  name: "John",
  age: 30,
  gender: "male"
};

Object.entries(person).forEach(([key, value]) => {
  console.log(`${key}: ${value}`);
});
```
## map
- The map() method is used to loop over an array and create a new array with the results of calling a provided function on every element in the array.
```js
const numbers = [1, 2, 3, 4, 5];

const doubledNumbers = numbers.map(function(number) {
  return number * 2;
});

console.log(doubledNumbers); // [2, 4, 6, 8, 10]

//Using map() with Index
const numbers = [1, 2, 3, 4, 5];

const indexedNumbers = numbers.map(function(number, index) {
  return `${number} at ${index}`;
});

console.log(indexedNumbers)

//Using map() with an Object
const people = [
  { name: "John", age: 30 },
  { name: "Mary", age: 25 },
  { name: "Alex", age: 40 }
];

const names = people.map(person => person.name);

console.log(names); // Output: ["John", "Mary", "Alex"]

//Using map() with Arrow Function
const numbers = [1, 2, 3, 4, 5];

const squaredNumbers = numbers.map(number => number ** 2);

console.log(squaredNumbers);
```

## filter
- The filter() method is used to loop over an array and create a new array with all elements that pass a provided test.
```js
const numbers = [1, 2, 3, 4, 5];

const evenNumbers = numbers.filter(function(number) {
  return number % 2 === 0;
});

console.log(evenNumbers); // [2, 4]
```

## find
- The find() method is used to loop over an array and return the first element that passes a provided test.
```js
const numbers = [1, 2, 3, 4, 5];

const firstEvenNumber = numbers.find(function(number) {
  return number % 2 === 0;
});

console.log(firstEvenNumber); // 2
```
## reduce
- The reduce() method is used to loop over an array and reduce it to a single value by performing a provided operation on each element.
```js
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce(function(total, number) {
  return total + number;
}, 0);

console.log(sum); // 15
```
## Square Bracket Notation
- Square bracket notation is particularly useful when working with dynamic property names or when the property name is not known until runtime. 
```js
const person = {
  name: 'John',
  age: 30,
};

const propertyName = 'age';

person[propertyName] = 31;

console.log(person.age); // Output: 31
```
## Math Object

1. Math.PI: Returns the value of pi, which is approximately 3.141592653589793.
```js
    console.log(Math.PI); // Output: 3.141592653589793
```
2. Math.abs(): Returns the absolute value of a number.
```js
    console.log(Math.abs(-5)); // Output: 5
```
3. Math.ceil(): Rounds a number up to the nearest integer.
```js
    console.log(Math.ceil(4.3)); // Output: 5
```
4. Math.floor(): Rounds a number down to the nearest integer.
```js
    console.log(Math.floor(4.9)); // Output: 4
```
5. Math.round(): Rounds a number to the nearest integer.
```js
console.log(Math.round(4.5)); // Output: 5
console.log(Math.round(4.4)); // Output: 4
```
6. Math.max(): Returns the largest of zero or more numbers.
```js
    console.log(Math.max(1, 2, 3)); // Output: 3
```
7. Math.min(): Returns the smallest of zero or more numbers.
```js
    console.log(Math.min(1, 2, 3)); // Output: 1
```
8. Math.random(): Returns a random number between 0 (inclusive) and 1 (exclusive).
```js
    console.log(Math.random()); // Output: a random number between 0 and 1
```
9. Math.sqrt(): Returns the square root of a number.
```js
    console.log(Math.sqrt(9)); // Output: 3
```
10. Math.pow(): Returns the result of a base raised to an exponent.
```js
    console.log(Math.pow(2, 3)); // Output: 8
```
## Date Object
- It provides a number of methods to get and set the current date and time, as well as manipulate them in various ways.

1. new Date(): Creates a new instance of the Date object with the current date and time.
```js
let currentDate = new Date();
console.log(currentDate); // Output: current date and time
```
2. Date.now(): Returns the number of milliseconds since January 1, 1970, 00:00:00 UTC.
```js
let currentTime = Date.now();
console.log(currentTime); // Output: number of milliseconds since January 1, 1970, 00:00:00 UTC
```
3. getYear(), getFullYear(): Returns the year of the date as a 2-digit or 4-digit number.
```js
let date = new Date();
console.log(date.getYear()); // Output: year as a 2-digit number
console.log(date.getFullYear()); // Output: year as a 4-digit number
```
4. getMonth(): Returns the month of the date as a number between 0 and 11.
```js
let date = new Date();
console.log(date.getMonth()); // Output: month as a number between 0 and 11
```
5. getDate(): Returns the day of the month of the date as a number between 1 and 31.
```js
let date = new Date();
console.log(date.getDate()); // Output: day of the month as a number between 1 and 31
```
6. getDay(): Returns the day of the week of the date as a number between 0 (Sunday) and 6 (Saturday).
```js
let date = new Date();
console.log(date.getDay()); // Output: day of the week as a number between 0 and 6
```
7. getHours(), getMinutes(), getSeconds(), getMilliseconds(): Returns the hours, minutes, seconds, and milliseconds of the date as numbers.
```js
let date = new Date();
console.log(date.getHours()); // Output: hours of the date as a number between 0 and 23
console.log(date.getMinutes()); // Output: minutes of the date as a number between 0 and 59
console.log(date.getSeconds()); // Output: seconds of the date as a number between 0 and 59
console.log(date.getMilliseconds()); // Output: milliseconds of the date as a number between 0 and 999
```
8. setFullYear(), setMonth(), setDate(), setHours(), setMinutes(), setSeconds(), setMilliseconds(): Sets the year, month, day of the month, hours, minutes, seconds, and milliseconds of the date.
```js
let date = new Date();
date.setFullYear(2022);
console.log(date.getFullYear()); // Output: 2022
```
9. toString(): Returns a string representation of the date.
```js
let date = new Date();
console.log(date.toString()); // Output: string representation of the date
```
## DOM - Intro

- The Document Object Model (DOM) is a programming interface for web documents. 
- It represents the page so that programs can change the document structure, style, and content. 
- Essentially, it connects web pages to scripts or programming languages by representing the page in the form of an object-oriented model. 
- This allows programming languages, such as JavaScript, to manipulate the page's content, structure, and styling.

The DOM tree is made up of four main types of nodes: document nodes, element nodes, attribute nodes, and text nodes.
    - The HTML document itself is the document node.
    - The HTML elements are defined by element nodes.
    - The HTML attributes are defined by attribute nodes.
    - Text inside HTML elements are defined by text nodes.
    - Comments are defined by comment nodes.

JavaScript can access and manipulate the DOM in a variety of ways. For example, it can:
    - Add or remove elements and attributes
    - Change the content of an element
    - Change the styling of an element
    - Respond to user events, such as mouse clicks or keyboard input

## Window and Document Overview
- In web development, the Window and Document are two important objects that provide a way to interact with and manipulate the browser window and the content displayed in it.
- The Window object is the top-level object of the browser's JavaScript API, and it represents the browser window that is displaying the current web page.
- One common use of the Window object is to interact with the current web page by accessing its Document object. 
- The Document object represents the content of the web page and provides methods for manipulating the HTML elements and their properties, such as adding or removing elements, changing their attributes, and modifying their content.

Some common methods for manipulating the Document object include:

getElementById(): retrieves an element by its ID attribute
querySelector(): retrieves the first element that matches a specified CSS selector
createElement(): creates a new element
appendChild(): adds an element as a child of another element
removeChild(): removes a child element from its parent
setAttribute(): sets an attribute on an element
addEventListener(): adds an event listener to an element

## Get Element By ID

Usecases:
1. Manipulating text and content
```js
    // retrieve the reference to the div element
    const myDiv = document.getElementById('myDiv');

    // change the text content of the div element
    myDiv.textContent = 'Hello JavaScript!';

    // change the background color of the div element
    myDiv.style.backgroundColor = 'red';
```
2. Validating form inputs
```js
    // retrieve the reference to the email input element
    const emailInput = document.getElementById('email');

    // add an event listener to the form submit button
    const submitButton = document.querySelector('button[type="submit"]');
    submitButton.addEventListener('click', (event) => {
    // prevent the default form submission behavior
    event.preventDefault();
    
    // check that the email address is valid
    const email = emailInput.value;
    if (isValidEmail(email)) {
        // submit the form
        event.target.form.submit();
    } else {
        // display an error message
        alert('Please enter a valid email address.');
    }
    });

    function isValidEmail(email) {
    // check that the email address is valid
    // ...
    }
```

3. Animating elements
```js
    // retrieve the reference to the image element
    const myImage = document.getElementById('myImage');

    // add an event listener to the image element
    myImage.addEventListener('mouseenter', () => {
    // animate the image's position and opacity
    myImage.style.transform = 'translateX(50px)';
    myImage.style.opacity = 0.5;
    });

    myImage.addEventListener('mouseleave', () => {
    // reset the image's position and opacity
    myImage.style.transform = '';
    myImage.style.opacity = 1;
    });
```
4. Showing and hiding elements
```js
    //html
    <button id="showBtn">Show</button>
    <button id="hideBtn">Hide</button>
    <div id="myDiv">This is my div element</div>

    //JS
    const myDiv = document.getElementById('myDiv');
    const showBtn = document.getElementById('showBtn');
    const hideBtn = document.getElementById('hideBtn');

    showBtn.addEventListener('click', () => {
    myDiv.style.display = 'block';
    });

    hideBtn.addEventListener('click', () => {
    myDiv.style.display = 'none';
    });
```

## Get Elements By Tag Name
- getElementsByTagName() is a method in JavaScript that is used to retrieve a collection of elements on the page with the specified tag name. 
- It returns a HTMLCollection object that contains all elements with the specified tag name in the order they appear in the HTML source code.

1. Accessing a single element:
```js
const myElement = document.getElementsByTagName('div')[0];
```
2. Looping through multiple elements:
```js
const myElements = document.getElementsByTagName('div');
for (let i = 0; i < myElements.length; i++) {
  console.log(myElements[i]);
}
```
3. Adding event listeners to multiple elements:
```js
const myButtons = document.getElementsByTagName('button');
for (let i = 0; i < myButtons.length; i++) {
  myButtons[i].addEventListener('click', function() {
    console.log('Button ' + (i + 1) + ' was clicked!');
  });
}
```
### Tag Names
a: Anchor element
abbr: Abbreviation element
acronym: Acronym element (deprecated)
address: Address element
applet: Applet element (deprecated)
area: Area element
article: Article element
aside: Aside element
audio: Audio element
b: Bold element
base: Base element
basefont: Basefont element (deprecated)
bdi: BDI element
bdo: BDO element
big: Big element (deprecated)
blockquote: Blockquote element
body: Body element
br: Line break element
button: Button element
canvas: Canvas element
caption: Caption element
center: Center element (deprecated)
cite: Citation element
code: Code element
col: Column element
colgroup: Column group element
data: Data element
datalist: Data list element
dd: Description element
del: Deleted text element
details: Details element
dfn: Definition element
dialog: Dialog element
dir: Directory element (deprecated)
div: Division element
dl: Description list element
dt: Description term element
em: Emphasis element
embed: Embedded content element
fieldset: Fieldset element
figcaption: Figure caption element
figure: Figure element
font: Font element (deprecated)
footer: Footer element
form: Form element
frame: Frame element (deprecated)
frameset: Frameset element (deprecated)
h1 - h6: Heading elements
head: Head element
header: Header element
hr: Horizontal rule element
html: HTML element
i: Italic element
iframe: Inline frame element
img: Image element
input: Input element
ins: Inserted text element
kbd: Keyboard input element
label: Label element
legend: Legend element
li: List item element
link: Link element
main: Main element
map: Map element
mark: Marked text element
meta: Meta element
meter: Meter element
nav: Navigation element
noframes: No frames element (deprecated)
noscript: No script element
object: Object element
ol: Ordered list element
optgroup: Option group element
option: Option element
output: Output element
p: Paragraph element
param: Parameter element (deprecated)
picture: Picture element
pre: Preformatted text element
progress: Progress element
q: Quotation element
rp: Ruby parentheses element
rt: Ruby text element
ruby: Ruby annotations element
s: Strikethrough element (deprecated)
samp: Sample output element
script: Script element
section: Section element
select: Select element
small: Small print element
source: Media source element
span: Span element
strong: Defines strong text
table: Defines an HTML table
tr: Defines a row in an HTML table
td: Defines a cell in an HTML table
ul: Defines an unordered list in an HTML document

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## Get Element By Class Name

1. Retrieving elements with a single class name:
```js
const elements = document.getElementsByClassName('my-class');
//This retrieves all elements with the class name "my-class" and returns a live HTMLCollection.
```
2. Retrieving elements with multiple class names:
```js
const elements = document.getElementsByClassName('class-1 class-2');
//This retrieves all elements that have both the "class-1" and "class-2" class names.
```
3. Retrieving elements from a specific parent element:
```js
const parent = document.getElementById('parent-element');
const elements = parent.getElementsByClassName('my-class');
```
4. Retrieving the first element with a class name:
```js
const element = document.getElementsByClassName('my-class')[0];
```
- It's worth noting that getElementsByClassName returns a live collection, which means that if you modify the DOM in a way that affects the collection, it will automatically update to reflect those changes. If you need a static collection of elements, you can convert the HTMLCollection to an array:
```js
const elements = Array.from(document.getElementsByClassName('my-class'));
```
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## Query Selector and Query Selector ALL
- The Document method querySelector() returns the first Element within the document that matches the specified selector, or group of selectors. 
- If no matches are found, null is returned.

1. Selecting an element by its ID:

2. Selecting the first element of a certain tag:
```js
const myElement = document.querySelector('div');
```
3. Selecting the first element with a certain class:
```js
const myElement = document.querySelector('.myClass');
```
4. Selecting the first element with a certain attribute:
```js
const myElement = document.querySelector('[data-myAttribute]');
```
5. Selecting the first element matching a specific CSS selector:
```js
const myElement = document.querySelector('ul li:last-child');
```
- what is selectors?
    - A string containing one or more css selectors to match. 
    - This string must be a valid CSS selector string; if it isn't, a SyntaxError exception is thrown.
    - more on: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors
- same for Query Selector ALL
    const myElements = document.querySelectorAll('.myClass');

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Navigate the DOM - Children

- In the DOM, nodes are organized in a hierarchical structure with parent and child relationships. 
- Navigating the DOM tree is the process of accessing nodes in the tree structure, and there are several methods available for doing this.
- One common way to navigate the DOM is by accessing a parent node and then using a method to retrieve its child nodes. 
- The children property is one such method that returns a collection of child nodes for a specified parent node. 
- The children property returns a live HTMLCollection object, which means that any changes made to the DOM will be automatically reflected in the collection.

Here's an example of how to use the children property to retrieve all the child elements of a parent element:
    //html
    <div id="parent">
    <p>First paragraph</p>
    <p>Second paragraph</p>
    <ul>
        <li>List item 1</li>
        <li>List item 2</li>
    </ul>
    </div>

    //javascript
    const parent = document.getElementById('parent');
    const children = parent.children;

    console.log(children); // HTMLCollection [p, p, ul]

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Navigate the DOM - parentElement

- In DOM manipulation, the parent element of an HTML element can be navigated using the parentElement property.
    //html
    <div id="parent">
    <p>Child element 1</p>
    <p>Child element 2</p>
    </div>

    //javascript
    const childElement = document.querySelector('p');
    const parentElement = childElement.parentElement;
    console.log(parentElement); // Output: <div id="parent">...</div>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Navigate the DOM - nextSibling, previousSibling

- The nextSibling and previousSibling properties are used to access the siblings (i.e., elements that share the same parent) that come after or before a given element, respectively.
<body>
  <div id="parent">
    <p>First paragraph</p>
    <p>Second paragraph</p>
    <p>Third paragraph</p>
  </div>

  <script>
    const secondPara = document.querySelector('#parent p:nth-child(2)'); // get the second paragraph element
    const prevSibling = secondPara.previousSibling; // get the previous sibling of the second paragraph
    const nextSibling = secondPara.nextSibling; // get the next sibling of the second paragraph

    console.log(prevSibling); // logs "Text "
    console.log(nextSibling); // logs "<p>Third paragraph</p>"
  </script>
</body>

- In this example, we first select the second paragraph element using the querySelector() method. Then, we use the previousSibling property to get the previous sibling of the second paragraph, which is a text node (containing only whitespace). Finally, we use the nextSibling property to get the next sibling of the second paragraph, which is the third paragraph element.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Navigate the DOM - nextElementSibling, previousElementSibling

- The nextElementSibling and previousElementSibling properties are used to navigate the DOM to get the next or previous sibling element, which is an element node (e.g., an HTML element like <div>, <p>, etc.).
    <div id="parent">
        <span>First</span>
        <span>Second</span>
        <span>Third</span>
    </div>

    <script>
        const secondSpan = document.querySelector('#parent span:nth-child(2)');
        const thirdSpan = secondSpan.nextElementSibling;
        const firstspan = thirdSpan.previousElementSibling;
        console.log(secondSpan.textContent); // Output: "Second"
        console.log(firstspan.textContent); // Output: "First"
    </script>



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

textContent nodeValue innerHTML

- textContent: textContent property is used to set or get the text content of an element, including its descendants. It returns or sets a string containing the text within the specified element.

    <div id="myDiv">Hello <span>World</span>!</div>
    const myDiv = document.getElementById('myDiv');
    const textContent = myDiv.textContent;
    console.log(textContent); // Output: Hello World!

    //to set
    myDiv.textContent = "Goodbye World!";
    console.log(myDiv.textContent); // Output: Goodbye World!

- nodeValue property is used to set or get the value of a node, including text nodes. It returns or sets a string containing the value of the specified node.

    //To get the value of the above paragraph element, you can use the nodeValue property:
    const myParagraph = document.getElementById('myParagraph').firstChild;
    const nodeValue = myParagraph.nodeValue;
    console.log(nodeValue); // Output: This is a paragraph.

    //To set the value of the above paragraph element, you can also use the nodeValue property:
    myParagraph.nodeValue = "This is a new paragraph.";
    console.log(myParagraph.nodeValue); // Output: This is a new paragraph.

- Note that nodeValue property only works for text nodes. For other types of nodes, it returns null. 
- In such cases, you can use textContent property to get or set the text content.

- innerHTML is a property that sets or returns the HTML content (including tags) inside an element. 
- It is commonly used to update the content of an element or add new elements to it. 
- When used to update the content of an element, it replaces the existing content with the new content, including any HTML tags.
    <div id="myDiv">
    <p>Hello World</p>
    </div>
    const myDiv = document.getElementById('myDiv');
    myDiv.innerHTML = '<p>Hello Universe</p>';


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

getAttribute() setAttribute()

- getAttribute() is used to get the value of a specified attribute on the element. It takes one parameter, which is the name of the attribute we want to retrieve. For example, to get the value of the src attribute of an img element with the id of myImage, we would use:
    const myImage = document.getElementById('myImage');
    const srcValue = myImage.getAttribute('src');
    console.log(srcValue); // logs the value of the src attribute of myImage

- setAttribute() is used to set the value of a specified attribute on the element. It takes two parameters, the name of the attribute and the value we want to set. For example, to set the src attribute of the img element with the id of myImage to a new value, we would use:
    const myImage = document.getElementById('myImage');
    myImage.setAttribute('src', 'new-image.jpg');

- We can also use setAttribute() to create a new attribute on the element. For example, to create a data-* attribute on an element, we would use:
    const myElement = document.getElementById('myElement');
    myElement.setAttribute('data-my-attribute', 'my-value');

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

classList and className

- In JavaScript, the classList property is used to add, remove, and toggle CSS classes on an HTML element. 
- It returns a collection of a element's CSS classes, which can then be manipulated using the add(), remove(), toggle(), and contains() methods.

1. Adding or Removing CSS Classes

    const myElement = document.getElementById('myElement');
    // Add a CSS class to an element
    myElement.classList.add('active');
    // Remove a CSS class from an element
    myElement.classList.remove('active');

2. Toggling CSS Classes

    const myElement = document.getElementById('myElement');
    // Toggle a CSS class on an element
    myElement.classList.toggle('active');

3. Checking if an element has a CSS class

    const myElement = document.getElementById('myElement');
    // Check if an element has a CSS class
    if (myElement.classList.contains('active')) {
    // Do something
    }

- The className property, on the other hand, is used to get or set the value of the class attribute of an HTML element. 
- It returns a string that contains all the classes associated with the element, separated by a space.

1. Setting the Class Name of an Element
    const myElement = document.getElementById('myElement');
    // Set the class name of an element
    myElement.className = 'new-class';

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

createElement - createTextNode - appendChild

- createElement(), createTextNode(), and appendChild() are used together to create and insert new elements and text nodes into the DOM.

<!DOCTYPE html>
<html>
  <head>
    <title>Example</title>
  </head>
  <body>
    <div id="myDiv"></div>
    <script>
      // get reference to the div element
      const myDiv = document.getElementById('myDiv');

      // create a new paragraph element
      const newParagraph = document.createElement('p');

      // create a new text node
      const newText = document.createTextNode('This is a new paragraph.');

      // append the text node to the paragraph element
      newParagraph.appendChild(newText);

      // append the paragraph element to the div element
      myDiv.appendChild(newParagraph);
    </script>
  </body>
</html>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

insertBefore
- The insertBefore() method in JavaScript is used to insert a new node before an existing node as a child node of a specified parent node. 
- Syntax: parentNode.insertBefore(newNode, referenceNode);
    > where parentNode is the parent node where the new node will be inserted, newNode is the node to be inserted, and referenceNode is the node before which the new node should be inserted. 
    > If referenceNode is null, then the new node is inserted at the end of the child list of the parentNode.

1. Inserting a new element before an existing element:

    const parent = document.getElementById('parent');
    const existingElement = document.getElementById('existingElement');
    const newElement = document.createElement('div');
    newElement.textContent = 'New Element';
    parent.insertBefore(newElement, existingElement);

2. Moving an element from one position to another:

    const parent = document.getElementById('parent');
    const elementToMove = document.getElementById('elementToMove');
    const referenceElement = document.getElementById('referenceElement');
    parent.insertBefore(elementToMove, referenceElement);

3. Inserting a new element at the end of the child list:

    const parent = document.getElementById('parent');
    const newElement = document.createElement('div');
    newElement.textContent = 'New Element';
    parent.appendChild(newElement);

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

replaceChild

- The replaceChild() method is used to replace a child node of a specified node with a new node.
<body>
  <ul id="myList">
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
  </ul>
  <button onclick="replaceListItem()">Replace Item 2</button>
</body>

<script>
function replaceListItem() {
  // Create a new list item
  var newItem = document.createElement("li");
  var textNode = document.createTextNode("New Item");
  newItem.appendChild(textNode);
  
  // Get a reference to the list and the second item
  var list = document.getElementById("myList");
  var oldItem = list.children[1];
  
  // Replace the old item with the new item
  list.replaceChild(newItem, oldItem);
}
</script>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

prepend innerText

- prepend() method can be used to add an element to the beginning of a parent element. 
    const myList = document.querySelector('ul');
    const newListItem = document.createElement('li');
    newListItem.textContent = 'New item';
    myList.prepend(newListItem);

- innerText property can be used to get or set the text content of an element.
    const myHeading = document.querySelector('h1');
    myHeading.innerText = 'New heading';


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

remove & removeChild

- remove and removeChild are two methods in the DOM used to remove an element from the document.

- remove

1. Removing an element when a certain condition is met:
    const myElement = document.querySelector('#myElement');
    if (someCondition) {
    myElement.remove();
    }

2. Removing an element after a certain amount of time:
    const myElement = document.querySelector('#myElement');
    setTimeout(() => {
    myElement.remove();
    }, 5000);
    
- removeChild method:

1. Removing a child element from a parent element:

    const myParent = document.querySelector('#myParent');
    const myChild = document.querySelector('#myChild');
    myParent.removeChild(myChild);
    
2. Removing a child element at a specific index from a parent element:

    const myParent = document.querySelector('#myParent');
    const index = 2;
    myParent.removeChild(myParent.children[index]);

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Change CSS with "style" property

- The style property of an HTML element can be used to change its CSS style properties dynamically through JavaScript. Here are some use cases:

- Change the background color of a button when it's clicked:
    const myButton = document.getElementById('myButton');
    myButton.addEventListener('click', function() {
    myButton.style.backgroundColor = 'red';
    });

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Events Overview

- In JavaScript, events are actions or occurrences that happen on the web page, such as clicking on a button, hovering over an element, scrolling the page, or submitting a form. 
- We can use event listeners to listen for these events and execute code in response to them.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Click Event

- It is triggered when an element is clicked by the user

1. Button click event: You can use the click event to handle button clicks in your web page. For example, you can use it to submit a form or perform some other action.
    
    <button id="myButton">Click me</button>
    
    const button = document.getElementById('myButton');
    button.addEventListener('click', function() {
    alert('Button clicked!');
    });

2. Image click event: You can use the click event to handle image clicks on your web page. For example, you can use it to display a larger version of the image in a modal.

    <img src="myImage.png" id="myImage">

    const image = document.getElementById('myImage');
    image.addEventListener('click', function() {
    // display a larger version of the image in a modal
    });

3. Link click event: You can use the click event to handle link clicks on your web page. For example, you can use it to prevent the default behavior of a link and perform some other action instead.

    <a href="#" id="myLink">Click me</a>

    const link = document.getElementById('myLink');
    link.addEventListener('click', function(event) {
    event.preventDefault(); // prevent the default behavior of the link
    // perform some other action instead
    });

4. Menu item click event: You can use the click event to handle menu item clicks on your web page. For example, you can use it to display a submenu or perform some other action.

    <ul>
    <li><a href="#" id="menu1">Menu item 1</a></li>
    <li><a href="#" id="menu2">Menu item 2</a></li>
    <li><a href="#" id="menu3">Menu item 3</a></li>
    </ul>

    const menu1 = document.getElementById('menu1');
    menu1.addEventListener('click', function() {
    // display a submenu for menu item 1
    });

    const menu2 = document.getElementById('menu2');
    menu2.addEventListener('click', function() {
    // perform some other action for menu item 2
    });

    const menu3 = document.getElementById('menu3');
    menu3.addEventListener('click', function() {
    // perform some other action for menu item 3
    })

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Mouse Events

- mouse events are events that are triggered when the user interacts with the mouse. 
- These events include click, mouseover, mouseout, mousemove, and many others.

click
contextmenu
dblclick
mousedown
mouseup
mousemove
mouseover
mouseout
mouseenter
mouseleave
selectstart
wheel
pointerlockchange
pointerlockerror
gotpointercapture
lostpointercapture

1. Mouseover Event - This event is triggered when the mouse pointer is moved over an element. It is commonly used to change the appearance of an element when the user hovers over it. Here is an example of how to use the mouseover event:

const myImage = document.getElementById('myImage');
myImage.addEventListener('mouseover', function() {
  this.style.border = '1px solid red';
});

3. Mouseout Event - This event is triggered when the mouse pointer moves out of an element. It is commonly used to reset the appearance of an element when the user stops hovering over it. Here is an example of how to use the mouseout event:
javascript
Copy code
const myImage = document.getElementById('myImage');
myImage.addEventListener('mouseout', function() {
  this.style.border = 'none';
});

4. Mousemove Event - This event is triggered when the mouse pointer is moved over an element. It is commonly used to track the movement of the mouse and update the position of an element. Here is an example of how to use the mousemove event:
javascript
Copy code
const myBox = document.getElementById('myBox');
myBox.addEventListener('mousemove', function(event) {
  const x = event.clientX;
  const y = event.clientY;
  this.style.top = y + 'px';
  this.style.left = x + 'px';
});
These are just a few examples of how mouse events can be used in JavaScript. With the help of these events, you can create interactive and engaging web pages that respond to user actions.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Key Events

- Key events are events that are triggered when a keyboard key is pressed or released. 

Here are some of the commonly used keyboard events in JavaScript:

keydown - occurs when a key is pressed down
keyup - occurs when a key is released
keypress - occurs when a key is pressed and released
input - occurs when the value of an input element is changed (including by typing on the keyboard)
change - occurs when the value of a form element (such as a select or input) is changed
focus - occurs when an element becomes the active element (such as when an input element is clicked on)
blur - occurs when an element loses focus (such as when an input element is clicked away from)

Usecases:
1. Form validation: You can use key events to validate user input in a form, such as checking if a required field has been filled in or if the input matches a certain pattern.

    const input = document.querySelector('#username');

    input.addEventListener('keyup', () => {
    if (input.value.length < 3) {
        input.classList.add('error');
    } else {
        input.classList.remove('error');
    }
    });

2. Hotkeys: You can use key events to implement hotkeys in your web app, such as Ctrl+S for saving or Ctrl+Z for undo.

    document.addEventListener('keydown', (event) => {
    if (event.ctrlKey && event.key === 's') {
        // Save the document
    } else if (event.ctrlKey && event.key === 'z') {
        // Undo the last action
    }
    });

3. Game controls: You can use key events to implement game controls in a browser-based game.

    document.addEventListener('keydown', (event) => {
    if (event.key === 'ArrowLeft') {
        // Move the player left
    } else if (event.key === 'ArrowRight') {
        // Move the player right
    } else if (event.key === 'Space') {
        // Jump
    }
    });

4. Autocomplete: You can use key events to implement autocomplete functionality, such as showing suggestions when the user types in a search box.

    const input = document.querySelector('#search');

    input.addEventListener('keyup', () => {
    // Fetch suggestions based on the input value
    });
    
5. Navigation: You can use key events to implement navigation in a web app, such as using the arrow keys to navigate between pages.

    document.addEventListener('keydown', (event) => {
    if (event.key === 'ArrowLeft') {
        // Go to the previous page
    } else if (event.key === 'ArrowRight') {
        // Go to the next page
    }
    });

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Event Object

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

CurrentTarget vs Target

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Event Propagation - Bubbling- Capturing

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Event Propagation Example

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Forms

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Local Storage

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Local Storage With Multiple Values

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

setTimeout

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

setInterval

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Events - "DOMContentLoaded"

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Events - "load"

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Events - "scroll"

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Width, Height, GetBoundingClientRect

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Events - "resize"

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Event Object usecases 
The Event Object in JavaScript provides information about an event when it occurs, such as the type of event, the target element, the mouse position, and keyboard state. It can be used to modify the default behavior of the event or to provide additional functionality to an event.

Here are some use cases of the Event Object:

Preventing the default behavior of an event: By default, some events perform certain actions, such as submitting a form or following a hyperlink. With the Event Object, you can prevent this default behavior using the preventDefault() method.
Example:

javascript
Copy code
document.querySelector('a').addEventListener('click', function(event) {
  event.preventDefault();
  console.log('The link was clicked, but its default behavior was prevented.');
});
Stopping event propagation: Event propagation is the process by which an event travels through the DOM hierarchy from the top-level element to the target element. The Event Object has a stopPropagation() method that can be used to stop the event from propagating further up the hierarchy.
Example:

javascript
Copy code
document.querySelector('button').addEventListener('click', function(event) {
  event.stopPropagation();
  console.log('The button was clicked, but the event did not propagate further.');
});
Accessing information about the event: The Event Object provides a variety of properties and methods that allow you to access information about the event, such as the target element, the type of event, the coordinates of the mouse, and the state of the keyboard.
Example:

javascript
Copy code
document.addEventListener('mousemove', function(event) {
  console.log(`The mouse is at (${event.clientX}, ${event.clientY})`);
});
Dynamically modifying elements on the page based on the event: With the Event Object, you can dynamically modify elements on the page based on the event that occurs. For example, you can change the color of a button when it is clicked, or display a message when the mouse moves over an element.
Example:

javascript
Copy code
document.querySelector('button').addEventListener('click', function(event) {
  event.target.style.backgroundColor = 'red';
});
These are just a few use cases of the Event Object. With the rich set of properties and methods it provides, it can be used in a variety of ways to create dynamic and interactive web applications.




Khushi Jain
CurrentTarget vs Target usecases
In JavaScript, events can propagate through the DOM, meaning they can be triggered on an element and then propagate up through its ancestors. When an event is triggered, it can be handled by multiple event listeners attached to different elements.

In this context, the event.currentTarget property refers to the element to which the event listener is attached, while the event.target property refers to the element on which the event was originally triggered.

Here are some use cases for event.currentTarget and event.target:

When you want to apply an event listener to a parent element and then determine which child element triggered the event. In this case, you would attach the event listener to the parent element, and then use event.target to determine which child element was clicked or otherwise triggered the event.

When you want to handle an event on an element and then stop the event from propagating further up the DOM. In this case, you would attach the event listener to the element you want to handle the event on, and then use event.stopPropagation() to prevent the event from bubbling up to parent elements.

When you want to apply an event listener to multiple elements, but perform a different action based on which element triggered the event. In this case, you would attach the event listener to the parent element, and then use event.currentTarget to determine which child element triggered the event, and then perform a different action based on that element.




Khushi Jain
Event Propagation - Bubbling- Capturing usecases
Event propagation is the process of propagating an event from the target element to its parent elements in the DOM tree. There are two types of event propagation in the DOM:

Bubbling: In bubbling, the event is first captured by the innermost element and then propagated to its parent elements in the DOM tree. For example, if you click on a button that is inside a div element, the button's click event will be captured first, and then the div's click event will be captured next.

Capturing: In capturing, the event is first captured by the outermost element and then propagated to its child elements in the DOM tree. For example, if you click on a div element that contains a button, the div's click event will be captured first, and then the button's click event will be captured next.

To understand the event propagation, we can use the event object that is passed to the event handler function. The event object has two important properties:

event.target: It refers to the element on which the event was originally fired.

event.currentTarget: It refers to the element on which the event handler is currently attached.

Here are some use cases of event propagation:

Event delegation: Event delegation is a technique that uses event propagation to handle events on multiple elements with a single event handler. For example, if you have a list of items and want to handle the click event on each item, you can attach the event handler to the parent element and use event.target to identify the clicked item.

Stop propagation: Sometimes, you may want to stop the event from propagating further to its parent elements. You can use the event.stopPropagation() method to stop the event propagation.

Capturing and bubbling: You can use the addEventListener() method to attach event handlers to elements and control the event propagation using the third parameter of the method. If you set this parameter to true, the event will be captured instead of bubbling. If you set it to false or omit it, the event will bubble by default.




Khushi Jain
Event Propagation Example Capturing usecases
Sure, here's an example of using event propagation with capturing:

HTML:

bash
Copy code
<div id="outer">
  <div id="inner">
    <button id="btn">Click me!</button>
  </div>
</div>
JavaScript:

javascript
Copy code
const outer = document.getElementById('outer');
const inner = document.getElementById('inner');
const btn = document.getElementById('btn');

outer.addEventListener('click', () => {
  console.log('Outer clicked');
}, true); // Use capturing

inner.addEventListener('click', () => {
  console.log('Inner clicked');
}, true); // Use capturing

btn.addEventListener('click', () => {
  console.log('Button clicked');
}, true); // Use capturing
In this example, we have three elements: outer, inner, and btn. We've added a click event listener to each of these elements with the useCapture parameter set to true. This means that the event listeners will be triggered during the capturing phase of the event propagation, rather than the bubbling phase.

When you click the button, you'll see the following output in the console:

sql
Copy code
Outer clicked
Inner clicked
Button clicked
This is because the capturing phase starts at the top of the DOM tree and works its way down to the target element (btn). In this case, the capturing phase triggers the event listeners on outer, inner, and btn in that order.




Khushi Jain
Forms Example usecases
Forms are an essential part of most websites, and JavaScript can be used to enhance their functionality. Here are some examples of using JavaScript with forms:

Form Validation: JavaScript can be used to validate user input in a form before it is submitted to the server. This can help to ensure that the data entered is valid and reduce the number of errors that occur. Examples of validation include checking for required fields, validating email addresses, and verifying that passwords meet certain criteria.

Auto-Complete: JavaScript can be used to provide auto-complete functionality in forms. This can help users to quickly and easily enter data by suggesting values based on what has been entered so far. Examples include auto-complete for email addresses, usernames, and city names.

Dynamic Form Fields: JavaScript can be used to add or remove form fields based on user input. This can be useful in cases where additional information is needed based on the user's selection. Examples include adding additional fields for shipping information when a different shipping address is selected, or adding fields for additional guests when booking a hotel room.

Conditional Form Fields: JavaScript can be used to show or hide form fields based on the user's selection. This can help to simplify the form and make it easier to use by only showing relevant fields. Examples include showing fields for payment information only when a payment option is selected, or showing fields for a specific type of product only when that product is selected.

AJAX Form Submission: JavaScript can be used to submit form data to the server without refreshing the page. This can provide a more seamless user experience and reduce the amount of time it takes for the form to be processed. Examples include submitting a contact form or a newsletter subscription form.

These are just a few examples of how JavaScript can be used with forms. The possibilities are endless, and with the right approach, you can enhance the functionality of your forms and provide a better user experience for your visitors.




Khushi Jain
Local Storage usecases
Local storage is a way to store key-value pairs in the user's web browser. It allows developers to store data locally on the user's computer, which can be used to store information that is required by the web application to function properly. Here are some use cases of local storage:

User Preferences: Local storage can be used to store user preferences like theme, font size, language, etc. which can be retrieved every time the user visits the website.

Shopping Cart: Local storage can be used to store items in the shopping cart of an e-commerce website. This will help users to resume their shopping at a later time, even if they close their browser.

Form Data: Local storage can be used to store form data temporarily. If a user accidentally refreshes the page or loses internet connection, the form data will still be available when the user returns to the page.

Game State: Local storage can be used to store the game state of a web-based game. This can help the user to resume the game from the last point where they left off.

User Authentication: Local storage can be used to store user authentication tokens, which can be used to keep the user logged in even after the user closes the browser.

Overall, local storage is a powerful tool for web developers to provide a seamless user experience to their users. It is supported by all modern web browsers and can store up to 5-10 MB of data, depending on the browser.




Khushi Jain
Local Storage With Multiple Values usecases
Local Storage is a great way to store data in a user's browser that can be retrieved even after the user has closed the browser or turned off their computer. Here are some use cases of Local Storage with multiple values:

User Settings: You can store user settings such as color theme, language preference, and font size in Local Storage. This can help to provide a better user experience since users won't have to keep re-setting their preferences each time they visit the website.

Shopping Cart: You can use Local Storage to store information about items that have been added to a shopping cart. This can help to create a smoother shopping experience since users won't have to re-add items to the cart each time they visit a new page.

Form Data: You can use Local Storage to store form data that users have previously entered. This can help to speed up the form-filling process since users won't have to re-enter their information each time they visit the website.

Game Progress: If you have a game that users can play on your website, you can use Local Storage to store their progress. This can help to create a more engaging experience since users can pick up where they left off each time they visit the website.

Here's an example of how to use Local Storage with multiple values:

javascript
Copy code
// Store multiple values in Local Storage
localStorage.setItem('userSettings', JSON.stringify({ theme: 'dark', language: 'en', fontSize: 16 }));

// Retrieve the values from Local Storage
const userSettings = JSON.parse(localStorage.getItem('userSettings'));

// Update a single value in Local Storage
userSettings.theme = 'light';
localStorage.setItem('userSettings', JSON.stringify(userSettings));
In the example above, we're storing an object with multiple values in Local Storage using setItem(). We're then retrieving the values using getItem() and updating a single value before saving it back to Local Storage. Note that we're using JSON.stringify() and JSON.parse() to convert the object to a string and back again since Local Storage only supports string values.




Khushi Jain
setTimeout usecases
The setTimeout() function is used to execute a function or a piece of code after a specified delay (in milliseconds). Here are some common use cases for setTimeout():

Display a notification message after a certain time delay: You can use setTimeout() to display a notification message to the user after a certain time delay. For example, you can use the following code to display a notification message after 5 seconds:
javascript
Copy code
setTimeout(function() {
  alert('Hello World!');
}, 5000);
Execute a function after a certain time delay: You can use setTimeout() to execute a function after a certain time delay. For example, you can use the following code to execute a function after 5 seconds:
javascript
Copy code
setTimeout(function() {
  console.log('Function executed after 5 seconds.');
}, 5000);
Implement a typing effect: You can use setTimeout() to implement a typing effect where characters are displayed on the screen one by one after a certain time delay. For example, you can use the following code to implement a typing effect:
scss
Copy code
let text = 'Hello World!';
let index = 0;

function type() {
  document.getElementById('output').innerHTML += text.charAt(index);
  index++;

  if (index >= text.length) {
    clearInterval(timer);
  }
}

let timer = setInterval(type, 100);
In this example, the type() function uses setTimeout() to display each character of the text string on the screen one by one after a time delay of 100 milliseconds. The setInterval() function is used to call the type() function repeatedly until all the characters of the text string are displayed.

Implement a loading indicator: You can use setTimeout() to implement a loading indicator where a message is displayed to the user while the page is loading. For example, you can use the following code to display a loading message for 5 seconds:
javascript
Copy code
document.getElementById('loading').style.display = 'block';

setTimeout(function() {
  document.getElementById('loading').style.display = 'none';
}, 5000);
In this example, the setTimeout() function is used to hide the loading message after 5 seconds. The display property of the loading message is set to block to display the message and is set to none to hide the message.




Khushi Jain
setInterval usecases
setInterval is a method in JavaScript that repeatedly calls a function or executes a code snippet with a fixed time delay between each call. It can be used in a variety of ways, including:

Creating a clock or timer - setInterval can be used to create a timer or clock that updates the time every second or minute.
Example:

javascript
Copy code
let timer = setInterval(function() {
  let currentTime = new Date();
  console.log(currentTime);
}, 1000);
This will log the current time every second.

Animation - setInterval can be used to create animations on web pages by repeatedly updating the position of an element or changing its style.
Example:

javascript
Copy code
let element = document.getElementById("myElement");
let position = 0;
let animation = setInterval(function() {
  position += 10;
  element.style.left = position + "px";
  if (position >= 500) {
    clearInterval(animation);
  }
}, 50);
This will move the element to the right by 10 pixels every 50 milliseconds until it reaches a position of 500 pixels.

Sending periodic AJAX requests - setInterval can be used to periodically send AJAX requests to a server to update data on a web page.
Example:

javascript
Copy code
let data = [];
let request = setInterval(function() {
  $.ajax({
    url: "data.php",
    success: function(response) {
      data = response;
      updateUI(data);
    }
  });
}, 5000);
This will send an AJAX request to data.php every 5 seconds and update the UI with the response.

It is important to note that setInterval can cause performance issues if not used properly, such as causing excessive CPU usage and memory leaks. It should be used with caution and only when necessary.




Khushi Jain
Events - "DOMContentLoaded" usecases
The DOMContentLoaded event is fired when the initial HTML document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading. It is a useful event to use when you want to execute JavaScript code as soon as the document is ready.

Here are some use cases for DOMContentLoaded event:

Setting up initial page state: You can use the DOMContentLoaded event to set up the initial state of the page. For example, you could hide or show certain elements, disable or enable form controls, or set default values for fields.

Initializing JavaScript modules: If you have JavaScript modules that need to be initialized after the page loads, you can use the DOMContentLoaded event to trigger their initialization. This ensures that the modules are ready to be used as soon as the page is ready.

Loading external resources: You can use the DOMContentLoaded event to load external resources such as stylesheets, scripts, and images. This ensures that the resources are only loaded after the DOM is ready, which can improve page load times and prevent rendering issues.

Starting animations and transitions: If you have animations or transitions that need to start as soon as the page loads, you can use the DOMContentLoaded event to trigger them. This ensures that the animations or transitions start at the right time and don't cause visual glitches or delays.

Overall, the DOMContentLoaded event is a powerful tool for ensuring that your JavaScript code runs as soon as the DOM is ready, which can improve page load times, prevent rendering issues, and provide a better user experience.




Khushi Jain
Events - "load" usecases
The "load" event is fired when a web page and all its resources have finished loading. It can be used for various purposes, such as:

Displaying a loading indicator until all the content has been loaded.
Starting an animation or slideshow when the page is fully loaded.
Executing a script that depends on a specific element being fully loaded and rendered on the page.
Measuring page load time for performance optimization purposes.
Modifying the layout or content of the page based on the size and dimensions of the loaded resources (images, videos, etc.).
Here is an example of how to use the "load" event to display a loading indicator until all the content has been loaded:

html
Copy code
<!DOCTYPE html>
<html>
<head>
  <title>Load Event Example</title>
  <style>
    .loading {
      display: block;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 3em;
    }
  </style>
</head>
<body>
  <div class="loading">Loading...</div>
  <img src="image.jpg" alt="Image">
  <script>
    window.addEventListener('load', function() {
      // Hide the loading indicator
      document.querySelector('.loading').style.display = 'none';
    });
  </script>
</body>
</html>
In this example, the "load" event is attached to the window object using the addEventListener method. When the event is fired, the callback function hides the loading indicator by setting its display style property to "none".




Khushi Jain
Events - "scroll" usecases
The scroll event is triggered when the user scrolls an element, such as a webpage, using the mouse wheel, touchpad, or keyboard. Here are a few use cases of the scroll event:

Infinite scrolling: The scroll event can be used to implement infinite scrolling, where new content is loaded as the user scrolls down the page. When the user reaches the bottom of the page, the event is triggered, and the next set of content can be loaded.

Scroll-based animations: The scroll event can be used to create animations that are triggered by scrolling. For example, as the user scrolls down the page, an image or text can be animated to appear or disappear.

Parallax effects: The scroll event can be used to create parallax effects, where different layers of content move at different speeds as the user scrolls.

Sticky navigation: The scroll event can be used to create a sticky navigation menu that sticks to the top of the page as the user scrolls down.

Lazy loading: The scroll event can be used to implement lazy loading, where images or other resources are only loaded when they are visible in the viewport. When the user scrolls down the page, the event is triggered, and the next set of images can be loaded.

Overall, the scroll event is a useful tool for creating interactive and dynamic web pages that respond to user input.




Khushi Jain
Width, Height, GetBoundingClientRect usecases
The width and height properties in JavaScript are used to get the width and height of an element, respectively. These properties can be used to manipulate the size of an element dynamically using JavaScript.

For example, to set the width of an element with the ID myElement to 200 pixels, you can use the following code:

arduino
Copy code
document.getElementById("myElement").style.width = "200px";
The getBoundingClientRect() method returns the size of an element and its position relative to the viewport. This method returns a DOMRect object, which contains the following properties:

x and y: the coordinates of the element's top-left corner relative to the viewport.
width and height: the dimensions of the element.
top, right, bottom, and left: the distances between the element's edges and the corresponding edges of the viewport.
This method is particularly useful when you need to calculate the position of an element relative to the viewport, for example, when implementing a parallax effect.

Here's an example of using getBoundingClientRect() to get the dimensions and position of an element with the ID myElement:

arduino
Copy code
const element = document.getElementById("myElement");
const rect = element.getBoundingClientRect();
console.log(rect.width, rect.height, rect.x, rect.y);



Khushi Jain
Events - "resize" usecases
The resize event is triggered when the size of the browser window or an element is changed. Some use cases of the resize event are:

Responsive design: When designing a website or application that needs to adapt to different screen sizes, the resize event can be used to dynamically adjust the layout based on the window size.

Updating content: When the size of an element changes due to resizing, its content may need to be updated accordingly. For example, if a container div gets bigger, the text inside it may need to wrap differently or images may need to resize.

Animations: The resize event can be used to trigger animations or effects that are tied to changes in element size. For example, an image gallery may animate the transition between images when the window is resized.

Here is an example of using the resize event to update the size of an element dynamically:

html
Copy code
<!DOCTYPE html>
<html>
<head>
  <style>
    #box {
      width: 200px;
      height: 200px;
      background-color: red;
    }
  </style>
</head>
<body>
  <div id="box"></div>
  <script>
    window.addEventListener('resize', function() {
      var box = document.getElementById('box');
      var rect = box.getBoundingClientRect();
      box.style.width = rect.width + 10 + 'px';
      box.style.height = rect.height + 10 + 'px';
    });
  </script>
</body>
</html>
In this example, the resize event is used to increase the size of a red box element by 10 pixels in both width and height each time the window is resized. The getBoundingClientRect method is used to get the current dimensions of the box element.

Counter HTML
Preview
02:25
Counter JS
11:14
Reviews HTML
Preview
04:45
Reviews JS
22:40
Navbar HTML
Preview
02:48
Navbar General Concepts
04:08
Navbar JS
07:56
Sidebar HTML
Preview
03:44
Sidebar Manual Setup
03:07
Sidebar JS
05:51
Modal HTML
Preview
03:39
Modal Challange
02:42
Modal JS
03:02
Questions HTML
Preview
07:14
Questions General Concept
02:54
Questions JS - Traversing the DOM
07:32
Questions JS - Using Selectors Inside the Element
10:19
Menu HTML
Preview
06:56
Display Items When Page Loads
14:39
Refactor
03:12
Filter Buttons HTML
01:57
Filter Buttons JS
11:42
Dynamic Filter Buttons
04:01
Unique Categories
07:29
Dynamic Filter Buttons Complete
09:40
Video Intro
Preview
01:12
Video HTML
02:44
Video Overlay Setup
02:42
Video JS
04:59
Video Preloader
04:51
Scroll Intro
Preview
03:31
Scroll HTML
10:37
Scroll - Setup Date
02:11
Scroll - Toggle Simple Setup
06:16
Scroll - Toggle Dynamic
10:44
Scroll - Fixed Navbar
08:50
Smooth Scroll Setup
10:23
Smooth Scroll Complete
10:53
Tabs HTML
Preview
11:42
Tabs JS
10:56
Countdown HTML
Preview
05:53
Set Date
19:51
Calculate Remaining Time
27:47
Time From Now
04:10
Lorem Ipsum HTML
Preview
04:26
Lorem Ipsum JS
17:20
GroceryBud - Intro
Preview
03:22
GroceryBud - HTML
05:09
GroceryBud - Select Elements
03:13
GroceryBud - addItem Setup
07:26
GroceryBud - truthy shortcut
03:32
GroceryBud - display alert
05:29
GroceryBud - addItem
08:49
GroceryBud - setBackToDefault
02:34
GroceryBud - clear items
06:54
GroceryBud - select edit and delete buttons
07:23
GroceryBud - delete item
07:18
GroceryBud - edit item
11:16
GroceryBud - localStorage info
04:25
GroceryBud - addToLocalStorage
08:38
GroceryBud - removeFromLocalStorage
05:39
GroceryBud - editLocalStorage
04:46
GroceryBud - load items from localStorage
06:49
Slider Intro
Preview
01:29
Slider HTML
03:34
Slider General Concepts
05:14
Slider JS Setup
03:27
Slider JS - Slides Approach
06:06
Slider JS - Button Approach

Netlify Intro
01:08
Drag and Drop Option
03:32
Continuous Deployment


Intro
02:10
Object Basics
06:13
Nested Objects, Bracket Notation
11:59
'this' - Keyword Basics
08:20
"this" - Keyword Advanced
07:10
Factory Functions
06:42
Constructor Functions
07:48
Constructor Property
04:51
Prototype Property
09:58
Property Lookup
05:45
ES6 Class Syntax
12:14
Call
09:42
Apply, Arguments
05:42
Bind
02:15
Button Example

Intro
Preview
02:09
Setup
01:47
Counter - HTML
03:10
Counter Setup
07:56
Counter - Select Elements
05:13
Counter - Functions
04:05
Counter - Complete
05:43
Counter - Class Refactor
03:43
Gallery Intro
01:08
Gallery - HTML
09:24
Gallery - Select Elements
06:37
Gallery - Open Modal Setup
12:10
Gallery - Open Modal Complete
12:06
Gallery - Close Modal
06:31
Gallery - Prev and Next
05:22
Gallery - Select Images
05:30
Gallery - Class Refactor

Intro
00:18
IIFE
08:59
Hoisting
06:26
Closure
08:28
Closure - Basic Example
03:53
Closure - Complete Example

ES6 Module Intro
02:20
VAR, LET, CONST
06:07
Function Scope and Block Scope
10:18
Template Strings
03:43
Template Strings - HTML
05:25
Tagged Template Literals
11:08
Arrow Functions - Basics
14:16
Arrow Functions - Objects and "this"
06:55
Arrow Functions - Select Elements and "this"
04:47
Default Parameters and Hoisting Gotchas
03:50
Array Destructuring
05:24
Swap Variables
02:39
Object Destructuring
05:03
Destructuring Function Parameters
03:01
New String Methods
07:32
"for of" - Loop
03:59
Spread Operator - Basics
05:26
Spread Operator - Objects
03:01
Spread Operator - DOM Elements
03:27
Spread Operator - Functions Arguments
03:38
Rest Operator
10:36
Array.of
02:06
Array.from - Strings and Arguments Object
04:34
Array.from - DOM Elements(NodeList)
07:00
find, findIndex,every,some
08:59
"for in" - Loop
01:44
Object.keys()
01:15
Object.values()
00:26
Object.entries()
04:40
new Set() - General Overview
04:21
new Set() - Use Case
06:02
String includes()
05:31
Array includes()
03:08
Important Info

Projects - Intro
00:40
Numbers - Intro
00:23
Numbers - Setup
00:36
Readme
00:50
Numbers - HTML Structure
03:09
Numbers - Select Elements
04:25
Numbers - Initial Variables
03:20
Numbers - Complete
06:54
Dark Mode - Intro
00:59
Dark Mode - Setup
00:27
Dark Mode - HTML Structure
03:41
Dark Mode - Toggle CSS
07:09
Dark Mode - Import Data
03:26
Dark Mode - Render Items
04:21
Dark Mode - Moment.js
06:21
Filters - Intro
01:48
Filters - HTML Structure
06:47
Filters - Display Products
07:59
Filters - Text Filter
09:40
Filters - Let and Original Array
04:40
Filters - Empty Array
03:27
Filters - Display Buttons
06:12
Filters - Buttons Filter

Intro
02:31
Setup
06:47
Named Export
05:54
Default Export
08:48
Get Element

Intro
00:54
Synchronous
03:33
Recipe Example
04:54
Asynchronous
12:21
Callback Hell
10:44
Callback Hell - DOM Example
10:24
Promises
10:45
Important Unsplash API update !!!!
00:14
Reject Example
20:05
Promises - DOM Example
13:32
Async/Await

Intro
01:06
AJAX, HTTP, API
04:32
Simple Text
26:33
Add Button
05:15
JSON
16:55
Fetch
09:59
Fetch - Errors "gotcha"
02:02
Fetch - Big Picture
01:55
Fetch with Function
06:35
Fetch - with async/await
04:34
Try / Catch

AJAX Projects - Intro
01:03
Dad Jokes - Intro
00:10
Dad Jokes - HTML Structure
01:37
API Fundamentals
03:29
Dad Jokes - Docs
04:50
Dad Jokes - Select Elements
01:40
Dad Jokes - Fetch Random Joke
08:39
Dad Jokes - Loading
01:58
Dad Jokes - Try / Catch
01:48
Dad Jokes - Throw New Error
06:28
Products - Intro
00:33
Products - HTML Structure
07:39
Products -Possible AJAX States
04:01
Products - API Docs
03:28
Products - Fetch Products
03:34
Products - Loading and Error
03:50
Products - Start Function
05:02
Products - Display Products
11:57
Products - Query Params
05:47
Products - Single Product HTML
05:25
Products - Initial Logic
04:31
Products - Fetch Product
08:04
Products - Display Single Product
05:38
Products - Display Colors
03:06
Random User - Intro
Preview
01:18
Random User - HTML
10:06
Random User - API
04:44
Random User - Select Elements
14:37
Random User - Fetch User
20:46
Random User - Display User
18:28
Cocktails - Intro
Preview
01:14
Cocktails - Setup
02:51
Cocktails - HTML
09:49
Cocktails - API
07:36
Cocktails - Present Drinks
05:35
Cocktails - Fetch Drinks
05:07
Cocktails - Display Drinks
16:08
Cocktails - Search Form
10:26
Cocktails - Loading
06:56
Cocktails - Set Drink
14:43
Cocktails - Single Drink HTML
03:34
Cocktails - Single Drink
10:40
Cocktails - Display Single Drink

More Projects - Intro

Intro
Preview
00:23
Starter Project
00:11
HTML Setup
06:47
Display People
12:53
Apply CSS
07:11
Next Slide
07:35
Next Slide - End of Array
02:27
Prev Slide

Intro
Preview
01:39
Starter Project
00:11
HTML
09:10
Sidebar Toggle
09:50
Sidebar Complete
11:47
Submenu Setup
12:36
Submenu Links
06:38
Submenu - Hide and Column Layout

Intro
01:04
Starter Project
Preview
00:10
Setup
03:35
Fetch Followers
05:10
Display Followers
10:21
Paginate - Create Pages
12:54
Display Buttons
14:44
Button Functionality

Intro
01:16
HTML Structure
04:01
API Docs
04:33
Initial Setup
04:55
Fetch Pages
05:38
Render Results

Intro
Preview
03:59
About
03:29
Starter Project
00:21
Setup
01:56
Starter Overview
03:35
Navbar, Hero - HTML
07:50
Sidebar HTML
06:13
Sidebar Toggle
08:59
Cart HTML
10:31
Cart Toggle
08:18
About Page
06:51
API Overview
07:33
Featured Products - HTML
09:26
Fetch Products
08:20
Setup Store
11:11
Exports - Alternative Syntax
02:50
LocalStorage
09:09
Featured Products
01:42
Display Products
08:30
Format Price
10:19
AddToCart Setup
06:16
Product HTML
04:12
Display All Products
02:36
Page Loading
03:30
Filters HTML
04:07
Search Filter
15:08
Companies Filter
15:13
Price Filter
13:04
Single Product - Overview
03:29
Single Product - HTML
08:11
Single Product - Initial JS
05:41
Single Product - Fetch Product
04:21
Single Product - Fetch Error
09:25
Single Product - Complete
13:07
setupCart - Initial Setup
09:43
addToCart - Setup
11:22
addToCartDOM
08:32
addToCart - Totals
09:33
setupCart - init
07:42
Cart - Update Items
10:28
Cart - Remove Item
09:45
Cart - Increase Amount
03:25
Cart - Decrease Amount
05:40
Products Page Fix
06:09
Bug Fix 2
05:47
Finished Project

Bonus
