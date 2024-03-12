# [Javascript](https://launchschool.com/books/javascript/read/introduction)

## Introduction

### A brief Javascript History

- 2008: Google's open-source Chrome V8: a high-performance JavaScript Engine.
- Ryan Dahl's Node.js: cross-platform environment.

### Javascript's Future

### Abstraction

- It can go lower or higher
  - lower is writing for the computer
  - higher is writing libraries and frameworks for the user/dev.

### Who this book is for

- beginners

### What's not covered

- The DOM API
- Asynchronous programming
- Object-Oriented Javascript
- Testing

### How to read this book

- Code along

## Preparations

### Runtime Environments

- Mainly node.js and the browser.

#### Application Programming interface

- When an app reahes into an operating system's resources, this API makes sure that it happens in a safe way.
- It outlines a scheme and format that the dev can use to securely access resouces with the Operating System being the mediary between them.
- Compiler + Operating system's API = runtime environment

##### Browser

- Almost every browser has a Javascript engine built in.
- JS in the browser has 2 main purposes:
  - To change web-pages based on the user actions
  - To exchange messages with a server over a network.
- Main JS enviroment A:
  - The original.
  - Does 2 things:
    - change web-pages as the user manipulates it
      - Needs an API for this, to change a HTML page.
    - Exchange messages with a server.
      - Needs an API for this, to use the operating system's ability to send and receive messages over a network.
- Almost all browsers do this, but not necessarily in a compatible way.
- This is where dev-tools come in. All major browsers provide  this feature which includes a:
  - REPL
  - Debugger
  - Network Inspector
  - Performance profiler
  - and more...

##### Node.js

- Node.js:
  - This turns JavaScript into a general purpose programming language, which can runs apps on almost any system.
  - It needs at a minimum to do these:
    - read/write disk files
    - read/write via the terminal
    - send/receive messages over a network
    - interact with a database
- Main JS enviroment B:
  - A "runtime environment" (do i know what that is, well enough to explain it to a 4 year old?) that turns JS into a programming-language that can run basically anywhere.
  - A programming environment (like node.js) must be able to:
    - read/write disk files
    - read/write via the terminal
    - send/receive messages over a network
    - interact with a database.

##### Other Javascript runtime environments

- Adobe's Acrobat
- Actionscript
- GNOME shell

### Installation

- `node -v` -> v21.6.2
- npm -v` -> 10.2.4

### Using a code editor

- Use VSCode

### Stylish JavaScript

- `//` for comments
- `/*` for multiline comments or mid-line comments
- Spacing on curly braces is like normal blocks:

<img width="687" alt="Screenshot 2024-03-01 at 07 39 57" src="https://github.com/SandyRodger/launch_school_books/assets/78854926/b0e63e29-9e6d-471f-a6ab-c1dc719cde84">

### Naming Conventions

- camelCase for var and function names ie: `let answerToUltimateQuestion = 42;`
- Which is different from CamelCase (AKA PascalCase) for constructor functions

<img width="675" alt="Screenshot 2024-03-01 at 07 44 28" src="https://github.com/SandyRodger/launch_school_books/assets/78854926/18037797-cb36-44b1-9cf4-a7904db7daec">

- SCREAMING_SNAKE_CASE for constants and "magic-numbers"

### On semicolons

- JS will input these invisibly, but you should be explicit, because if JS puts them somewhere you didn't want them it cna cause bugs. 

### The command Line
 
 - Just a primer

#### Command line commands

- I know all this.

#### The Node REPL

- `console.log('Hello, world!')`
- Node prints return values in grey.
- Exit with ctrl-d or ctrl-c twice

### Running JavaScript

- `node example.js`
- When you run code from your command line it gets executed bny the interpreter, which takes JS code and makes it readable to the computer.
- ctrl-c your way out of infinite loops.

#### Running Javascript in the browser

- You have to embed the JS in an HTML file.

### The chrome console

- it's, among other things, a REPL.

### Documentation

- Programming environments provide 2 main types of reuseable code:
  - The standard library:
    - components and operations that make up the core language
  - Components and operations specific to one runtime environemnt.
