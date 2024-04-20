# [Javascript](https://launchschool.com/books/javascript/read/introduction)

## [Introduction](https://launchschool.com/books/javascript/read/introduction)

### [A brief Javascript History](https://launchschool.com/books/javascript/read/introduction#briefhistory)

- 2008: Google's open-source Chrome V8: a high-performance JavaScript Engine.
- Ryan Dahl's Node.js: cross-platform environment.

### [Javascript's Future](https://launchschool.com/books/javascript/read/introduction#javascriptsfuture)

### [Abstraction](https://launchschool.com/books/javascript/read/introduction#abstraction)

- It can go lower or higher
  - lower is writing for the computer
  - higher is writing libraries and frameworks for the user/dev.

### [Who this book is for](https://launchschool.com/books/javascript/read/introduction#whothisbookisfor)

- beginners

### [What's not covered](https://launchschool.com/books/javascript/read/introduction#whatsnotcovered)

- The DOM API
- Asynchronous programming
- Object-Oriented Javascript
- Testing

### [How to read this book](https://launchschool.com/books/javascript/read/introduction#howtoreadthisbook)

- Code along

## [Preparations](https://launchschool.com/books/javascript/read/preparations)

### [Runtime Environments](https://launchschool.com/books/javascript/read/preparations#runtimeenvironments)

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

### [Installation](https://launchschool.com/books/javascript/read/preparations#installation)

- `node -v` -> v21.6.2
- npm -v` -> 10.2.4

### [Using a code editor](https://launchschool.com/books/javascript/read/preparations#usingacodeeditor)

- Use VSCode

### [Stylish JavaScript](https://launchschool.com/books/javascript/read/preparations#stylishjavascript)

- `//` for comments
- `/*` for multiline comments or mid-line comments
- Spacing on curly braces is like normal blocks:

<img width="687" alt="Screenshot 2024-03-01 at 07 39 57" src="https://github.com/SandyRodger/launch_school_books/assets/78854926/b0e63e29-9e6d-471f-a6ab-c1dc719cde84">

### [Naming Conventions](https://launchschool.com/books/javascript/read/preparations#namingconventions)

- camelCase for var and function names ie: `let answerToUltimateQuestion = 42;`
- Which is different from CamelCase (AKA PascalCase) for constructor functions

<img width="675" alt="Screenshot 2024-03-01 at 07 44 28" src="https://github.com/SandyRodger/launch_school_books/assets/78854926/18037797-cb36-44b1-9cf4-a7904db7daec">

- SCREAMING_SNAKE_CASE for constants and "magic-numbers"

### [On semicolons](https://launchschool.com/books/javascript/read/preparations#onsemicolons)

- JS will input these invisibly, but you should be explicit, because if JS puts them somewhere you didn't want them it cna cause bugs. 

### TThe command Line](https://launchschool.com/books/javascript/read/preparations#thecommandline)
 
 - Just a primer

#### Command line commands

- I know all this.

#### The Node REPL

- `console.log('Hello, world!')`
- Node prints return values in grey.
- Exit with ctrl-d or ctrl-c twice

### [Running JavaScript](https://launchschool.com/books/javascript/read/preparations#runningjavascript)

- `node example.js`
- When you run code from your command line it gets executed bny the interpreter, which takes JS code and makes it readable to the computer.
- ctrl-c your way out of infinite loops.

#### Running Javascript in the browser

- You have to embed the JS in an HTML file.

### [The chrome console](https://launchschool.com/books/javascript/read/preparations#thechromeconsole)

- it's, among other things, a REPL.

### [Documentation](https://launchschool.com/books/javascript/read/preparations#documentation)

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

### [About the Exercises](https://launchschool.com/books/javascript/read/preparations#aboutexercises)

- Yup

### [Preparations Exercises](https://launchschool.com/books/javascript/read/preparations#exercises)

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

## [The Basics](https://launchschool.com/books/javascript/read/basics)

### [DataTypes](https://launchschool.com/books/javascript/read/basics#datatypes)

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

### [Arithmetic Operators](https://launchschool.com/books/javascript/read/basics#arithmeticoperations)

#### Adding, subtracting and multiplying numbers

- Same as ruby
- EXCEPT `%` isn't precisely equivalent to modulo. There's an edge-case difference which is:
  - remainder (in JS) returns positive when the 1st operand is po  sitive, and negative if 1st is negative. Modulo is this for the 2nd operand.
  - So if either number is negative - bear this in mind. Otherwise, forget it. 

### [NaN](https://launchschool.com/books/javascript/read/basics#nan)

- Not A Number
- `typeof NaN` => `'number'`, because this error is the result of numbers.
- `NaN` is a mathematical term and different to JS `undefined`.
- NaN is not equal to itself.

### [Infinity and -Infinity](https://launchschool.com/books/javascript/read/basics#infinity)

- It's a number, it does unexpected things

### [Equality comparison](https://launchschool.com/books/javascript/read/basics#equalitycomparison)

- `===`
- For now, avoid `==`

### [String concatenation](https://launchschool.com/books/javascript/read/basics#stringconcatenation)

- `'foo' + 'bar'`
- `'1' + 2` => 12 (num plus string add as a number)

### [Explicit coercion](https://launchschool.com/books/javascript/read/basics#explicitcoercion)

- Implicit lets the engine choose how to coerce the objects. Explicit coercion is where you choose.

#### Strings to numbers

- `Number('1')` => 1
- `Number('foo')` => NaN (No error message!)
- Also available is `ParseInt('12')`, which ignores invalid characters.
  - `ParseInt('12xyz')` => 12
  - `ParseInt('3.1315')` => 3
