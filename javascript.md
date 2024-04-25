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


- same as Ruby (heterogenous - can include different types of thing)
- "An **ordered** list of items.
- An **indexed** list of items.

```
myArray[myArray.length - 1]
```

### [Modifying Arrays](https://launchschool.com/books/javascript/read/arrays#modifyingarrays)

#### Replacing and Adding Elements with `[]`

`array[1] = 4`

`array[array.length] = 10` => to add new elems to the end.

- With a `const` array you can reassign elements, but not the array itself.
  - If you want the content to be constant, you have to use `Object.freeze`.

```
const MyArr = Object.freeze([1, 2, 3]);
console.log(MyArr[1] = 5); // => 5
console.log(MyArr); // => [1, 2, 3]
```

- A detail of `Object.freeze` is that it only goes one level deep. So the contents of nested Arrays can be modified (unless they themselves are frozen).

#### Adding elements with `push`

```
let array = [1, 2, 3];
console.log(array.push(true)); // => 4, because push returns the new length of the array.
console.log(array) 
console.log(array.push('eat', 'my', 'sparenky')); // => 7
console.log(array)
```

- `push` mutates the array, but returns the updated length.

#### Adding elements with concat

- like `push` without mutating the caller.

```
let array = [1, 2, 3];
console.log(array.concat('another thing', 'and another thing')); // => [ 1, 2, 3, 'another thing', 'and another thing' ]
console.log(array); // => [1, 2, 3]
```

#### Removing elements with `pop`

- What you think of as taking the top of the call-stack off. Mutating.

```
let arr = [1, 2, 3];
console.log(arr.pop); // => [Function: pop]        ...WHAT?
console.log(arr.pop()); // => 3
console.log(arr); // => [1, 2]
```

#### Removing elements with `splice`

- Remove one or more elements from an Array, even if they aren't at the end.

```
let arr = [1, 2, 3, '4', 'Elk', true, [1, 2, 3]];
console.log(arr); // => [ 1, 2, 3, '4', 'Elk', true, [ 1, 2, 3 ] ]
console.log(arr.splice(4, 2)); [ 'Elk', true ]
console.log(arr); // => [ 1, 2, 3, '4', [ 1, 2, 3 ] ]
```

- (`splice` can also insert elements, more on that later)

### [Iteration Methods](https://launchschool.com/books/javascript/read/arrays#iterationmethods)

#### `forEach`

- a **callback** function is required. That means a function that is passed into another function:

```
let array = [1, 2, 3];
array.forEach(function(num) {
  console.log(num); // on first iteration  => 1
                    // on second iteration => 2
                    // on third iteration  => 3
}); // returns `undefined`

/// OR 

[1, 2, 3].forEach(function(num) { console.log(num); });

/// OR 

[1, 2, 3].forEach(num => console.log(num));

/// OR 

let array2 = [1, 2, 3]
array2.forEach(num => console.log(num + 2)); // => 3, 4, 5
```

- `forEach` always returns undefined


#### `map`

- like `forEach` when you need to return a new array. (like Ruby!)
-   `forEach` performs simple iteration and teurns `undefined`, while `map` transforms an array's elements and returns a new array with transformed values.

#### `filter`

- returns a new array populated by values that returned truthy from the block.

```
let numbers = [1, 2, 3, 4, 5, 6, 7 ,8, 9, 10, 1, 2];
numbers.filter(num => num > 4)
console.log(numbers) // => [1, 2, 3, 4, 5, 6, 7 ,8, 9, 10, 1, 2] so, doesn't mutate the caller
console.log(numbers.filter(num => num > 4)); // => [ 5, 6, 7, 8, 9, 10 ]
```

#### `reduce`

- squeezes the array down to one value.
- Same as Ruby

### [Arrays Can Be Odd](https://launchschool.com/books/javascript/read/arrays#arrayscanbeodd)

- 0 based index (easy) So length will always be 1 greater than the index of the final element (easy)
- Arrays are objects, so `console.log(typeof [1, 2, 3]); // => object`
  - If you need to see if an object is an Array, do it like this: `console.log(Array.isArray([1, 2, 3])); // => true`
- If you reassign `arr.length` to a new number, JS will chop down the arr:

```
let a = [1, 2, 3]
console.log(a); // => [1, 2, 3]
a.length = 1;
console.log(a); // => [1]
```

- And if you lengthen the arr, it fills it with empty spaces!

```
a.length = 7;
console.log(a); // => [ 1, <6 empty items> ]
```

- what's more, all of this:

```
console.log(a[2]); // => undefined                                             The empty spaces evaluate as undefineds
console.log(a.filter(element => element === undefined)); // => []              But if you look for undefineds, they won't be found
a.forEach(element => console.log(element)); // => 1                            and if you look for elements you can't see these empty spaces
a[5] = 'bugger me sideways';                                                   and you can put a real item in the middle of the empty spaces
console.log(a); // => [ 1, <4 empty items>, 'bugger me sideways', <1 empty item> ] 
console.log(a.length); // => 7                                                 and the length will count the empty spaces
a.forEach(element => console.log(element)); // => 1, bugger me sideways        but a block won't treat them as elements
console.log(Object.keys(a)); // => [ '0', '5' ]                                and this method also ignores them.
```

- If you assign elements to indexes that aren't positive numbers, JS will enter them as what look like kv pairs. They look like elements, but are actually "properties" and are not counted in `length`:

