# [Javascript](https://launchschool.com/books/javascript/read/introduction)

## Introduction

### A brief Javascript History

- 2008: Google's open-source Chrome V8: a high-performance JavaScript Engine.
- Ryn Dahl's Node.js: cross-platform environment.

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
- Browser:
  - Almost every browser has a Javascript engine built in.
  - JS in the browser has 2 main purposes:
    - To change web-pages based on the user actions
    - TO exchange mesages with a server over a network.
- Node.js:
  - This turns JavaScript into a general purpose programming language, which can runs apps on almost any system.
  - It needs at a minimum to do these:
    - read/write disk files
    - read/write via the terminal
    - send/receive messages over a network
    - interact with a database
- Other JavaScript Runtime environemnets:
  - Adobe's Acrobat
  - Actionscript
  - GNOME shell

#### Application Programming interface

### Installation

### Using a code editor

### Stylish JavaScript

- `//` for comments
- `/*` for multiline comments or mid-line comments
- Spacing on curly braces is like normal blocks:

<img width="687" alt="Screenshot 2024-03-01 at 07 39 57" src="https://github.com/SandyRodger/launch_school_books/assets/78854926/b0e63e29-9e6d-471f-a6ab-c1dc719cde84">

### Naming Conventions

- camelCase for var and function names ie: `let answerToUltimateQuestion = 42;`
- Which is different from CamelCase (AKA PascalCase) for constructor functions

<img width="675" alt="Screenshot 2024-03-01 at 07 44 28" src="https://github.com/SandyRodger/launch_school_books/assets/78854926/18037797-cb36-44b1-9cf4-a7904db7daec">

- SCREAMING_SNAKE_CASE 

### On semicolons

### The command Line

#### Command line commands
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

## The Basics
## Variables
## Input/Output
## Functions
## Flow Control
## Loops & Iterating
## Arrays
## Objects
## More Stuff
## Conclusions
