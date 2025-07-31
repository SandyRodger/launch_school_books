# [Introduction](https://launchschool.com/books/python/read/introduction)

## GETTING STARTED
## Introduction
## [A Brief Python History](https://launchschool.com/books/python/read/introduction#briefhistory)
## [Python's Future](https://launchschool.com/books/python/read/introduction#pythonsfuture)

## [Abstraction](https://launchschool.com/books/python/read/introduction#abstraction)

- i know this... ?    

## Who This Book is For
## What's Not Covered
## How to Read This Book
## [Preparations](https://launchschool.com/books/python/read/preparations)
### [Installing python](https://launchschool.com/books/python/read/preparations#installingpython)

echo "alias python=python3" >> ~/.bash_profile
python --version

### [using the REPL](https://launchschool.com/books/python/read/using_python#usingrepl)
### [Stylish Python](https://launchschool.com/books/python/read/using_python#stylishpython)

## Using Python
### [Indentation](https://launchschool.com/books/python/read/using_python#indentation)

- ok
  
### [Using the REPL](https://launchschool.com/books/python/read/using_python#usingrepl)

- `help()`
- `help(len)`
- `help(str)`
- `bool` class => `help(3 == 4)`

#### Additional REPL Tips

- `exit()`
- `quit()`
- control-D

#### Copying and Pasting in the Python REPL

### [Running Python Code From a File](https://launchschool.com/books/python/read/using_python#runningpythoncode)


### [Stylish Python](https://launchschool.com/books/python/read/using_python#stylishpython)

- 'Use spaces around operators, except for **, which should not be surrounded by spaces:'
  - `print(8**3)`
- comment with `#`.
- The block ends when you outdent back to the original level.
- You can also have multiple levels of indentation, though you should avoid using more than two levels.
- 
### [PEPs](https://launchschool.com/books/python/read/using_python#peps)

- style guide for python AKA PEP 8.

### [Continuation Lines](https://launchschool.com/books/python/read/using_python#continuationlines)

- string literals:

```
return ("This is a long string. "
        "It's actually very long. "
        "It spans multiple lines. "
        "Are you getting tired of this? "
        "So am I.")
```

