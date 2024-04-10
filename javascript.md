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
- `Array.prototype.slice()` Array or String = instance
- `Date.prototype.toString()` = Sting/Object/Array/Number = instance

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
- NaN is not equal to itself.

## Variables
## Input/Output
## Functions
## Flow Control
## Loops & Iterating
## Arrays
## Objects
## More Stuff
## Conclusions
![Uploading image.png…]()