```
> arr = [1, 2, 3]
= [ 1, 2, 3 ]

> arr[-3] = 4
= 4

> arr
= [ 1, 2, 3, '-3': 4 ]

> arr[3.1415] = 'pi'
= 'pi'

> arr["cat"] = 'Fluffy'
= 'Fluffy'

> arr
= [ 1, 2, 3, '-3': 4, '3.1415': 'pi', cat: 'Fluffy' ]
```

- `Object.keys(arr)` returns all the properties, which means the indexes and (what look to me like) values.

- I need to look at this when I have more brain-power:

```
let a = new Array(3);
console.log(a); // => [ <3 empty items> ]
console.log(a[0] === undefined); // =>true

let b = [];
b.length = 3
console.log(b) // => [ <3 empty items> ]
console.log(b[0] === undefined); // => true


let c = [undefined, undefined, undefined];
console.log(c); //=> [ undefined, undefined, undefined ]
console.log(c[0] === undefined); // => true

let aKeys = Object.keys(a)
console.log(aKeys); // => []
console.log(a.length); // => 3
console.log(aKeys.length); // => 0

let bKeys = Object.keys(b)
console.log(bKeys); // => []
console.log(b.length); // => 3
console.log(bKeys.length); // => 0

let cKeys = Object.keys(c);
console.log(cKeys); // => [ '0', '1', '2' ]
console.log(c.length); // => 3
console.log(cKeys.length); // => 3
```

### [Nested Arrays](https://launchschool.com/books/javascript/read/arrays#nestedarrays)

```
let hornburg = ['seventh', ['sixth', ['fifth', ['fourth', ['third', ['second', ['first']]]]]]]

console.log(hornburg[0]); // => seventh
console.log(hornburg[1][0]); // => sixth
console.log(hornburg[1][1][0]); // => fifth
console.log(hornburg[1][1][1][0]); // => fourth
console.log(hornburg[1][1][1][1][0]); // => third
console.log(hornburg[1][1][1][1][1][0]); // => second
console.log(hornburg[1][1][1][1][1][1][0]); // => first
```

### [Array Equality](https://launchschool.com/books/javascript/read/arrays#arrayequality)


- `[1, 2, 3] === [1, 2, 3]` => false. Because it compares their memory address (object id)

```
// One way to compare arrays is by writing the following function:

function arraysEqual(arr1, arr2) {
  if (arr1.length !== arr2.length) return false;

  for (let i = 0; i < arr1.length; i += 1) {
    if (arr1[i] !== arr2[i]) {
      return false;
    }
  }

  return true;
}

console.log(arraysEqual([1, 2, 3], [1, 2, 3])); // => true
console.log(arraysEqual([1, 2, 3], [4, 5, 6])); // => false
console.log(arraysEqual([1, 2, 3], [1, 2, 3, 4])); // => false
```

### [Other Array Methods](https://launchschool.com/books/javascript/read/arrays#otherarraymethods)

#### `includes`

- `[1, 2, 3, 4, 5].includes(2) // => true`

#### indexOf

- `[1, 2, 3].indexOf(2) // => 1`  
- Returns the first match it finds, but you can give it a staring index: `[1, 2, 3, 4, 5, 1, 2, 3, 4, 5].indexOf(2, 4) // => 6`

#### `sort`

- `['a', 'z', 'f', 'b', 'c'].sort() // =>[ 'a', 'b', 'c', 'f', 'z' ]`
- Mutates the caller

#### `slice`

- Extracts and returns a copied portion of the array.
- `['a', 'z', 'f', 'b', 'c'].slice(1, 3) // => [ 'z', 'f' ]`
- If you omit the second argument it takes the rest of the array (just like `splice`).
- Without argument it retruns a copy.

#### `reverse`

- is destructive. Avoid destruction with `slice`: `[1, 2, 3, 4].slice().reverse()`

### [Summary](https://launchschool.com/books/javascript/read/arrays#summary)

### [Exercises](https://launchschool.com/books/javascript/read/arrays#exercises)

1. 

```
let array1 = [1, 2, undefined, 4]; // => 4

let array2 = [1]; 
array2.length = 5; // => 5

let array3 = [];
array3[-1] = [1]; // => 1 NO - 0, because negative numbers are not taken into account when determining an Array's length.

let array4 = [1, 2, 3, 4, 5];
array4.length = 3; // => 3

let array5 = [];
array5[100] = 3; // => 100 NO - it's 101, obvs.
```

2. 

```
let myArray = [1, 3, 6, 11, 4, 2,
  4, 9, 17, 16, 0];

output = myArray.filter(num => num % 2 == 0)
console.log(output);

// LS solution:

for (let i = 0; i < myArray.length; i += 1) {
  let value = myArray[i];
  if (value % 2 === 0) {
    console.log(value);
  }
};
```

3.

```
let myArray = [
  [1, 3, 6, 11],
  [4, 2, 4],
  [9, 17, 16, 0],
];

let result = myArray.map(arr => arr.filter(num => num % 2 == 0));

console.log(result);

// LS solution:

for (let outer_i = 0; outer_i < myArray.length; outer_i += 1) {
  for (let inner_i = 0; inner_i < myArray[outer_i].length; inner_i += 1) {
    let value = myArray[outer_i][inner_i];
    if (value % 2 === 0) {
      console.log(value);
    }
  }
}

// OR

myArray.forEach(function(nestedArray) {
  nestedArray.forEach(function(value) {
    if (value % 2 == 0) {
      console.log(value);
    }
  });
});
```