- Javascript cannot represent numbers longer than 300 digits, so above that `ParseInt` will return `Infinity`
- `ParseFloat` is also a thing.

#### Numbers to Strings

- `String(20)` => '20'

### [Data Structures](https://launchschool.com/books/javascript/read/basics#datastructures)

- "data structures" AKA "complex data types"
- 2 most common:
  - Arrays
  - Objects

#### Arrays

- Same as Ruby? To begin with, but then...
  - `[1, 2, 3, 4, 5][0]` => 1  (Unlike Ruby, index numbers can't be negative)
- We can also write them like this: (the trailing comma is common practice)

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

- In Ruby these would be called hashes.
- Keys are always strings, but they look like this `dog:`.
  - `{ dog: 'barks' }`
- Items in an object are not ordered. So we retrieve values by the key, not the index.
  - `({ dog: 'barks', cat: 'meows', pig: 'oinks' })['cat']` => meows
 
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

- Rememeber you set keys to retrieve values.

### [Expressions and Return Values](https://launchschool.com/books/javascript/read/basics#expressionsandreturnvalues)

- Expression are what you write at the `>` prompt.
- Almost everything you write in JS is an expression.
-  Even without operators, it's an expression:
  -  `"hi"` => 'hi'

#### Printing (logging) vs returning values

- I know this from Ruby...

```
> console.log('Howdy')
Howdy
= undefined
```

### [Statements](https://launchschool.com/books/javascript/read/basics#statements)

- Not an expression, but often contains expressions:
  - `let foo = 3;` This is a statement, but `3` is an expression. If you use `foo` later, it will be an expression.
  - KEY DIFF: CAN'T CAPTURE A VALUE FROM A STATEMENT :
    - `console.log(3 * 5);` => 15
    - `console.log(let answer = 3 * 5);` => Error

#### Statements in Practice

- "A statement is a line of code commanding a task. Every program consists of a sequence of statements".
- There is some quibbling about what constitutes a statement, but LS will use the term more loosely, so don't worry about it.
- Just remember: Expressions can be part of a statement, but not all statements can be part of an expression.

### [Summary](https://launchschool.com/books/javascript/read/basics#summary)

### [Exercises](https://launchschool.com/books/javascript/read/basics#exercises)

1. `'Sandy' + ' ' + 'Rodger'`
2.  (Gross, but not a million miles away from LS solution)

```
let num = 4936

rightmost_digit = num % 10
console.log(rightmost_digit)

let num2 = (num - rightmost_digit) / 10

rightmost_digit = num2 % 10
console.log(rightmost_digit)

let num3 = (num2 - rightmost_digit) / 10

rightmost_digit = num3 % 10
console.log(rightmost_digit)

let num4 = (num3 - rightmost_digit) / 10

rightmost_digit = num4 % 10
console.log(rightmost_digit)

```

3. 

- String
- Boolean
- Float NOPE -number
- Number
- Undefines
- Object

4. Implicit coersion : regardless of the order of operands, if one is a string, they are concatenated as strings.

5. `console.log(5 + Number('10'));`
6. `console.log(`The value of 5 + 10 is ${Number('5') + 10}.`);`
7. Undefined
8. `let names = ['a', 'b', 'c', 'd', 'e'];`
9. 
```
let pets2 = {
  asta:	'dog',
  butterscotch:	'cat',
  pudding:	'cat',
  neptune:	'fish',
  darwin: 'lizard',
};
```
10. False
11. 3
12. true

## [Variables](https://launchschool.com/books/javascript/read/variables)

### [Variables and Variable Names](https://launchschool.com/books/javascript/read/variables#variablesandvariablenames)

```javascript
let answer = 41;
answer = 42
console.log(answer)
```

#### Variable naming

- "identifiers" can refer to:
  - variable names declared by `let` and `var`
  - Consant names declared by `const`
  - Property names of objects (?)
  - Function names
  - Function params 
  - Class names     
- Variable name can refer to all of the above, except 'Property names of objects'.
- THIS IS FINICKY BULLSHIT AND I WANT TO PUNCH THE SCREEN.

#### What else is a variable?

- Variables declared with `let` and `var`
- Constants declared with `const` (They are constant, even though they're under the umbrella of variables)
- Properties of the global object
- Function names
- Function Params (weird that these are vars, but that's how JS stores them)
- Class names     (weird that these are vars, but that's how JS stores them)

### [Declaring and Assigning Variables](https://launchschool.com/books/javascript/read/variables#declaringandassigningvariables)

- You can create a variable without a value. It's usually done with `let`. That would be declaring the variable: `let firstName` => undefined
- To assign a more useful value we use an **initializer** AKA `=` : `let firstName = 'John'` => undefined.
- Assignments and reassignments return values, but declarations don't. So the example above isn't returning `undefined`, the NODE repl is supplying that automatically.
- UUUUURRRRGGHHHHHH `=` is a "syntactic token" when used in a declaration. But it is a "assignment operator" in assignemnt. FUCKING FUCK BALLS KILL ME NOW.
- In the following example, b still equals 4 because reassignment does not also reassign all previous assignments that used that variable (OBVIOUSLY)

```javascript
let a = 4 // = undefined
let b = a // = undefined
let a = 7 // = 7
b         // = 4
```

### [Declaring Constants](https://launchschool.com/books/javascript/read/variables#declaringconstants)

- `const` is `let` for constants.

```javascript
const firstName = 'Mitchell' // = undefined
firstName // = Mitchell
```

- They have an immutable binding.

```
const INTEREST_RATE = 0.0783;
INTEREST_RATE = 0.0788; // Uncaught Type Error
```

- this is better:

```
const INTEREST_RATE = 0.0783;
let interest = amount * INTEREST_RATE;
```

- Unlike vars, const declarations require a value.

```
const TEST_1; // Uncaught SyntaxError: Missing initializer in const declaration
let test_1; // undefined
```

### [Variable Scope](https://launchschool.com/books/javascript/read/variables#variablescope)

- Where you declare a variable defines its scope.
- `let` or `const` means a block scope.
- Not everything between curly braces is a block (BLUE BOX) = Finicky Bullshit

- The following example shows that assignment within a block cannot be accessed outside the block:

```
if (1 === 1) {
  let a = 'foo';
}

console.log(a); // ReferenceError: a is not defined
```

- But if you assign it outside the block first then it is (same as Ruby)

```javascript
let a = 'foo';
if (1 === 1) {
  a = 'bar';
}

console.log(a);    // => 'bar'
```

- Same for `const`s. `var` is different.

### [A Common Gotcha](https://launchschool.com/books/javascript/read/variables#acommongotcha)

- If you forgo `const` or `let`, JS will still assign the value, but it can have unintended consequenses. Notably: undeclared vars have global scope. So avoid that, because it fucks up the whole code-base.

### [Summary](https://launchschool.com/books/javascript/read/variables#summary)



### [Exercises](https://launchschool.com/books/javascript/read/variables#exercises)

1. 
```javascript
const NAME = 'Victor';
console.log(`Good Morning, ${NAME}.`);
console.log(`Good Afternoon, ${NAME}.`);
console.log(`Good Evening, ${NAME}.`);
```

2. 
```
let age = 34;
let years = 10;
console.log(`In ${years} years, you will be ${age + years} years old.`);
years += 10;
console.log(`In ${years} years, you will be ${age + years} years old.`);
years += 10;
console.log(`In ${years} years, you will be ${age + years} years old.`);
years += 10;
console.log(`In ${years} years, you will be ${age + years} years old.`);
```

3. Error because initializing a var within a scope makes it inaccessible outside the block

4. Prints first three then const reassignment error.

5. `Bar` because it can't see `qux`.

6. No because CONSTs are also bound by block scoping rules.

## [Input/Output](https://launchschool.com/books/javascript/read/input_output)

### [Command Line Output](https://launchschool.com/books/javascript/read/input_output#commandlineoutput)

```
let name = 'Jane';
console.log(`Good morning, ${name}!`);
```

### [Command Line Input](https://launchschool.com/books/javascript/read/input_output#commandlineinput)

- readline API
- readline-sync (simplified version)
- `package.json` in current directory.
  - no, then `npm init -y`
  - `npm install readline-sync --save`

#### Example: Greet the User By Name

```javascript
let rlSync = require('readline-sync');

let number1 = Number(rlSync.question('Enter the first number\n'));
let number2 = Number(rlSync.question('Enter the second number\n'));
let sum = number1 + number2;

console.log(`The numbers ${number1} and ${number2} add to ${sum}`);
```

### [Input in the Browser](https://launchschool.com/books/javascript/read/input_output#inputinthebrowser)

- Very different from Node.

```html
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

### [Summary](https://launchschool.com/books/javascript/read/input_output#summary)


### [Exercises](https://launchschool.com/books/javascript/read/input_output#exercises)

1. 
```javascript
let rlSync = require('readline-sync');

let name = rlSync.question('What is your name!?\n');

console.log(`Fuck you ${name}!`);
```

2.

```
let rlSync = require('readline-sync');

let name = rlSync.question('What is your name!?\n');
let secondName = rlSync.question('What is your last name!?\n');

console.log(`Fuck you ${name} ${secondName}!`);
```

3.
```javascript
let rlSync = require('readline-sync');

let age = rlSync.question('How old are you?\n');

let years = 10;
console.log(`In ${years} years, you will be ${Number(age) + years} years old.`);
years += 10;
console.log(`In ${years} years, you will be ${Number(age) + years} years old.`);
years += 10;
console.log(`In ${years} years, you will be ${Number(age) + years} years old.`);
years += 10;
console.log(`In ${years} years, you will be ${Number(age) + years} years old.`);
```

## [Functions](https://launchschool.com/books/javascript/read/functions)

- Ruby methods?

### [Using Functions](https://launchschool.com/books/javascript/read/functions#usingfunctions)

```javascript
function funcName() {
  func_body;
}
```

```javascript
function say() {
  console.log("Hi!");
}
```

```javascript
function say() {
  console.log("Output from say()");
}

console.log("First");
say(); // this is the function call (Like method call). It doesn't work without the parentheses
console.log("Last");
```

### [Arguments & Parameters](https://launchschool.com/books/javascript/read/functions#argumentsparameters)

```javascript
function say(text) {
  console.log(text);
}

say("hello");
say("hi");
say("how do you do");
say("Quite all right");
```

- function names are local variable when they are defined within another function. Otherwise global.
- THIS IS ALL FAMILIAR FROM RUBY.

### [Return Values](https://launchschool.com/books/javascript/read/functions#returnvalues)

- Implicit return v explicit return.

```javascript
function add(a, b) {
  return a + b;
}

add(2, 3); // returns 5
```

- Functions that always return a boolean are called predicates.

### [Default Parameters](https://launchschool.com/books/javascript/read/functions#defaultparameters)

```
function say(text = "hello") {
  console.log(text + "!");
}

say("Howdy"); // => Howdy!
say();        // => hello!
```

### [Nested Functions](https://launchschool.com/books/javascript/read/functions#nestedfunctions)

```
function foo() {
  function bar() {
    console.log("BAR");
  }

  bar(); // => BAR
  bar(); // => BAR
}

foo();
bar(); // ReferenceError: bar is not defined
```

- Such nested functions are created and destroyed every time the outer function runs.

### [Functions & Scope](https://launchschool.com/books/javascript/read/functions#functionsscope)

- Globs and locks baby.

#### Global variables

- Any var declared within a function or block is local. Everything else is global.
- Devs discourage global vars because in almost all cases they cause bugs.

#### Local Vars

- Short lived. When the function within which they were defined stops running, they stop being available. (Like the winter king in Game of Thrones)

### [Functions vs. Methods](https://launchschool.com/books/javascript/read/functions#functionsvsmethods)

- In JS Functions look like this: `aFunction()` and methods look like this `var.aMethod()`
- In Ruby this is Instance methods and Class methods ? 

### [Reassignment and Mutation](https://launchschool.com/books/javascript/read/functions#reassignmentandmutation)

- The only part of the following example I'm not sure on is the "object property" reassignemnt...

```javascript
let num = 3;              // A variable assigned to a primitive value
let arr = [1, 2, 3];      // A variable assigned to an array
let obj = { a: 1, b: 2 }; // A variable assigned to an object

num = 42;    // Reassignment
arr[1] = 42; // Reassignment of array element, but NOT the variable
             // The array referenced by arr is mutated!
obj.a = 42;  // Reassignment of object property, but NOT the variable
             // The object referenced by obj is mutated.

// You can still reassign the variables
arr = 42;                 // Reassignment; array is lost
obj = { b: 1, c: 2 }      // Reassignment: now refers to a different object
```

### [Mutating the Caller](https://launchschool.com/books/javascript/read/functions#mutatingthecaller)

```javascript
let oddNumbers = [1, 3, 5, 7, 9];
oddNumbers.pop();
console.log(oddNumbers); // => [1, 3, 5, 7]
```

- Strings are immutable. Actually. Operations on a String will return a brand new string.
- JS is pass-by-value when dealing with Primative values and pass-by-reference when dealing with objects and arrays.

### [Function Composition](https://launchschool.com/books/javascript/read/functions#functioncomposition)

#### Function composition

```javascript
console.log(add(20, 45)); // => 65
console.log(subtract(80, 10)); // => 70
```

```javascript
function times(num1, num2) {
  return num1 * num2;
}

console.log(times(add(20, 45), subtract(80, 10))); // => 4550
// 4550 == ((20 + 45) * (80 - 10))
```

```javascript
add(subtract(80, 10), times(subtract(20, 6), add(30, 5))); // => 560
```

### [Three Ways to Define a Function](https://launchschool.com/books/javascript/read/functions#threewaystodefineafunction)

#### Function declaration

```javascript
function functionName(zeroOrMoreArguments...) {
  // function body
}
```

- You can call functions before you declare them.

#### Function expression

```javascript
let greetPeople = function () {
  console.log("Good Morning!");
};

greetPeople();
```

- assigning it to a variable makes it an expression rather than a declaration.
- You cannot invoke a function expression before it appears in the program.

#### First class functions

- The example above declares a variable named `greetPeople` and assigns it to the function expression after the `=` sign. We can do that because JS functions are **first class functions** WHAR?!
- All JS functions are objects. So you can assign them to vars and pass them around. This is going to be a big deal going forward.
- Any function definition that doesn't have the word `function` right at the beginning is a function expression.

```javascript
(function greetPeople() { // This is a function expression, not a declaration
  console.log("Good Morning!");
});
```

and the following (not a function declaration, it's a function expression)

```
function makeGreeter(name) {
  return function greeter() {
    console.log(`Hello ${name}`);
  };
}
```

### Arrow functions

-Thirdly there's this bullshit:

```
let greetPeople = () => console.log("Good Morning!");
greetPeople();
```

- These are (similar to) function expressions with an alternate syntax. Not totally the same because:
  - implicit returns `let add = (a, b) => a + b;`
  - We can omit the `return` keyword when A) the function contains a single expression (It can have subexpressions, but must evaluate to a single value) B) it isn't surrounded by curly braces

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

### [The Call Stack](https://launchschool.com/books/javascript/read/functions#callstack)

- new frame is "pushed" to the stack.
- Frames are "popped" from the stack.
- If the stack runs out of room you will see a `RangeError`

### [Summary](https://launchschool.com/books/javascript/read/functions#summary)


### [Exercises](https://launchschool.com/books/javascript/read/functions#exercises)

1. 1, no, because the `bar` assigned in the function is local and therefore not visible to the console.log call on line 7.
2. 
```
function getName(prompt) {
  let readlineSync = require('readline-sync');
  let name = readlineSync.question(prompt);
  return name;
}

let firstName = getName('What is your first name? ');
let lastName = getName('What is your last name? ');
console.log(`Hello, ${firstName} ${lastName}!`);
```

3. 
```
let rlSync = require('readline-sync');

function multiply() {
  let first = rlSync.question('Enter the first operand:\n');
  let second = rlSync.question('Enter the second operand:\n');
  console.log(`${first} * ${second} = ${first * second}`)
};

multiply();
```

4. Nothing, the `return` escapes the method before it can print anything.
5. Nothing, it returns a value, but prints nothing.
6
```
function multiplyNumbers(num1, num2, num3) { 
  let result = num1 * num2 * num3; 
  return result;
}

let product = multiplyNumbers(2, 3, 4); 

// function arguments are 2, 3, 4
// function body is lines 2 and 3 (between the curly braces)
// function declaration is everything on lines 1 to 4
// function invocation is line 6: multiplyNumbers(2, 3, 4);
// function name is multiplyNumbers on lines 1 and 6
// function parameters is (num1, num2, num3) on line 1
// function return value will be 24
// the names of all the vars are num1, num2, num3, result, product also multiplyNumbers
```

7. `'Hello'` and `undefined`
8. `42` and `3.1415`
9. 
```
function multiply(left, right) { // multiply, left, right
  let product = left * right; // product, left, right
  return product; // product
}

function getNumber(prompt) { //getNumber, prompt
  return parseFloat(question(prompt)); // parseFloat, question, prompt
}

let left = getNumber('Enter the first number: '); // left, getNumber
let right = getNumber('Enter the second number: '); // right, getNumber
console.log(`${left} * ${right} = ${multiply(left, right)}`); // console, left, right, multiply
```
10.
```
function multiply(left, right) { // multiply, left, right
  let product = left * right; // product, left, right
  return product; // product
}

function getNumber(prompt) { //getNumber, prompt
  return parseFloat(question(prompt)); // parseFloat, question, prompt
}

let left = getNumber('Enter the first number: '); // left, getNumber
let right = getNumber('Enter the second number: '); // right, getNumber
console.log(`${left} * ${right} = ${multiply(left, right)}`); // console, left, right, multiply

// Global vars: multiply, getNumber, parseFloat, question, left(line 10), right(line 11), getNumber, console
// Local vars: left, right, product, prompt
```

11. Nope, the left and right definied within a function are local variables completely seperate to the global variables left and right defined outside the function. Variable shadowing.

## [Flow Control](https://launchschool.com/books/javascript/read/flow_control)

### [Conditionals](https://launchschool.com/books/javascript/read/flow_control#conditionals)

- `if` + logical operators:
  - `>=`
  - `==`
  - `===`
  - `!=`
  - `!==`
  - `&&`
  - `||`
- also `else`.

```
// Run this code in your browser with an HTML file

let a = prompt('Enter a number');

if (a === '3') {
  console.log("a is 3");
} else if (a === '4') {
  console.log("a is 4");
} else {
  console.log("a is neither 3, nor 4");
}
```

### [Comparisons](https://launchschool.com/books/javascript/read/flow_control#comparisons)

- `===` is the strict equality operator and compares type and value
- `!==` is the strict inequality operator.
- `==` the non-strict equality operator (AKA 'loose equality oeprator'). Attempts to coerce one oeprand to the other's type. Or sometimes both! (can you imagine).
  - `5 == '5'` => true
  - `'' == 0` => true
- `==` is governed by complex and difficult rules, so stick to `===` when you can.
- `"42" < 420` => true because the first operand is coerced into a number. 

### [Logical Operators](https://launchschool.com/books/javascript/read/flow_control#logicaloperators)

- `!`
  - `!true` => false
  - `!(4 === 4)` => false
  - `!(4!==4)` => true

### [Short Circuits](https://launchschool.com/books/javascript/read/flow_control#shortcircuits)

```
> isRed(item) && isPortable(item)
> isGreen(item) || hasWheels(item)
```

- In the 2nd example JavaScript doesn't check the seond condition if the first condition is true.

### [Truthiness](https://launchschool.com/books/javascript/read/flow_control#truthiness)

- Same as Ruby... EXCEPT JS doesn't evaluate the same things as truthy and falsy. For example: in Ruby 0 is truthy.
- The return value in `&&` and `||` is always the operand evaluated last.
- Using a string as if it is a Boolean:

```
let foo = null;
let bar = 'qux';
let isOk = foo || bar;
```

- but more clearly:

```
// if statement
let isOk;
if (foo || bar) {
  isOk = true;
} else {
  isOk = false;
}
```

```
// ternary expression
let isOk = (foo || bar) ? true : false;
```

- And finally the most common way to assign a non-boolean value evaluated by truthiness is with `!!`:

```
let isOk = !!(foo || bar);
```

- `!!` is just two consecutive `!`s. So `!!a` is the same as `!(1a)`

### [Nullish Coalescing Operator](https://launchschool.com/books/javascript/read/flow_control#nullishcoalescing)

- `??` evaluates the right-hand operand if the left-hand operand is nullish.
- 'nullish' is `null` or `undefined`
- So it's simillar to `||`, but  with nullish instead of falsy, as seen below:

```
> null ?? "over here!"    // does not short-circuit
= 'over here!

> undefined ?? "pick me!" // does not short-circuit
= 'pick me!'

> false ?? "not me"       // short-circuits
= false

> 0 ?? "not me either"    // short-circuits
= 0
```

- So it's most appropriate when you're likely to run up against `null` or `undefined`. As below:

```
function foo(str) {
  let found = ["Pete", "Alli", "Chris"].find(name => name === str);
  return found ?? "Not found";
}

console.log(foo("Alli"));     // => Alli
console.log(foo("Allison"));  // => Not found
```

- `??` isn't used a lot in Core, more in Capstone.

### [Operator Precedence](https://launchschool.com/books/javascript/read/flow_control#operatorprecedence)

- highest to lowest:
  - Comparison: `<=`, `<`, `>`, `>=`
  - Equality: `===`, `!==`, `==`, `!=`
  - Logical AND: `&&`
  - Logical OR: `||`

```
if (x || y && z) {
  // do something
}
```

- "evaluated [...] at the same depth" ?

```
if ((x || y) && z) {
  // do something
}
```

- Parentheses help programmers understand your intentions.
- JS evaluates JS in usual algebraic order. THat means innermost bracketed items first and working outwards.
- SHort circuit evaluation does not change presedence rules.

### [The Ternary Operator](https://launchschool.com/books/javascript/read/flow_control#theternaryoperator)

```
> 1 == 1 ? 'this is true' : 'this is not true'
= 'this is true'

> 1 == 0 ? "this is true" : "this is not true"
= 'this is not true'

```

- It does the same thing as an `if/else` statement, but one cannot capture the result of a statement in a variable or argument. With a ternary operator we can:

```
> let message = true ? 'this is true' : 'this is not true'
= undefined

> message
= 'this is true'

> console.log(false ? 'this is true' : 'this is not true')
this is not true
= undefined
```

#### When should I use a Ternary expression?

- CHoosing between two values, rather than between two actions.
- Yes:

```
let foo = hitchhiker ? 42 : 3.1415;    // Assign result of ?: to a variable
console.log(hitchhiker ? 42 : 3.1415); // Pass result as argument
return hitchhiker ? 42: 3.1415;        // Return result
```

- No:

```
hitchhiker ? foo = 42 : bar = 3.1415;               // Setting variables
hitchhiker ? console.log(42) : console.log(3.1415); // Printing
```

### [Switch Statement](https://launchschool.com/books/javascript/read/flow_control#switchstatement)

- Like a `case` statement in Ruby?
- The key difference with `if` statements is that it can compare a single value with multiple values, rather than a one to one comparison.
- They use the key words `switch`, `case`, `default` and `break`.

```
let a = 5;

switch (a) {
  case 5:
    console.log('a is 5');
    break;
  case 6:
    console.log('a is 6');
    break;
  default:
    console.log('a is neither 5, nor 6');
    break;
} // => a is 5
```

- Which does the same thing as this:

```
let a = 5;

if (a === 5) {
  console.log('a is 5');
} else if (a === 6) {
  console.log('a is 6');
} else {
  console.log('a is neither 5, nor 6');
} // => a is 5
```

- Without `break` it does each option (Why that would ever be helpful is beyond me). It's called 'fall-throughs' apparently. Even when it's correct it looks wrong.

```
let a = 5;

switch (a) {
  case 5:
    console.log('a is 5');
  case 6:
    console.log('a is 6');
  default:
    console.log('a is neither 5, nor 6');
} // => a is 5
  //    a is 6
  //    a is neither 5, nor 6
```

- Here's a situation where it is correct:

```
let a = 5;

switch (a) {
  case 5:
  case 6:
  case 7:
    // executed if a is 5, 6, or 7
    console.log("a is either 5, 6, or 7");
    break;
  case 8:
  case 9:
    // executed if a is 8 or 9
    console.log('a is 8 or 9');
    break;
  default:
    // executed if a is anything else
    console.log('a is not 5, 6, 7, 8, or 9');
    break;
}
```

### [Summary](https://launchschool.com/books/javascript/read/flow_control#summary)


### [Exercises](https://launchschool.com/books/javascript/read/flow_control#exercises)

1.
```
false || (true && false); // => false TICK
true || (1 + 2); // => true TICK
(1 + 2) || true; // => 3 TICK
true && (1 + 2); // => true CROSS 3
false && (1 + 2); // => false TICK
(1 + 2) && true; // => true TICK
(32 * 4) >= 129; // => false TICK
false !== !true; // => false TICK
true === 4; // => false TICK
false === (847 === '847'); // => true TICK
false === (847 == '847'); // => false TICK
(!true || (!(100 / 5) === 20) || ((328 / 4) === 82)) || false; // => true TICK
```

2. 
```
function evenOrOdd(num) {
  if (num % 2 === 0) {
    console.log("even");
  } else {
    console.log("odd");
  }
}

evenOrOdd(4)
evenOrOdd(5)
```

3.
```
function evenOrOdd(num) {
  if (typeof num !== 'number') {
    console.log(`${num} is not num`);
  } else if (num % 2 === 0) {
    console.log(`${num} is even`);
  } else {
    console.log(`${num} is odd`);
  }
}

evenOrOdd('bacon')
evenOrOdd(4)
evenOrOdd(5)
```

4. The lack of `break`s will make this following code print all the outputs. NO : it won't print the first one, because the inpout doesn't match, but once it matches it prints all the remaining options in a 'fall-through'.

```
function barCodeScanner(serial) {
  switch (serial) {
    case '123':
      console.log('Product1');
    case '113':
      console.log('Product2');
    case '142':
      console.log('Product3');
    default:
      console.log('Product not found!');
  }
}

barCodeScanner('113');
```

5. 

```
if (foo()) {
  return 'bar';
} else {
  return qux();
}
```

6. 'Not Empty', because `[]` is a truthy value.

```
function isArrayEmpty(arr) {
  if (arr) {
    console.log('Not Empty');
  } else {
    console.log('Empty');
  }
}

isArrayEmpty([]);
```

7. 

```
function capitalize_(str) {
  if (str.length > 10) {
    return str.toUpperCase();
  } else {
    return str;
  }
}

capitalize_('hello world')
capitalize_('goodbye')
```

8.

```
function numberRange(num) {
  if (num >= 0 && num <= 50) {
    console.log(`${num} is between 0 and 50`);
  } else if (num >= 51 && num <= 100) {
    console.log(`${num} is between 51 and 100`);
  } else if (num >= 100) {
    console.log(`${num} is greater than 100`);
  } else if (num < 0) {
    console.log(`${num} is less than 0`);
  }
}

numberRange(25);
numberRange(75);
numberRange(125);
numberRange(-25);
```

9.

```
console.log(false ?? null); // false
console.log(true ?? (1 + 2)); // true
console.log((1 + 2) ?? true); // 3
console.log(null ?? false); // false
console.log(undefined ?? (1 + 2)); // 3
console.log((1 + 2) ?? null); // 3
console.log(null ?? undefined); // undefined
console.log(undefined ?? null); // null
```

10.

```
function show(foo = undefined, bar = null) {
  console.log(`foo is ${foo ?? 3}, bar is ${bar ?? 42}`);
}

show(5, 7); // foo is 5, bar is 7
show(0, 0); // foo is 0, bar is 0
show(4); // foo is 4, bar is 42
show(); // foo is 3, bar is 42
```

## [Loops & Iterating](https://launchschool.com/books/javascript/read/loops_iterating)

### [while Loops](https://launchschool.com/books/javascript/read/loops_iterating#whileloops)

- post-incremenet operator, v pre-increment operator.
- Some devs think they're to be avoided.

```
let a = 1;

console.log(a); // 1  (Difference is not apparent when printing)

++a; // pre-increment operator: returns the new value

console.log(a); // 2 (Here is the result of the addition)

a++ // post-increment operator: returns the old value

console.log(a); // 3 (Difference is not apparent when printing)
```

#### Looping over Arrays with While

```
let names = ['Chris', 'Kevin', 'Naveed', 'Pete', 'Victor'];
let upperNames = [];
let index = 0;

while (index < names.length) {
  let upperCaseName = names[index].toUpperCase();
  upperNames.push(upperCaseName);
  index += 1;
}

console.log(upperNames); // => ['CHRIS', 'KEVIN', 'NAVEED', 'PETE', 'VICTOR']
console.log(names); // [ 'Chris', 'Kevin', 'Naveed', 'Pete', 'Victor' ] because #toUpperCase doesn't mutate the original value.
```

#### Do/While loop

```
let answer;
do {
  answer = prompt("Do you want to do that again?");
} while (answer === 'y');
```

### [for Loops](https://launchschool.com/books/javascript/read/loops_iterating#forloops)

```
for (initialization; condition; increment) {
  // loop body
}
```

```
let names = ['Chris', 'Kevin', 'Naveed', 'Pete', 'Victor'];
let upperNames = [];

for (let index = 0; index < names.length; index += 1) {
  let upperCaseName = names[index].toUpperCase();
  upperNames.push(upperCaseName);
}

console.log(upperNames); // => ['CHRIS', 'KEVIN', 'NAVEED', 'PETE', 'VICTOR']
```

### [Controlling Loops](https://launchschool.com/books/javascript/read/loops_iterating#controllingloops)

#### `continue`

- means skip ?

```
let names = ['Chris', 'Kevin', 'Naveed', 'Pete', 'Victor'];
let upperNames = [];

for (let index = 0; index < names.length; index += 1) {
  if (names[index] === 'Naveed') {
    continue;
  }

  let upperCaseName = names[index].toUpperCase();
  upperNames.push(upperCaseName);
}

console.log(upperNames); // => ['CHRIS', 'KEVIN', 'PETE', 'VICTOR']
```

- which has the same effect as a negated `if` in the following code:

```
let names = ['Chris', 'Kevin', 'Naveed', 'Pete', 'Victor'];
let upperNames = [];

for (let index = 0; index < names.length; index += 1) {
  if (names[index] !== 'Naveed') {
    let upperCaseName = names[index].toUpperCase();
    upperNames.push(upperCaseName);
  }
}

console.log(upperNames); // ['CHRIS', 'KEVIN', 'PETE', 'VICTOR']
```

- `continue` can be avoided, but it tends to make code more concise and explicit:

- This:

```
for (let i = 0; i < someNumber; i += 1) {
  if (someCondition) {
    // execute 10 lines
  }
}
```

- can become this:

```
for (let i = 0; i < someNumber; i += 1) {
  if (!someCondition) continue;
  // execute 10 lines
}
```

- And this:

```
for (let i = 0; i < someNumber; i += 1) {
  if (someCondition) {
    // some code here
    if (anotherCondition) {
      // some more code here
    }
  }
}
```

- Can become this:

```
for (let i = 0; i < someNumber; i += 1) {
  if (!someCondition) continue;
  // some code here

  if (!anotherCondition) continue;
  // some more code here
}
```

- At an earlier point this this book it was recommended to ALWAYS use a block with an `if` statement. One common exception is with `continue`, `break` and `return`. In that case the keyword is acting as a block.

#### `break`

- I know this from Ruby.

### [Array Iteration](https://launchschool.com/books/javascript/read/loops_iterating#arrayiteration)

```
let names = ['Chris', 'Kevin', 'Naveed', 'Pete', 'Victor'];

names.forEach(function(name) {
  console.log(name);
});
```

- This is not a function definition which we pass to `forEach`, it is in fact a function expression.
- The function has no name. It is an "anonymous function".
- JS has "first-class functions", which means functions are values and so you can assign them to variables and pass them around etc.
- We can make it more concise by using arrow functions:

```
let names = ['Chris', 'Kevin', 'Naveed', 'Pete', 'Victor'];

names.forEach(name => console.log(name));
```

- Most devs prefer **array looping abstractions** like `forEach` rather than loops.

### [Recursion](https://launchschool.com/books/javascript/read/loops_iterating#recursion)

- 'functions that call themselves'. They are close cousins to loops. You could say (and "we do") that recursion is another way to create loops in JS.

```
function doubler(number) {
  console.log(number);

  if (number <= 50) {
    doubler(number * 2);
  }
}

doubler(5); // => 5
            // => 10
            // => 20
            // => 40
            // => 80
```

- Fibonacci:

```
function fibonacci(number) {
  if (number < 2) return number; // 0 if number is 0, 1 if number is 1
  return fibonacci(number - 1) + fibonacci(number - 2);
}

console.log(fibonacci(6));  // => 8
console.log(fibonacci(20)); // => 6765
```

- Every recursive function has a baseline condition. (`number < 2` above).

### [Summary](https://launchschool.com/books/javascript/read/loops_iterating#summary)


### [Exercises](https://launchschool.com/books/javascript/read/loops_iterating#exercises)

1. 

```
let age = 34

ages = [10, 20, 30, 40];
for (let index = 0; index < ages.length; index += 1) {
  console.log(`In ${ages[index]} years, you will be ${Number(age) + ages[index]} years old.`);
}
```

2. 

```
function factorial(num) {
  let output = 1;
  for (let counter = 1; counter <= num; counter ++) {
    output *= counter;
  }
  return output; // without the 'return' the function returns 'undefined'
}
console.log(factorial(1));     // => 1
console.log(factorial(2));     // => 2
console.log(factorial(3));     // => 6
console.log(factorial(4));     // => 24
console.log(factorial(5));     // => 120
console.log(factorial(6));     // => 720
console.log(factorial(7));     // => 5040
console.log(factorial(8));     // => 40320
```

3. Because in line 3 `counter` is reassigned to 1 every iteration. (it's assignment, but should be comparison with `===`)

4. No, the block provides an increment and JS seems ok with it. ALL 3 COMPONENTS IN A `for` LOOP ARE OPTIONAL. The guiding wisdom is to limit the scope of your variables to the smallest possible.

```
for (let i = 0; i < 5;) {
  console.log(i += 1);
}

let i;
for (i = 0; i < 5;) {
  console.log(i += 1);
}
```

5.

```
  function randomNumberBetween(min, max) {
    return Math.floor(Math.random() * (max - min + 1) + min);
  }

  let tries = 1;

  while (randomNumberBetween(1, 6) <= 2) { tries += 1; }

  console.log('It took ' + String(tries) + ' tries to get a number greater than 2');
```

6. 

```
function factorial(number) {
  while (number > 1) {
    return number *= (factorial(number - 1));
  };
  return number;
}
```

## [Arrays](https://launchschool.com/books/javascript/read/arrays)

### [What is an Array?](https://launchschool.com/books/javascript/read/arrays#whatisanarray)
### [Modifying Arrays](https://launchschool.com/books/javascript/read/arrays#modifyingarrays)
### [Iteration Methods](https://launchschool.com/books/javascript/read/arrays#iterationmethods)
### [Arrays Can Be Odd](https://launchschool.com/books/javascript/read/arrays#arrayscanbeodd)
### [Nested Arrays](https://launchschool.com/books/javascript/read/arrays#nestedarrays)
### [Array Equality](https://launchschool.com/books/javascript/read/arrays#arrayequality)
### [Other Array Methods](https://launchschool.com/books/javascript/read/arrays#otherarraymethods)
### [Summary](https://launchschool.com/books/javascript/read/arrays#summary)
### [Exercises](https://launchschool.com/books/javascript/read/arrays#exercises)

## [Objects](https://launchschool.com/books/javascript/read/objects)

### [What are Objects?](https://launchschool.com/books/javascript/read/objects#whatareobjects)
### [Objects vs. Primitives](https://launchschool.com/books/javascript/read/objects#objectsvsprimitives)
### [Prototypes](https://launchschool.com/books/javascript/read/objects#prototypes)
### [Iteration](https://launchschool.com/books/javascript/read/objects#iteration)
### [Common Operations](https://launchschool.com/books/javascript/read/objects#commonoperations)
### [Objects vs. Arrays](https://launchschool.com/books/javascript/read/objects#objectvsarrays)
### [Summary](https://launchschool.com/books/javascript/read/objects#summary)
### [Exercises](https://launchschool.com/books/javascript/read/objects#exercises)

## [More Stuff](https://launchschool.com/books/javascript/read/more_stuff)

### [Variables as Pointers](https://launchschool.com/books/javascript/read/more_stuff#variablesaspointers)
### [for/in and for/of](https://launchschool.com/books/javascript/read/more_stuff#forinforof)
### [Method Chaining](https://launchschool.com/books/javascript/read/more_stuff#methodchaining)
### [Regex](https://launchschool.com/books/javascript/read/more_stuff#regex)
### [The Math Object](https://launchschool.com/books/javascript/read/more_stuff#themathobject)
### [Dates](https://launchschool.com/books/javascript/read/more_stuff#dates)
### [Exceptions](https://launchschool.com/books/javascript/read/more_stuff#exceptions)
### [Stack Traces](https://launchschool.com/books/javascript/read/more_stuff#readingstacktraces)
### [ES6 and Beyond](https://launchschool.com/books/javascript/read/more_stuff#essixandbeyond)
### [Exercises](https://launchschool.com/books/javascript/read/more_stuff#exercises)

## [Conclusions](https://launchschool.com/books/javascript/read/next_steps)

### [Conclusion & Next Steps](https://launchschool.com/books/javascript/read/next_steps)