- fstrings (?!) and rstrings (?!) triple quoted strings (?!)
- (Then there's a bit about how to write various collections over multiple lines. This is straight-forward, but I have not yet learnt about these collections and how they work. They look similar to arrays, tuples and objects in other languages.)
- End collections with a comma, like javascript objects.
- use parentheses:

```
return (obj.bar1
      + obj.bar2
      + obj.bar3)
```

- use backslash to end a line you want to continue:

```
result = value1 + \
         value2 + \
         value3
```

### [Using JupyterLab/Jupyter Notebook](https://launchschool.com/books/python/read/using_python#usingjupyter)

- alternative REPLs
- don't know what to do with this: https://jupyter.org/try-jupyter/lab/

```
import platform
platform.python_version()
# '3.13.1'
```

- installed with `brew install jupyterlab`

### [Debugging Python Code with print](https://launchschool.com/books/python/read/using_python#debuggingwithprint)

- Pdb module for later

### [About the Exercises](https://launchschool.com/books/python/read/using_python#aboutexercises)
### Exercises

- yup

## [Data Types](https://launchschool.com/books/python/read/data_types)

### Data Types

- Everything with a value in Python is said to be an object. (so like Ruby)
- Python has more classes than most. Here are just some:
  - integers
  - floats
  - boolean
  - strings
  - ranges
  - tuples
  - lists
  - **dictionaries**
  - sets
  - **frozen sets**
  - functions
  - **noneType** ( some call this a primitive )

### [Literals](https://launchschool.com/books/python/read/data_types#literals)

```
'Hello, world!'   # str literal
3.141592          # float literal
True              # bool literal
{'a': 1, 'b': 2}  # dict literal
[1, 2, 3]         # list literal
(4, 5, 6)         # tuple literal
{7, 8, 9}         # set literal
```

- not all objects have literal forms:

```
range(10)         # Range of numbers: 0-9
range(1, 11)      # Range of numbers: 1-10
set()             # Empty set
frozenset([1, 2]) # Frozen set of values: 1 and 2
```

### [Numeric Values](https://launchschool.com/books/python/read/data_types#numericvalues)

- skip

### [Variables and Assignment](https://launchschool.com/books/python/read/data_types#variablesassignment)

- skim

### [Boolean Values](https://launchschool.com/books/python/read/data_types#booleanvalues)

- In Python, booleans sometimes act like numeric values: you can use them in mathematical and comparison expressions. You shouldn't do that, really.
- skim

### [Text Sequences](https://launchschool.com/books/python/read/data_types#textsequences)

- strings of characters.
- There is one significant difference between a text sequence and an ordinary sequence. Ordinary sequences contain zero or more objects, but a text sequence does not contain any objects: it simply contains the characters (or bytes) that make up the text sequence. Those characters or bytes are not objects; they are simply part of the value.

#### String Literals and Dealing With Quotes

```
'Hi there'                      # Single quotes
"Monty Python's Flying Circus"  # Double quotes

# Triple single quotes
'''King Arthur: "What is your name?"
Black Knight: "None shall pass!"
King Arthur: "What is your quest?"
Black Knight: "I have no quarrel with you,
               but I must cross this bridge."
'''

# Triple double quotes
"""Man: "Is this the right room for an argument?"
Other Man: "I've told you once."
Man: "No you haven't!"
"""
```

- triple quotes are often used for multi-line strings and a special kind of comment

`print("C:\\Users\\Xyzzy")  # Each \\ produces a literal \`

#### Indexing Strings

`my_str[1]`
`my_str[-3]`

#### Raw Strings and f-Strings

- string literals with an `r` prefix are raw string literals.Raw string literals don't recognise escapes like `/`.

```
# Both of these print C:\Users\Xyzzy
print("C:\\Users\\Xyzzy")  # Each \\ produces a literal \
print(r"C:\Users\Xyzzy")  # raw string literal
```

- The same with `f` for formatted string literals. f strings enable string interpolation.
- escape curly braces by doubling them:

```
foo = 'hello'
print(f'Use {{foo}} to embed a string: {foo}')
# Use {foo} to embed a string: hello
```

- Make numbers more readable with this:

```
print(f'{123456789:_}')       # 123_456_789
print(f'{123456789:,}')       # 123,456,789
```

### [Functions](https://launchschool.com/books/python/read/data_types#functions)

- of function type

### [None: When You Want Nothing](https://launchschool.com/books/python/read/data_types#none)

- `None` -> the absence of value. MIssing, unset, unavailable data, sometimes an error.

### [Sequences](https://launchschool.com/books/python/read/data_types#sequences)

#### Lists and Tuples

- list literals use square brackets
- tuples use parentheses
- Lists are mutable, tuples are immutable.
- If you want to define a tuple with one element you must include a comma like this:
```
my_tuple = (1,)
print(type(my_tuple))        # <class 'tuple'>
```

#### Ranges

```
>>> tuple(range(5))
(0, 1, 2, 3, 4)

>>> tuple(range(5, 10))
(5, 6, 7, 8, 9)

>>> list(range(1, 10, 2))
[1, 3, 5, 7, 9]

>>> list(range(0, -5, -1))
[0, -1, -2, -3, -4]
```

### [Mappings](https://launchschool.com/books/python/read/data_types#mappings)

- unordered collections of objects
- This book just deals with dictionaries, which are like javascript objects.

```
my_dict = {
  'dog': 'barks',
  'wind': 'blows',
  'fire': 'burns'
}
print(my_dict)
```

- The only significant requirement for keys is that they are hashable.

### [Sets](https://launchschool.com/books/python/read/data_types#sets)

- unordered collections of unique objects. (the objects are sometimes called members)

```
d1 = {}         # Empty dict
print(type(d1))
# <class 'dict'>

s1 = set()      # Empty set
print(s1)
set()

# Create a set from a literal
s2 = {2, 3, 5, 7, 11, 13}
print(s2)
{2, 3, 5, 7, 11, 13}

# Create a set from a string
s3 = set("hello there!")
{'t', 'o', 'e', 'l', ' ', 'h', '!', 'r'}
```

### [Summary](https://launchschool.com/books/python/read/data_types#summary)
### Exercises

1. all correct
- 'True' => string
- False => Boolean
- (1, 2, 3) => Tuple
- 1.5 => float
- [1, 2, 3] List
- 2 => Integer
- rage(5) => range
- {1, 2, 3} => Set
- None => none
- {'foo': 'bar'} => dictionary.

2. yup
`names = ('Asta', 'Butterscotch', 'Pudding', 'Neptune', 'Darwin')`

3. 
```
pet = {
  'Asta':	'dog',
  'Butterscotch':	'cat',
  'Pudding':	'cat',
  'Neptune':	'fish',
  'Darwin':	'lizard',
}
```

## [Basic Operations](https://launchschool.com/books/python/read/basic_ops)

- `len()`
- 3 types:
  - Built-in => available everywhere
  - standard => needn't downlaod them but, but need to import them.
  - non-standard => download them

### [Arithmetic Operations](https://launchschool.com/books/python/read/basic_ops#arithmeticoperations)

- `/` and `//` for Integer division? => rounds it.

```
print(16 // 3)     # 5
print(16 // -3)    # -6
print(16 // 2.3)   # 6.0
print(-16 // 2.3)  # -7.0
```

- there are slight imprecisons. 0.1 + 0.2 is not exaclty equal to 0.3.
- be preciser with this:

```
import math
math.isclose(0.1 + 0.2, 0.3)  # True
```
- or this:
```
from decimal import Decimal
Decimal('0.1') + Decimal('0.2') == Decimal('0.3')
# True
```


### [Equality Comparison](https://launchschool.com/books/python/read/basic_ops#equalitycomparison)

- `==`

### [Ordered Comparisons](https://launchschool.com/books/python/read/basic_ops#orderedcomparisons)

- skim
- capitalsa re less than lower case in comparison

### [String Concatenation](https://launchschool.com/books/python/read/basic_ops#stringconcatenation)



### [Coercion](https://launchschool.com/books/python/read/basic_ops#coercion)

#### type coercion

```
print(int('5'))               # 5
print(float('3.141592'))      # 3.141592
```
#### Strings to Numbers

#### Numbers to Strings

#### Implicit Coercion

-  Python implicitly coerces True to the integer value 1 and False to 0

### [Determining Types](https://launchschool.com/books/python/read/basic_ops#determiningtypes)

#### type function

```
print(type(1))         # <class 'int'>
print(type(3.14))      # <class 'float'>
print(type(True))      # <class 'bool'>
print(type('abc'))     # <class 'str'>
print(type([1, 2, 3])) # <class 'list'>
print(type(None))      # <class 'NoneType'>

foo = 42               # Variables work, too
print(type(foo))       # <class 'int'>
```

#### dunder name

```
print(type('abc').__name__)   # str
print(type(False).__name__)   # bool
print(type([]).__name__)      # list
```

#### type + is

```
print(type('abc') is str)     # True
print(type('abc') is int)     # False
print(type(False) is bool)    # True
print(type([]) is list)       # True
print(type([]) is set)        # False
```

- or `isinstance` function when dealing with inheritance.
#### isinstance

```
print(isinstance('abc', str))    # True
print(isinstance([], set))       # False

class A:
    pass

class B(A):
    pass

b = B()

print(type(b).__name__) # B
print(type(b) is B)     # True
print(type(b) is A)     # False (b's type is
                        # not A)
print(isinstance(b, B)) # True
print(isinstance(b, A)) # True (b is instance of A and B)
```

### [String Representations](https://launchschool.com/books/python/read/basic_ops#stringrepresentations)

- `str`
- `repr`
- ... i have not understood this

### [Collection and String Lengths](https://launchschool.com/books/python/read/basic_ops#collectionstringlengths)

- `len()`

```
print(len('Launch School'))       # 13 (string)
print(len(range(5, 15)))          # 10 (range)
print(len(range(5, 15, 3)))       # 4 (range)
print(len(['a', 'b', 'c']))       # 3 (list)
print(len(('d', 'e', 'f', 'g')))  # 4 (tuple)
print(len({'foo': 42, 'bar': 7})) # 2 (dict)
print(len({'foo', 'bar', 'qux'})) # 3 (set)
```

### [Indexing and Key Access](https://launchschool.com/books/python/read/basic_ops#indexingkeyaccess)

- yep, nothing to see here.
- Unline javascript, trying to access a property on an object that does not exist will raise an Error:

```
print(my_dict['d'])           # KeyError: 'd'
```

```
my_dict = {
    'dog': 'barks',
    'cat': 'meows',
    'pig': 'oinks',
}

my_dict['pig'] = 'snorts'
print(my_dict)
# Pretty printed for clarity
# {
#     'dog': 'barks',
#     'cat': 'meows',
#     'pig': 'snorts'
# }

my_dict['fish'] = 'glub glub'
print(my_dict)
# Pretty printed for clarity
# {
#     'dog': 'barks',
#     'cat': 'meows',
#     'pig': 'snorts',
#     'fish': 'glub glub'
# }
```

### [Expressions and Statements](https://launchschool.com/books/python/read/basic_ops#expressionsandstatements)

- An expression combines values, variables, operators, and calls to functions to produce a new object;
  - Literals: 5, 'Karl', 3.141592, True, None
  - Variable references: foo or name when these variables have been previously defined.
  - Arithmetic operations: x + y or a * b - 5.
  - Comparison operations: 'x' == 'x' or 'x' < 'y'.
  - String operations: 'x' + 'y' or 'x' * 32.
  - Function calls: print('Hello') or len('Python').
  - Any valid combination of the above that evaluates to a single object.
- A statement, on the other hand, is an instruction that tells Python to perform an action of some kind:
  - Assignment: like x = 5. This doesn't evaluate as a value; it assigns a value to a variable.
  - Control flow: such as if, else, while, for, and so on. These determine the flow of your program but don't evaluate as a value themselves.
  - Function and class definitions: using def or class.
  - Return statements: like return x, which tells a function to exit and return a value. return itself doesn't return a value; it informs the function what value it should return.
  - Import statements: such as `import math`.
 
- Key differences:
  - expressions always return a value, statements do not
  - expressions are often parts of statements (in `y = x + 5` `x + 5` is an expression)
  - Statements often represent bigger chuncks of functionality like loops or conditionals; expressions deal with determining values.

### [Expression Evaluation](https://launchschool.com/books/python/read/basic_ops#expressionevaluation)

- precedence. But you should use parentheses to make it clear.

### [Output vs. Return Values](https://launchschool.com/books/python/read/basic_ops#outputvsreturnvalues)

### [Summary](https://launchschool.com/books/python/read/basic_ops#summary)

### Exercises

1
```
sandy = 'sandy'
rodger = 'rodger'
full_name = sandy + ' ' + rodger
print (full_name)
```

2.
- `4936 - 4930`
- `int(((4936 % 49) - 6) / 10)`
- `(4936 // 100) - 40`
- `4936 // 1000`

3. `510`
4. `print(int('5') + int('10'))`
5. yes - correct
6. false
7. `int('3.1415')` => valueError
8. true -> correct

## [Variables](https://launchschool.com/books/python/read/variables)

- `def` creates functions
- call a fucntion with `()`
  
### [Variables and Variable Names](https://launchschool.com/books/python/read/variables#variablesandvariablenames)

#### identifiers



### [Naming Conventions](https://launchschool.com/books/python/read/variables#namingconventions)

- snake_case
- constants -> SCREAMING_SNAKE_CASE
- class names -> PascalCase

### [Creating and Reassigning Variables](https://launchschool.com/books/python/read/variables#creatingandreassigningvariables)



### [Creating Constants](https://launchschool.com/books/python/read/variables#creatingconstants)



### [Expressions and Assignment](https://launchschool.com/books/python/read/variables#expressionsassignment)


### [Augmented Assignment](https://launchschool.com/books/python/read/variables#augmentedassignment)



### Reassignment vs. Mutation
### Summary
### Exercises

## Input/Output
### Terminal Output
### Terminal Input
### Summary
### Exercises

## Functions and Methods
### Calling Functions
### Built-in Functions
### Creating Functions
### Scope
### Namespaces
### Arguments & Parameters
### Return Values
### Default Parameters
### Functions vs. Methods
### Mutating the Caller
### Summary
### Exercises

## Flow Control
### Conditionals
### Comparisons
### Logical Operators
### Short Circuits
### Truthiness
### Logical Operator Precedence
### match/case Statement
### Ternary Expressions
### Summary
### Exercises

## COLLECTIONS AND ITERATION

## Intro to Collections
### Collection Types
### What are Sequences?
### What are Sets?
### What are Mappings?
### Sequence Constructors
### Summary
### Exercises

## Using Collections
### Indexing
### Slicing
### Key-Based Access
### Common Collection Operations
### String Operations
### Nested Collections
### Comparing Collections
### Summary
### Exercises

## Loops and Iterating
### while Loops
### for Loops
### Controlling Loops
### Simultaneous Iteration
### Comprehensions
### Summary
### Exercises

## ADDITIONAL TOPICS
## Variables As Pointers
### Variables As Pointers
### Variables and Objects
### Variables and Shared Objects
### Equality and Identity
### Shallow vs. Deep Copies
### Summary
### Exercises

## More Stuff
### Function Composition
### Method Chaining
### Modules
### The math Module
### The datetime Module
### Function Definition Order
### Nested Functions
### The global and nonlocal Statements
### Summary
### Exercises

## CONCLUSION
### Conclusion & Next Steps