4.

```
let myArray = [1, 3, 6, 11, 4, 2,
  4, 9, 17, 16, 0];

let output = myArray.map(num => num % 2 == 0 ? 'even' : 'odd');

console.log(output);

// LS solution:

let newArray = myArray.map(function(value) {
  if (value % 2 == 0) {
    return 'even';
  } else {
    return 'odd';
  }
});

console.log(newArray);

// LS solution 2:

let newArray2 = [];

for (let i = 0; i < myArray.length; i += 1) {
  let value = myArray[i];
  if (value % 2 === 0) {
    newArray2.push('even');
  } else {
    newArray2.push('odd');
  }
}

console.log(newArray2);
```

5.

```
function findIntegers(array) {
  return array.filter(elem => Number.isInteger(elem));
};

let things = [1, 'a', '1', 3, NaN, 3.1415, -4, null, false];
let integers = findIntegers(things);
console.log(integers); // => [1, 3, -4]
 
```

6.

```
function oddLengths(arr) {
  return arr.map(str => str.length).filter(n => n % 2 == 1);
};


let arr = ['a', 'abcd', 'abcde', 'abc', 'ab'];
console.log(oddLengths(arr)); // => [1, 5, 3]

```

7. 
```
let array = [3, 5, 7];

function sumOfSquares(arr) {
  return arr.reduce((accumulator, element) => accumulator + (element * element));
};

console.log(sumOfSquares(array)); // => 83

// if no accumulator is provided, reduce takes the first element as an accumulator and begins with the second element. Therefore the calculation would be 3 + ((5*5)+(7*7)) =77
```

8. 

- This represents an unsuccessful attempt. I can't explain the output.

```
// function oddLengths(arr) {
//   return arr.reduce((accumulator, element) => accumulator.concat(element.length), [])
// };

function oddLengths(arr) {
  return arr.reduce((accumulator, element) => (element.length % 2 != 1) ? accumulator.concat(element.length) : ('whatever'), [])
};

let arr = ['a', 'abcd', 'abcde', 'abc', 'ab'];
console.log(oddLengths(arr)); // => [1, 5, 3]

```

- I didn't find a solution. 

LS solution:

```
function oddLengths(strings) {
  return strings.reduce((filteredNumbersArray, letters) => {
    let length = letters.length;
    if (length % 2 === 1) {
      filteredNumbersArray.push(length);
    }

    return filteredNumbersArray;
  }, []);
}

let arr = ['a', 'abcd', 'abcde', 'abc', 'ab'];
console.log(oddLengths(arr));
```

9.

```
let numbers1 = [1, 3, 5, 7, 9, 11];
let numbers2 = [];
let numbers3 = [2, 4, 6, 8];

function checkForThree(arr) {
  return arr.includes(3);
};

console.log(checkForThree(numbers1)); // => true
console.log(checkForThree(numbers2)); // => false
console.log(checkForThree(numbers3)); // => false
```

10.

```
let arr = [
  ["hello", "world"],
  ["example", "mem", null, 6, 88],
  [4, 8, 12]
];

console.log(arr);

arr[1][3] = 606 // but with 'let' it won't work ?

console.log(arr);
```

## [Objects](https://launchschool.com/books/javascript/read/objects)

- Objects, behaviour and state.

### [What are Objects?](https://launchschool.com/books/javascript/read/objects#whatareobjects)

- Ruby hashes (with key differences)
  - store key value pairs.
  - The keys are strings or symbols.
  - Values can be type
  - We create an object with the **object literal** syntax.

```
let person = {
  name:    'Jane',
  age:     37,
  hobbies: ['photography', 'genealogy'],
};
```

- Or on a single line:

```
let person = { name: 'Jane', age: 37, hobbies: ['photography', 'genealogy'] }
```

- We can access the values in two ways:
  - 'person.name' => 'Jane' (dot notation).
  - 'person[name]` => 'Jane' (bracket notation).
- dot notation is prefereable, but when the key is stored in a variable, you need to use bracket notation:

```
let key = 'name'
person[key]
```