- We're just going to deal with the first one.
- Offical docs : [ECMA International](https://ecma-international.org/publications-and-standards/standards/ecma-262/)
- [Standards docs](https://ecma-international.org/publications-and-standards/standards/ecma-262/)
- MDN = [Mozilla Development Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript) (not always reliable)

#### Constructors and Type names

- Constructors are little factories that output values of that type
- String: Uses PascalCase

#### Method names

- call methods on objects:
  - `'xyzzy'.toUpperCase()`
- Instance methods
- Static methods

#### Property name

- `"hello".length` => 5
- Instance method v static method:
  - `'Hello, '.concat('Bob!')` => 'Hello, Bob!'`
  - `String.fromCharCode(97)` => 'a'

#### Searching for documentation online

- precede your search wiht 'mdn'

### About the Exercises

- Yup

### Exercises

1. tick
2. tick
3. tick
4. 
```node
> let foo = "bar";
undefined
> console.log(foo);
bar
undefined
> foo;
'bar'
```

```console
let foo = "bar";
console.log(foo);
foo;
bar
'bar'
```

5.
- `String.prototype.substring()` = Instance
- `Object.create()` = Static
- `String.fromCharCode()` (static)
- `Array.prototype.slice()` (instance) OR String
- `Date.prototype.toString()` (instance)

6. Valid variable names? camelCase (letters, nums and underscores only)

- index : Yes
- CatName : No - catName (pascal case)
- snake_case : No - snakeCase (snake case)
- lazyDog - yes
- quick_Fox : no - quickFox
- 1stCharacter : no - firstCharacter (nums are allowed, but not in first place)
- operand2 : yes
- BIG_NUMBER : No - bigNumber (screaming snake case)

7. Valid function name? 

- index : yes
- CatName : yes (constructor functions are allowed to use Pascal case)
- snake_case : No - SnakeCase or snakeCase
- lazyDog : yes
- quick_Fox : No - quickFox or QuickFox
- 1stCharacter : No FirstCharacter or firstCharacter
- operand2 : Yes
- BIG_NUMBER : No - BigNumber or bigNumber

8. Valid constant name ? 

- index : no
- CatName : no
- snake_case : no
- lazyDog : no
- quick_Fox : no
- 1stCharacter : no
- operand2 : no
- BIG_NUMBER : yes

9.
- snake_case
- quick_Fox
- 1stCharacter

## The Basics

### DataTypes

- 5 primitive data-types
  - String
  - Number
  - Undefined
  - Null
  - Boolean
- 6 Data-type literals
  - String literals
  - Numeric literals
  - Boolean literals
  - Object literals
  - Array literals
  - Undefined

#### Strings
#### Numbers
#### Booleans
#### Undefined
#### Null
#### The typeof Operator

- `typeof 1` => `'number'`
- `typeof true` => `'boolean'`
- `typeof null` => `'object'`  ?! This is an original error, now too deeply coded in to change.
- `typeof [1, 2, 3]` => `'object'`

### Arithmetic Operators

#### Adding, subtracting and multiplying numbers

- Same as ruby
- EXCEPT `%` isn't modulo. THere's an edge-case difference which is:
  - remainder (in JS) returns positive when the 1st operand is opsitive, and negative if 1st is negative. Modulo is this for the 2nd operand.
  - So if either number is negative - bear this in mind. Otherwise, forget it. 

### NaN

- Not A Number
- `typeof NaN` => `'number'`, because this error is the result of numbers.
- `NaN` is a mathematical term and different to JS `undefined`.
- `NaN` is the only thing in JS that is not equal to itself.
- You can use `Number. isNaN` or `Object.is`

### Infinity and -Infinity

- Practically there's little difference between NaN and Imfinity, but they are very different ideas.
- `1/0 = Infinity`
- It does odd things:

```
> Infinity * Infinity
= Infinity

> Infinity + Infinity
= Infinity

> Infinity - Infinity
= NaN

> Infinity / Infinity
= NaN

> 1234567890 / Infinity
= 0
```
- There is also -Infinity, which is the result of `-1/0`
- Use `===` to determine whether a value is infinity or not

### Equality Comparison

```
> 42 === 42
= true

> 42 === 43
= false

> 'foo' === 'foo'   // It works with strings too
= true

> 'FOO' === 'foo'   // Case is different
= false
```

- It's like `==` in Ruby. The JS `==` is weird.

### String Concatenation

```
> 'foo' + 'bar'
= 'foobar'

> '1' + '2'
= '12'

> '1' + 2
= '12'
```

#### Implicit type coercion

- In JS Anything plus string = string
- Any other arithmetic operation results in a number

### Explicit Coercion

- `Number('1')` => 1
- `Number('foo')` => NaN
- `parseInt('12')` => NaN

```
> parseInt('12xyz')
= 12

> parseInt('3.1415')
= 3

> parseFloat('12.5foo')
= 12.5
```

- If the int is longer than about 300 digits, JS can't handle it and returns Infinity.

#### Numbers to strings

```
> String(20)
= '20'
```

### Data Structures

#### Arrays

- access elements like this `[1, 2, 3, 4, 5][0]`
- You can and should use trailing commas:

```
[
  "Eric Idle",
  "John Cleese",
  "Terry Gilliam",
  "Graham Chapman",
  "Michael Palin",
  "Terry Jones",
]
```
#### Objects

```
> { dog: 'barks' }
= { dog: 'barks' }
> { dog: 'barks', cat: 'meows', pig: 'oinks' }
= { dog: 'barks', cat: 'meows', pig: 'oinks' }
> ({ dog: 'barks', cat: 'meows', pig: 'oinks' })['cat']
= 'meows'
```

```
{
  title: "Monty Python's Flying Circus",
  cast: [
    "Eric Idle",
    "John Cleese",
    "Terry Gilliam",
    "Graham Chapman",
    "Michael Palin",
    "Terry Jones",
  ],
  firstSeason: 1969,
  lastSeason: 1974,
}
```

### Expressions and return values

### Statements

### Exercises

1.

```
> let first = "Sandy"
undefined
> let space = " "
undefined
> let last = "Rodger"
undefined
> first + space + last
'Sandy Rodger'
```

2. `Number(String(4936)[3])`

3. 

- 'true' = string
- false = Boolean
- 1.5 = Number
- 2 = Number
- undefined = Undefined
- { foo: 'bar' } = Object

4. ` console.log('5' + 10);` logs '510' instead of 15 because using + where the first operand is a string implicitly coerces the other operand into a string. 

5. `console.log(Number(5)+Number('10'))`

"two incomensurate date-types"

6.
```
> console.log('The value of 5 + 10 is ' + Number('5') + 10)
The value of 5 + 10 is 510

> console.log(`The value of 5 + 10 is ${Number('5') + 10}.`);
The value of 5 + 10 is 15.
```

7. returns 'undefined'

```
let foo = ['a', 'b', 'c'];
console.log(foo.length);  // => 3
console.log(foo[3]);      // will this result in an error?
```

8. `names = ['ab', 'ac', 'ad', 'ae', 'af'];`
9. 'namesObj = {ab: 1, ac: 2, ad:3, ae: 4, af:5}
10. False ("Strict equality operator")
11. 3
12. true, strings are compared digit by digit.

## Variables
### Variables and Variable Names
#### Variable naming
#### What else is a variable ?
### Variables and Variable Names 
### Declaring and Assigning Variables

- "initializer"
- expresions return values, statements don't

### Declaring Constants


### Variable Scope

- block scoped

### A Common Gotcha

- missing out let or var - this has myriad strange consequences, like global scope.

### Summary

### Exercises

- done in VSC

## Input/Output

### Command Line output

- get package.json with
  - `npm init -y`
  - `npm install readline-sync --save`

### Command Line Input

- 

### Input in the Browser

```
<!DOCTYPE html>
<html>
<head>
  <title>Testing Prompt</title>
</head>
<body>
  <script src="personalized_greeting_browser.js"></script>
</body>
</html>
```

### Summary
### Exercises

- Done

## Functions

### Using Functions

### Arguments & Parameters

- 

### Return Values

- "predicates" : methods that always return booleans.

### Default Parameters

- Same as Ruby

### Nested Functions

- 

### Functions & Scope

#### Global variables

#### Local Variables

### Functions vs. Methods

- `'xyzzy'.toUpperCase()`
- `functionName(obj)`

### Reassignment and Mutation

- 

### Mutating the Caller

- 

### Function Composition

- 

### Three Ways to Define a Function

 Function declaration. (You can call it before declaring it)

```
greetPeople();

function greetPeople() {
  console.log("Good Morning!");
}
```

2. Function expression:
  - just, saving the function in a var.
  - Can't be called before declared.
  - JS functions are "first-class functions", which means we can assign function expressions to variables. I THINK?!

```
let greetPeople = function () {
  console.log("Good Morning!");
};

greetPeople();
```

  - Any expression that doesn't have the word `function` right at the beginning is a function expression. Even this:

```
(function greetPeople() { // This is a function expression, not a declaration
  console.log("Good Morning!");
});
```

3. Arrow function

```
let add = (a, b) => a + b;
let getNumber = (text) => {
  let input = prompt(text);
  return Number(input);
};

let number1 = getNumber("Enter a number: ");
let number2 = getNumber("Enter another number: ");
console.log(add(number1, number2));
```

### The Call Stack

- like Ruby

### Summary
### Exercises


## Flow Control
## Loops & Iterating
## Arrays
## Objects
## More Stuff
## Conclusions
