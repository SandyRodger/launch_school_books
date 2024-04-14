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
### [Command Line Input](https://launchschool.com/books/javascript/read/input_output#commandlineinput)
### [Input in the Browser](https://launchschool.com/books/javascript/read/input_output#inputinthebrowser)
### [Summary](https://launchschool.com/books/javascript/read/input_output#summary)
### [Exercises](https://launchschool.com/books/javascript/read/input_output#exercises)

## [Functions](https://launchschool.com/books/javascript/read/functions)

### [Using Functions](https://launchschool.com/books/javascript/read/functions#usingfunctions)
### [Arguments & Parameters](https://launchschool.com/books/javascript/read/functions#argumentsparameters)
### [Return Values](https://launchschool.com/books/javascript/read/functions#returnvalues)
### [Default Parameters](https://launchschool.com/books/javascript/read/functions#defaultparameters)
### [Nested Functions](https://launchschool.com/books/javascript/read/functions#nestedfunctions)
### [Functions & Scope](https://launchschool.com/books/javascript/read/functions#functionsscope)
### [Functions vs. Methods](https://launchschool.com/books/javascript/read/functions#functionsvsmethods)
### [Reassignment and Mutation](https://launchschool.com/books/javascript/read/functions#reassignmentandmutation)
### [Mutating the Caller](https://launchschool.com/books/javascript/read/functions#mutatingthecaller)
### [Function Composition](https://launchschool.com/books/javascript/read/functions#functioncomposition)
### [Three Ways to Define a Function](https://launchschool.com/books/javascript/read/functions#threewaystodefineafunction)
### [The Call Stack](https://launchschool.com/books/javascript/read/functions#callstack)
### [Summary](https://launchschool.com/books/javascript/read/functions#summary)
### [Exercises](https://launchschool.com/books/javascript/read/functions#exercises)

## [Flow Control](https://launchschool.com/books/javascript/read/flow_control)

### [Conditionals](https://launchschool.com/books/javascript/read/flow_control#conditionals)
### [Comparisons](https://launchschool.com/books/javascript/read/flow_control#comparisons)
### [Logical Operators](https://launchschool.com/books/javascript/read/flow_control#logicaloperators)
### [Short Circuits](https://launchschool.com/books/javascript/read/flow_control#shortcircuits)
### [Truthiness](https://launchschool.com/books/javascript/read/flow_control#truthiness)
### [Nullish Coalescing Operator](https://launchschool.com/books/javascript/read/flow_control#nullishcoalescing)
### [Operator Precedence](https://launchschool.com/books/javascript/read/flow_control#operatorprecedence)
### [The Ternary Operator](https://launchschool.com/books/javascript/read/flow_control#theternaryoperator)
### [Switch Statement](https://launchschool.com/books/javascript/read/flow_control#switchstatement)
### [Summary](https://launchschool.com/books/javascript/read/flow_control#summary)
### [Exercises](https://launchschool.com/books/javascript/read/flow_control#exercises)

## [Loops & Iterating](https://launchschool.com/books/javascript/read/loops_iterating)

### [while Loops](https://launchschool.com/books/javascript/read/loops_iterating#whileloops)
### [for Loops](https://launchschool.com/books/javascript/read/loops_iterating#forloops)
### [Controlling Loops](https://launchschool.com/books/javascript/read/loops_iterating#controllingloops)
### [Array Iteration](https://launchschool.com/books/javascript/read/loops_iterating#arrayiteration)
### [Recursion](https://launchschool.com/books/javascript/read/loops_iterating#recursion)
### [Summary](https://launchschool.com/books/javascript/read/loops_iterating#summary)
### [Exercises](https://launchschool.com/books/javascript/read/loops_iterating#exercises)

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

## [More Stuff](https://launchschool.com/books/javascript/read/more_stuff

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