- Adding pairs:
  - `person.height = '5 ft'
  - `person[;gender'] = 'female'`

- It's the same for adding kv pairs.

```
let person = {
  name: 'Jane',
  age: 37,
  hobbies: ['photography', 'genealogy']
};

let personOneLine = { name: 'Jane', age: 37, hobbies: ['photography', 'genealogy'] }
let ageVar = 'age'

console.log(person.name);
console.log(person['name']); // has to be as a string
console.log(person[ageVar]);

person.height = '5 ft';
person['gender'] = 'female'

console.log(person); 

// {
//   name: 'Jane',
//   age: 37,
//   hobbies: [ 'photography', 'genealogy' ],
//   height: '5 ft',
//   gender: 'female'
// }

console.log(delete person.age); // true
console.log(delete person['gender']); // => true
console.log(delete person['blah']) // => true

console.log(person);

// {
//   name: 'Jane',
//   hobbies: [ 'photography', 'genealogy' ],
//   height: '5 ft'
// }
```

#### `delete`

- key-word for deleting kv pairs. Returns a boolean. 

```
const MyObj = { foo: "bar", qux: "xyz" }
MyObj.qux = "hey there"
MyObj.pi = 3.2415
console.log(MyObj)

MyObj = {} // TypeError: Assignment to constant variable.
```

### `freeze`

```
const MyObj = Object.freeze({ foo: "bar", qux: "xyz"})
MyObj.qux = "hey there"
console.log(MyObj); // => { foo: 'bar', qux: 'xyz' }
```

### [Objects vs. Primitives](https://launchschool.com/books/javascript/read/objects#objectsvsprimitives)

- Primitives:
  - Strings
  - Numbers
  - Booleans
  - `null`
  - `undefined`
  - `bigints`
  - `symbols`
- Objects
  - Simple Objects
  - Arrays
  - Dates
  - Functions

- Objects are complex values composed of primitive values or other objects. For example an array (as an object) has a `length` property that contains the number corresponding to its length.
- Objects are usually mutable.
#### atomic
- Primitives on the other hand are always immutable, in that they don't have parts that one can change. They are therefore called 'atomic', because they are 'indivisible.
- Variables that contain primitives can only be used in an expression or reassigned to some other value.
- All operations on primitive values return new values. Even in `0 + 0` the resulting `0` is a new `0`. **question** -> if `0` is an unchanging value in memory, how can there be a new or different `0` ?

#### functions are objects

- They can be:
  - assigned to variables.
  - passed to other functions as arguments.
  - returned by functions.

```
function hello() {
  console.log("Hello there!");
}

hello(); // => Hello there!

let greet = hello;
greet(); // => Hello there!

// --------------------------- --------------------------- ---------------------------

let sandy = function() {     // this is a function expression rather than a function declaration
  console.log("I am Sandy");
}

sandy(); // => I am Sandy

// --------------------------- --------------------------- ---------------------------

Array.prototype.push = function(newValue) {
  this[this.length] = newValue;
}

let array = [1, 2, 3];
array.push(4);
console.log(array); // => [ 1, 2, 3, 4 ]

// We can use this aspect of JS to define methods as object methods.

// --------------------------- --------------------------- ---------------------------

// And we can pass functions around as arguments and return values, like this:

Array.prototype.forEach = function(thisIsACallback) {
  for (let index = 0; index < this.length; index += 1) {
    thisIsACallback(this[index]);
  }
}

let array1 = [1, 2, 3];

array1.forEach(function  callback(value) { console.log(value) }) // 1 2 3

// --------------------------- --------------------------- ---------------------------

function greeter(greeting) {
  return function(name) {
    return console.log(`${greeting} ${name}`);
  }
}

let hello2 = greeter('Hello');
// let hi = greeter('Hi');

hello2('Trevor');
hello2('Jeremiah');

// This example uses a 'closure'. This is how the returned function still has acess to the value of `greeting` after `greeter` is finished (or more correcty: "returns").
```

#### What isn't either an Object or a Primative?

- Anything which is not data/a function:
  - variables & other identifiers (like function names).
  - Statements:
    - `if`
    - `return`
    - `try`
    - `while`
    - `break`
  - Keywords:
    - `new`
    - `function`
    - `let`
    - `const`
    - `class`
  - comments
  - There's more...

### [Prototypes](https://launchschool.com/books/javascript/read/objects#prototypes)

- JS objects can inherit. Parents are called "prototypes of ${child}".
- This would mean that the child now has access to properties **defined on** the parent.
- Prototypes implement inheritence in JS.
- We can demonstate this with the static method (?) `Object.create`

```
let bob = { name: 'Bob', age: 22 };
let studentBob = Object.create(bob);
studentBob.year = 'Senior';

console.log(studentBob.name); // 'Bob'

// Even though the creation of studentBob does not define a name property, it has one by virtue of inheriting it from its parent
```

- We'll look at other ways to inherit later.

### [Iteration](https://launchschool.com/books/javascript/read/objects#iteration)

- You can choose to iterate over an objects keys, values or both simultaneously.

#### The for/in loop

- You don't need an:
  - initializer
  - ending condition
  - incremenet clause
- It iterates over all the keys in the object and on each iteration assigns the key to a var for you to use.

```
let person = {
  name: 'Bob',
  age: 30,
  height: '6 ft',
};

for (let prop in person) {
  console.log(person[prop]);
}

// Bob
// 30
// 6 ft
```

- A notable feature of this feature is that it will iterate over an object including both original (inherited) properties, and new ones. Apparently this is sometimes undesireable.

```
let hairyMary = { allTheWayFrae: 'Brixton'};
let hairyMary2 = Object.create(hairyMary)
hairyMary2.iHaveA = 'pair o sand-shoes';
hairyMary2.codLiverOil = 'and the Oh-orange juice'

for (let prop in hairyMary2) {
  console.log(hairyMary2[prop]);
}

// Brixton
// pair o sand-shoes
// and the Oh-orange juice
```

- We can use `hasOwnProperty` method to circumvent this. As below:

```
let obj1 = { a: 1, b: 2};
let obj2 = Object.create(obj1);
obj2.c = 3;
obj2.d = 4;

for (let prop in obj2) {
  if (obj2.hasOwnProperty(prop)) {
    console.log(obj2[prop]);
  }
} // => 3 and 4, because they were not inherited.
```

#### Object.keys

```
let person = {
  name: 'Bob',
  age: 30,
  height: '6 ft',
};

person.numberOfEars = '2 ears';

let personKeys = Object.keys(person);
console.log(personKeys); // => [ 'name', 'age', 'height' ]
personKeys.forEach(key => {
  console.log(person[key]);
});

// Bob
// 30
// 6 ft
// 2 ears
```

#### Order ofobject properties

- Older versions (ES6 and previous) jumbled order. Modern ones don't.
- Most of the time the order s the order in which items are added.
- Exceptions to this are symbols and integers, which will be grouped in the following order:
  - symbol keys
  - strings
  - positive integers ( **question** why "non-negative" ?)
  - **question** (but in my example the order is numbers, then everything else alphabetised).
- So only rely on key order when all keys use only the alphabet.

```
let snape = Symbol("Snape");
let hagrid = Symbol("Hagrid");

let hogwarts = {
  hagrid: "Rubeus",
  ron: 'deSantis',
  1: 'what is this',
  hermione: 'granger',
  snape: 'Severus',
  400: 'yup',
  harry: 'potter',
};

const sortedHogwartsArray = Object.entries(hogwarts).sort(([keyA], [keyB]) => keyA.localeCompare(keyB));
const sortedHogwartsObject = Object.fromEntries(sortedHogwartsArray);

console.log(sortedHogwartsObject); // => { harry: 'potter', hermione: 'granger', ron: 'deSantis' }

// {
//   '1': 'what is this',
//   '400': 'yup',
//   hagrid: 'Rubeus',
//   harry: 'potter',
//   hermione: 'granger',
//   ron: 'deSantis',
//   snape: 'Severus'
// }
```

### [Common Operations](https://launchschool.com/books/javascript/read/objects#commonoperations)

- Unlike JS Arrays, objects don't have many methods. Mostly you just iterate over them. But here are some:

#### Object.values

```
let sizes = {
  big: 'Ooooh, it\'s ever so large',
  medium: 'medium, I\'d say',
  small: 'oh ho, look at the dinky little thing',
};

let sizesValues = Object.values(sizes);
console.log(sizesValues);

// [
//   "Ooooh, it's ever so large",
//   "medium, I'd say",
//   'oh ho, look at the dinky little thing'
// ]
```

### Object.entries

- returns an array of nested arrays containing a kv pair each.

```
let bones = {
  leg: ['tibia', 'femur', 'fibia'],
  arm: ['cloaca', 'lizard-eyes', 'hairy disaster'],
  back: ['spoon', 'ribs'],
}

console.log(Object.entries(bones));

// [
//   [ 'leg', [ 'tibia', 'femur', 'fibia' ] ],
//   [ 'arm', [ 'cloaca', 'lizard-eyes', 'hairy disaster' ] ],
//   [ 'back', [ 'spoon', 'ribs' ] ]
// ]
```

#### Object.assign

- mutates the first argument, leaves the second argument unchanged :

```
let sizes = {
  big: 'Ooooh, it\'s ever so large',
  medium: 'medium, I\'d say',
  small: 'oh ho, look at the dinky little thing',
};

let bones = {
  leg: ['tibia', 'femur', 'fibia'],
  arm: ['cloaca', 'lizard-eyes', 'hairy disaster'],
  back: ['spoon', 'ribs'],
}

Object.assign(sizes, bones); // mutates the first argument
console.log(sizes);

// {
//   big: "Ooooh, it's ever so large",
//   medium: "medium, I'd say",
//   small: 'oh ho, look at the dinky little thing',
//   leg: [ 'tibia', 'femur', 'fibia' ],
//   arm: [ 'cloaca', 'lizard-eyes', 'hairy disaster' ],
//   back: [ 'spoon', 'ribs' ]
// }

console.log(bones); // remains unchanged

// {
//   leg: [ 'tibia', 'femur', 'fibia' ],
//   arm: [ 'cloaca', 'lizard-eyes', 'hairy disaster' ],
//   back: [ 'spoon', 'ribs' ]
// }
```

- If you don't want to fuck up the first object, you can use an empty object as the first argument and have a total of 3 arguments.

### [Objects vs. Arrays](https://launchschool.com/books/javascript/read/objects#objectvsarrays)

- Objects if:
  - The items have names
- Arrays if:
  - The order matters
  - I need a stack("last in first out")/queue("first in first out") structure.

### [Summary](https://launchschool.com/books/javascript/read/objects#summary)


### [Exercises](https://launchschool.com/books/javascript/read/objects#exercises)

1. `person.name` or `person['name']`
2. All of them are valid, but JS will coerce them into strings. Therefore `'1'` and `1` will be the same key. Be careful of this, it catches everyone out sooner or later.

```
// trick question : all are valid, but the non-strings will be coerced into strings.

let myObj = {}
myObj[true] = 1 // will be overwritten
myObj['true'] = 2
myObj[1] = 3 // will be overwritten
myObj['1'] = 4
myObj[undefined] = 5
myObj['hello world'] = 6

console.log(myObj);
```

3.

```
let myArray = {
  length: 4,
  1: 'john',
  3: 'barry',
  2: 'jennifer',
};

for (let i = 0; i < myArray.length; i += 1) {
  console.log(myArray[i]);
}
```

4.

```
// Create an array from the keys of the object obj below, with all of the keys converted to uppercase. Your implementation must not mutate obj.

let obj = {
  b: 2,
  a: 1,
  c: 3,
};

let output = Object.keys(obj);
console.log(output.map((e) => e.toUpperCase()));
console.log(obj);
```

5.

```
let myProtoObj = {
  foo: 1,
  bar: 2,
};

let obj = Object.create(myProtoObj);

console.log(obj);
```

6.

```
// PRIMATIVES:

"foo"
3.1415
false
undefined

// OBJECTS:

[ 'a', 'b', 'c' ]
function bar() { return "bar"; }
{ a: 1, b: 2 }

// NEITHER:

foo

```

7.

```
let myProtoObj = {
  foo: 1, 
  bar: 2,
};

let myObj = Object.create(myProtoObj);

myObj.qux = 3;

let objKeys = Object.keys(myObj);
objKeys.forEach(function(key) {
  console.log(key);
});

// qux

for (let key in myObj) {
  console.log(key);
}

// qux
// foo
// bar
```

8.

```
let objToCopy = {
  foo: 1,
  bar: 2,
  qux: 3,
};

let newObj = copyObj(objToCopy);
console.log(newObj);        // => { foo: 1, bar: 2, qux: 3 }

let newObj2 = copyObj(objToCopy, [ 'foo', 'qux' ]);
console.log(newObj2);       // => { foo: 1, qux: 3 }

let newObj3 = copyObj(objToCopy, [ 'bar' ]);
console.log(newObj3);       // => { bar: 2 }

// My solution:

function copyObj(obj, keysArr = Object.keys(obj)) {
  output = {}
  keysArr.forEach(function(key) {
    output[key] = obj[key]
  })
  return output
}

// LS solution:

function copyObj(sourceObject, keys) {
  let destinationObject = {};

  if (keys) {
    keys.forEach(function(key) {
      destinationObject[key] = sourceObject[key];
    });

    return destinationObject;
  } else {
    return Object.assign(destinationObject, sourceObject);
  }
}
```

9. 

```
let foo = {
  a: 'hello',
  b: 'world',
};

let qux = 'hello';

function bar(argument1, argument2) {
  argument1.a = 'hi';
  argument2 = 'hi';
}

bar(foo, qux);

console.log(foo.a); // hi
console.log(qux); // hello
```

10.

```
[1, 2, ["a", ["b", false]], null, {}] // 6P, 4O
```

11.

```
let obj = {
  foo: { a: "hello", b: "world" },
  bar: ["example", "mem", null, { xyz: 6 }, 88],
  qux: [4, 8, 12]
};

obj.bar[3].xyz = 606

console.log(obj)
```

12.

```
function foo(bar) {
  console.log(bar, bar, bar);
}

let bar = foo;

foo("hello"); // should print "hello hello hello"
bar("hi");    // should print "hi hi hi"
```

13.

```
function foo(bar) {
  console.log(bar());
};

foo(function() { return "Welcome"});
foo(function() { return 3.1415});
foo(function() { return [1, 2, 3]});
```

14.

```
function hello(greeting, name) {
  return greeting + ' ' + name;
}

function xyzzy() {
  return { a: 1, b: 2, c: [3, 4, 5], d: {} };
}

const howdy = hello('Hi', 'Grace');
let foo = xyzzy();

// Variables: hello, xyzzy, greeting, name, howdy, foo.
// Object property names: a:, b:, c:, d:
// Primitive values: ' ', 1, 2, 3, 4, 5, 'Hi', 'Grace'
// Objects: hello, xyzzy, [3, 4, 5], {}, { a: 1, b: 2, c: [3, 4, 5], d: {} }
```

15.

```
function bar(arg1, arg2) {
  let foo = 'Hello';
  const qux = {
    abc: [1, 2, 3, [4, 5, 6]],
    def: null,
    ghi: NaN,
    jkl: foo,
    mno: arg1,
    pqr: arg2,
  };

  return qux;
}

let result = bar('Victor', 'Antonina');

// Variables: bar, arg1, arg2, foo, qux, result
// Object Property Names: abc, def, ghi, jkl, mno, pqr, 0, 1, 2, 3 (indexes).
// Primitive values: 'Hello', abc, def, ghi, jkl, mno, pqr, 1, 2, 3, 4, 5, 6, 'Victor', 'Antonina', null, NaN
// Objects: bar, {
  //   abc: [1, 2, 3, [4, 5, 6]],
  //   def: null,
  //   ghi: NaN,
  //   jkl: foo,
  //   mno: arg1,
  //   pqr: arg2,
  // }, [1, 2, 3, [4, 5, 6]], [4, 5, 6]

```

## [More Stuff](https://launchschool.com/books/javascript/read/more_stuff)

### [Variables as Pointers](https://launchschool.com/books/javascript/read/more_stuff#variablesaspointers)

- "pointers" (AKA "references).
- 'the pointes stored in variables are references' ... hmmmmmm

#### Working with primitive values

- Assigning a second variable to point to the same value as the first variable. Changing the value of the first variable will not alter the second variable. (like Ruby).
- Strings are primitive values, as you know. However they are not stored directly in the variable, like most other primitive values. But they behave as though they are.

#### Working with objects and non-mutating operations

- When we initialize `a` with `b` JS copiesnthe pointer, not the value. So mutating the value affects `a` and `b`. It can be called 'aliasing' when two vars refer to the same thing.
- Remember primatives can't be mutated, so giving a var a new primitive value will never effect other vars pointing to that value. 

#### Gotcha

````
let g = ['a', 'b', 'c']
let h = g
g[1] = 'x'
console.log(g); // => [ 'a', 'x', 'c' ]
console.log(h); // => [ 'a', 'x', 'c' ]
````

- This code doesn't mutate the element. It does mutate the array.

### Takeaway

- Same as Ruby, right?
- The idea that JS stores primitive values directly in variables is an oversimplification, but sufficient for now.

### [for/in and for/of](https://launchschool.com/books/javascript/read/more_stuff#forinforof)

- For looping easily over object properties.

```
let obj = { foo: 1, bar: 2, qux: 'c' };
for (let key in obj) {
  console.log(key);
}
// Output:  foo
//          bar
//          qux

let arr = [ 10, 20, 30 ]
for (let value in arr) {
  console.log(value);
}
// Output:  0
//          1
//          2

// because index properties are strings, this happens:

let arr2 = [ 10, 20, 30 ]
for (let index in arr2) {
  console.log(index + 5);
}
// Output:  05
//          15
//          25
```

- for/of: It's newer, and works on 'any iteratable collection' (so Strings as well)

```
let arr = [ 10, 20, 30 ]
for (let value of arr) {
  console.log(value);
}
// Output:  10
//          20
//          30

let str = "abc";
for (let char of str) {
  console.log(char);
}
// Output: a
//         b
//         c
```

### [Method Chaining](https://launchschool.com/books/javascript/read/more_stuff#methodchaining)

```
// -------- syntax variation: 1 ----------
let str = 'Pete Hanson';
let names = str.toUpperCase().split(' ').reverse().join(', ');
console.log(names); // => HANSON, PETE

// -------- syntax variation: 2 ----------

let str2 = 'Pete Hanson';
let names2 = str2.toUpperCase()
               .split(' ')
               .reverse()
               .join(', ');
console.log(names2);

// -------- syntax variation: 3 ----------

let str3 = 'Pete Hanson';
let names3 = str3.toUpperCase()
  .split(' ')
  .reverse()
  .join(', ');
console.log(names3);

// -------- syntax variation: 4 ----------

let str4 = 'Pete Hanson';
let names4 = str4.toUpperCase().
                split(' ').
                reverse().
                join(', ');
console.log(names4);
```

#### Optional Chaining

- like normal chainign, but if any of the values return `nullish` it returns `undefined`.
- Most often used in a chain where the first expression may return a nullish value

```
function reverse_words(sentence) {
  return sentence?.split(' ')
                  .reverse()
                  .join(' ');
}
console.log(reverse_words("Four score and seven"))
// seven and score Four

console.log(reverse_words(null))
// undefined
```

- But be careful where you deploy these, because usually an error message is a useful thing to see.

### [Regex](https://launchschool.com/books/javascript/read/more_stuff#regex)

- Here we'll look at the most common use case. Whether a string matches a regex.

```
// RegExp is the class.

a = /o/.test('bobcat')
console.log(a); // true
b = /l/.test('bobcat')
console.log(b) // false
```

#### `match`

```
word = "bobcat"
resulta = word.match(/match/) // No match
console.log(resulta) // => null
resultb = word.match(/[bct]/g) // Global match
console.log(resultb) // => [ 'b', 'b', 'c', 't' ]
resultc = word.match(/b((o))b/) // Singular match with groups
console.log(resultc) // => [ 'bob', 'o', 'o', index: 0, input: 'bobcat', groups: undefined ]
```

- No match retruns `null`
- This method has performance costs, and so `.test` is preferable, unless you need all the information about groups, index and input.

### [The Math Object](https://launchschool.com/books/javascript/read/more_stuff#themathobject)

```
console.log(Math.sqrt(36)); // => 6
console.log(Math.sqrt(302910)); // => 550.3726010622258
console.log(Math.PI); // 3.141592653589793
```

### [Dates](https://launchschool.com/books/javascript/read/more_stuff#dates)

```
let date = new Date ('December 25, 2012')
console.log(date.getDay()); // => 2 (0 = Sun, 6 = Sat, so 2 = Tue)

function getDayOfWeek(date) {
  let daysOfWeek = [
    'Sunday',
    'Monday',
    'Tuesday',
    'Wednesday',
    'Thursday',
    'Friday',
    'Saturday',
  ];

  return daysOfWeek[date.getDay()];
}

console.log(getDayOfWeek(date)); // => Tuesday
console.log(date.toLocaleDateString(date)) // =? 12/25/2012
```

### [Exceptions](https://launchschool.com/books/javascript/read/more_stuff#exceptions)

- `try`, `catch` and less often `finally`.

```
let names = ['bob', 'joe', 'steve', undefined, 'frank'];
names.forEach(name => {
  try {
    console.log(`${name}'s name has ${name.length} letters in it.`);
  } catch (exception) {
    console.log('Something has gone awry');
  }
});

// bob's name has 3 letters in it.
// joe's name has 3 letters in it.
// steve's name has 5 letters in it.
// Something has gone awry
// frank's name has 5 letters in it.
```

- Mishandling an exception is usually more destructive than letting the program crash.

#### throw

```
function foo(number) {
  if (typeof number !== "number") {
    throw new TypeError("expected a number");
  }

  return `${number} is a number`
}

console.log(foo(2)); // => 2 is a number
console.log(foo(true)); // => TypeError: expected a number
```

 - Don't raise exceptions for predictable results. Exceptions should really be for exceptions. That means:
   - situations your program cannot easily control. FOr instance, not being able to connect to a remote site in a web application.
 - The example above is therefore not a justified usage of exception handling.

#### syntax error

- Unlike `TypeError`s, these are immediately encountered when the program is run, so you can't catch them.
- Remember:
  - It has nothing to do with the value of any of your variables.
  - It is possible for the error to be caught much later in the program than it's cause. For instance a missing `{`. It's more common than you imagine.
  - The fact that none of the program executes reveals that programs have a preliminary phase of checking syntax before the execution phase.

### [Stack Traces](https://launchschool.com/books/javascript/read/more_stuff#readingstacktraces)

```
function foo() {
  console.log(bar);
}

foo();

/*
hello there: node 13_stack_traces.js 
/Users/sandyboy/Desktop/launch_school_books/JS_book_exercises/10_more_stuff/13_stack_traces.js:2
  console.log(bar);
              ^

ReferenceError: bar is not defined
    at foo (/Users/sandyboy/Desktop/launch_school_books/JS_book_exercises/10_more_stuff/13_stack_traces.js:2:15)
    at Object.<anonymous> (/Users/sandyboy/Desktop/launch_school_books/JS_book_exercises/10_more_stuff/13_stack_traces.js:5:1)
    at Module._compile (node:internal/modules/cjs/loader:1378:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1437:10)
    at Module.load (node:internal/modules/cjs/loader:1212:32)
    at Module._load (node:internal/modules/cjs/loader:1028:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:142:12)
    at node:internal/main/run_main_module:28:49

Node.js v21.6.2
*/

```

- Your stack traces are important. They will show you where and what the problem is. Ignore them and you may be creating more work for yourself.

### [ES6 and Beyond](https://launchschool.com/books/javascript/read/more_stuff#essixandbeyond)

- JavaScript's real name is "ECMAScript".
- A recent updated version is called "ECMAScript 6" AKD "ES6". )or even "ES2015".
- Before ES6 there weren't `let` and `const` or block scopes, which caused lots of problems. Prior to that vars were either local to functions or 100% global baby.
- ES6 also introduced arrow functions, which fic "lost execution context" AKA "context loss".
- There's more and it's always expanding.
- This means some Javascript environments may not be up to date. Which lead to the creation of **Babel** : a tool that lets you write code using the latest language features, then run it in old environments.

### [Exercises](https://launchschool.com/books/javascript/read/more_stuff#exercises)

1.

```
let array1 = [1, 2, 3];
let array2 = array1;
array1[1] = 4;
console.log(array2) // [1, 4, 3]
```

2. The `greeting` variable is not defined.

- LS answer:
  - An error occurred in the exercise2.js program on line 4 of the program; a ^ points to where JavaScript thinks the error is in the code: it's pointing to the argument list for console.log.

More specifically, line 6 in the output tells you that a ReferenceError exception occurred and that the name greeting isn't defined. Line 7 repeats some earlier information: JavaScript detected the error at column 15 of line 4 of the program, but it also tells you that the code is in the hello function. Line 8 tells you that hello was called from line 13 of the program in an anonymous function, namely the global-level of the program.

The rest of the output comes from running the code in node and probably isn't useful to you as an application programmer.

3. `console.log(Math.sqrt(37)); // => 6.082762530298219`

4.

```
// if the input is an array:

function largestValueInArray(array) {
  currentLargestValue = array[0]
  array.forEach(function(num) {
    if (currentLargestValue < num) {
      currentLargestValue = num;
    }
  });
  return currentLargestValue;
};

console.log(largestValueInArray([1, 6, 3, 2])); // => 6

// if the input is separate objects:

function largestValueFinder() {
  let array = Array.from(arguments);
  currentLargestValue = array[0]
  array.forEach(function(num) {
    if (currentLargestValue < num) {
      currentLargestValue = num;
    }
  });
  return currentLargestValue;
};

console.log(largestValueFinder(1, 6, 3, 2)); // => 6

// If you're assuming I'll use a Math object:

function largestValueWithMath(array) {
  return Math.max(...array)
}

console.log(largestValueWithMath([1, 2, 3, 6, 4, 2])); // => 6
```

5.


```
function doSomething(string) {
  return string.split(' ').reverse().map((value) => value.length);
}

/*

splits a string into an array of individual words, reverses the order of that array, then returns a new array containing the length of each word.

*/

console.log(doSomething("this summer is all about two things.")); // => [7, 3, 5, 3, 2, 6, 4]
```

6.


```
let words = [
  'laboratory',
  'experiment',
  'flab',
  'Pans Labyrinth',
  'elaborate',
  'polar bear',
];

function allMatches(arr, pattern) {
  let output = [];
  arr.forEach(function(word) {
    if (pattern.test(word)) {
      output.push(word)
    }
  })
  return output;
};
console.log(allMatches(words, /lab/)); // => ['laboratory', 'flab', 'elaborate']
```

7. Exeption handling is writing code to catch errors so that the program does not fail when errors are encountered. We use the keywords `try`, `catch`,  and `finally` to do this.

8.

```
function isNotANumber(value) {
  return value !== value;
};

console.log(isNotANumber(1)); // false
console.log(isNotANumber(true)); // false
console.log(isNotANumber(NaN)); // true
console.log(isNotANumber('NaN')); // false
```

9. (almost)

```
function isNegativeZero(value) {
  return 1 / value === -Infinity;
}
```

10.

```
let y = "5"
y++
// => 5
```



## [Conclusions](https://launchschool.com/books/javascript/read/next_steps)


### [Conclusion & Next Steps](https://launchschool.com/books/javascript/read/next_steps)

- Don't stop.
