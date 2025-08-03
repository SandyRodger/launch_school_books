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

- it's just `+=` etc.

- but you can smush together lists:
q
```
bar = [1, 2, 3]     # bar is [1, 2, 3]
bar += [4, 5]       # + with lists appends
                    # bar is now [1, 2, 3, 4, 5]
print(bar)          # prints [1, 2, 3, 4, 5]
```
- It talks about set union, but has not introduced this term:
  - `bar |= {2, 3, 4, 5} # | performs set union`


### [Reassignment vs. Mutation](https://launchschool.com/books/python/read/variables#reassignmentvsmutation)

- nothing new

### [Summary](https://launchschool.com/books/python/read/variables#summary)
### Exercises

1. 
- index => idiomatic
- CatName => non-idiomatic
- lazy_dog => non-idiomatic WRONG -> idiomatic
- quick_Fox => non-idiomatic
- 1stCharacter => non-idiomatic WRONG illegal
- operand2 => non-idiomatic WRONG idiomatic
- BIG_NUMBER => non-idiomatic
- π => illegal WRONG non-idiomatic
2.
- same as above
3.
- index => non-idiomatic (all chars should be capitalised)
- CatName => non-idiomatic (all chars should be capitalised)
snake_case => non-idiomatic (all chars should be capitalised)
LAZY_DOG3 => idiomatic
1ST => illegal, should not begin with a digit
operand2 => non-idiomatic (all chars should be capitalised)
BIG_NUMBER => idiomatic
Π => non-idiomatic, not an Ascii char
5.
```
name = 'Victor'
print(f'Good Morning {name}')
print(f'Good Afternoon {name}')
print(f'Good Evening {name}')

```
6.
```
age = 35
print(f'You are {age} years old.')
print(f'In 10 years, you will be {age + 10} years old.')
print(f'In 20 years, you will be {age + 20} years old.')
print(f'In 30 years, you will be {age + 30} years old.')
print(f'In 40 years, you will be {age + 40} years old.')
```
8.
```
balance = 1000
interestRate = 1.05
balance *= interestRate
balance *= interestRate
balance *= interestRate
balance *= interestRate
balance *= interestRate
print(balance)
```
9. already did it
10.
```
obj = 42 # assignment
obj = 'ABcd' # reassignment
obj.upper() # neither CORRECT
obj = obj.lower() # reassign CORRECT
print(len(obj)) # neither CORRECT
obj = list(obj) # reassign CORRECT
obj.pop() # mutate CORRECT
obj[2] = 'X' # MUTATE
obj.sort() # MUTATE
set(obj) # neither
obj = tuple(obj) # REASSIGN
```

## [Input/Output](https://launchschool.com/books/python/read/input_output)
### [Terminal Output](https://launchschool.com/books/python/read/input_output#terminaloutput)

- `sep` keyword to seperate output:
```
print(1, 2, 3, 'a', 'b', sep=',')      # 1,2,3,a,b
print('a', 'b', 'c', 'd', 'e', sep='') # abcde
```

- The end keyword argument defines what print() prints after it prints the last argument. By default, it prints a newline (\n). 

```
print(1, 2, 'a', 'b', sep=',', end=' <-\n')
# 1,2,a,b <-

print('a', 'b', end='', sep=','); print('c', 'd', sep=',')
# a,bc,d
```

### [Terminal Input](https://launchschool.com/books/python/read/input_output#terminalinput)

```
print("What's your name?")
name = input()

print(f'Good Morning, {name}!')
```

- or

```
name = input("What's your name? ")

print(f'Good Morning, {name}!')
```

### Summary
### Exercises
1.
```
name = input('what is your name? ')
print(f'Hello {name}')
```
2.

3.
```
age = input('give me your age ')
print(f'in 10 years you will be {int(age) + 10} years old')
```

## [Functions and Methods](https://launchschool.com/books/python/read/functions_methods)
### [Calling Functions](https://launchschool.com/books/python/read/functions_methods#callingfunctions)

```
def hello():
    print('Hello')
    return True

hello()         # invoking function; ignore return value
print(hello())  # using return value in a `print` call

>>> print(print())
None => for some reason the return value is None ?
```
### [Built-in Functions](https://launchschool.com/books/python/read/functions_methods#builtinfunctions)

- about 70 of them
- Here are some:
  - float
  - int
  - str, list, tuple
  - set, frozenset
  - input, print
  - type
  - len
- min/max
```
print(min(-10, 5, 12, 0, -20))      # -20
print(max(-10, 5, 12, 0, -20))      # 12

print(min('over', 'the', 'moon'))   # 'moon'
print(max('over', 'the', 'moon'))   # 'the'

print(max(-10, '5', '12', '0', -20))
# TypeError: '>' not supported between instances
# of 'str' and 'int'
```

#### ord and chr

#### truthy and falsey

- falsey:
  - False, None
  - all numeric 0 values (integers, floats, complex)
  - empty strings: ''
  - empty collections: [], (), {}, set(), frozenset(), and range(0)
  - Custom data types can also define additional falsy value(s).
- truthy
  - everything else

#### any/all
```
collection1 = [False, False, False]
collection2 = (False, True, False)
collection3 = {True, True, True}

print(any(collection1))       # False
print(any(collection2))       # True
print(any(collection3))       # True
print(any([]))                # False

print(all(collection1))       # False
print(all(collection2))       # False
print(all(collection3))       # True
print(all([]))                # True
```

- a comprehension ? like the following

```
numbers = [2, 5, 8, 10, 13]
print([number % 2 == 0 for number in numbers])
# [True False True True False]
```
#### Functions for the REPL

##### The id Function

- interning

##### the `dir` function

- use a comprehension to limit the output to just the names that don't contain `__` :

```
>>> names = sorted(dir(range(1)))
>>> names = [name for name in names
...          if '__' not in name]
>>> print(names)
['count', 'index', 'start', 'step', 'stop']
```

#### the `help` function

### [Creating Functions](https://launchschool.com/books/python/read/functions_methods#creatingfunctions)

#### docstring

```
def say():
    """
    The say function prints "Hi!"
    """
    print('Hi!')

print('-' * 60)
print(say.__doc__)
print('-' * 60)
help(say)
```

### [Scope](https://launchschool.com/books/python/read/functions_methods#scope)

 - all familiar from Javascript, except this:

```
def scope_test():
    if True:
        foo = 'Hello'
    else:
        bar = 'Goodbye'

    print(foo)
    print(bar)

scope_test()
```

### [Namespaces](https://launchschool.com/books/python/read/functions_methods#namespaces)

- order of look-up for an identifier:
  -  local namespace
  -  enclosing namespace
  -  global namespace
  -  built-in namespace

### [Arguments & Parameters](https://launchschool.com/books/python/read/functions_methods#argumentsparameters)

### [Return Values](https://launchschool.com/books/python/read/functions_methods#returnvalues)

- defaults to `None`

### [Default Parameters](https://launchschool.com/books/python/read/functions_methods#defaultparameters)

- yup

### [Functions vs. Methods](https://launchschool.com/books/python/read/functions_methods#functionsvsmethods)

- you should say methods when discussing functions explicitly designed to require calling objects.

### [Mutating the Caller](https://launchschool.com/books/python/read/functions_methods#mutatingthecaller)

- yup

### [Summary](https://launchschool.com/books/python/read/functions_methods#summary)
### Exercises

1. undefined variable foo
2. bar
3. 
```
def multiply():
  arg1 = float(input('Enter the first number: '))
  arg2 = float(input('Enter the second number: '))
  return arg1  * arg2

print(multiply())
```
4.
5. nothin'
6. nothin' at all
7. print 'hello', retunr an error -> nope, just return an error, unline JS
8. too many args also throws an error:

```
def foo(bar, qux):
    print(bar)
    print(qux)

foo(42, 3.141592, 2.718)
```
9. yep
10. yep
11. yep
12. yep
13. yep
18. yep
```
def remainders_3(numbers):
    return [number % 3 for number in numbers]

numbers_1 = [0, 1, 2, 3, 4, 5, 6]
numbers_2 = [1, 2, 4, 5]
numbers_3 = [0, 3, 6]
numbers_4 = []

print(any(remainders_3(numbers_1)))
print(any(remainders_3(numbers_2)))
print(any(remainders_3(numbers_3)))
print(any(remainders_3(numbers_4)))
```

19. yep
```
def remainders_5(numbers):
    return [number % 5 for number in numbers]

numbers_1 = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
numbers_2 = [1, 2, 3, 4, 6, 7, 8, 9]
numbers_3 = [0, 5, 10]
numbers_4 = []

print(all(remainders_5(numbers_1)))
print(all(remainders_5(numbers_2)))
print(all(remainders_5(numbers_3)))
print(all(remainders_5(numbers_4)))
```

## [Flow Control](https://launchschool.com/books/python/read/flow_control)
### [Conditionals](https://launchschool.com/books/python/read/flow_control#conditionals)

- new ones:
  - `and`
  - `or`
  - `not`
  - `elif` instead of `elsif`.
- `pass`: add a comment for clarity.

```
value = int(input('Enter a number: '))

if value > 10:
  print('value is greater than 10')
elif value < 10:
  print('value is less than 10')
else:
  pass # we don't care about 10 itself
```

### [Comparisons](https://launchschool.com/books/python/read/flow_control#comparisons)

- `==` operands have equal values
- Sometimes `==` will equate operands of different types, sometimes not:
```
print(5 == float(5))                # True

big_num = 12345678901234567
print(float(big_num) == big_num)    # False
```

### [Logical Operators](https://launchschool.com/books/python/read/flow_control#logicaloperators)

#### not

- so like `!` in js ?
  - `print(not True) # False

#### and / or

- `&&` / `||`

### [Short Circuits](https://launchschool.com/books/python/read/flow_control#shortcircuits)

- short circuit evaluation

### [Truthiness](https://launchschool.com/books/python/read/flow_control#truthiness)

- Falsey:
  - `False`
  - `None`
  - `0`
  - `''`
  - all empty collections
  - custom data types can be falsey
  - The final value returned by an expression using `and` or `or` is the final value read by the phrase:

```
print(3 and 'foo') # foo
print('foo' or 3) # foo
print([] or 3) # 3
```

- `is_ok = bool(foo or bar)`

### [Logical Operator Precedence](https://launchschool.com/books/python/read/flow_control#logicaloperatorprecedence)

- this is the list:
  - `==`, `!=`, `<=`, `<`, `>`, `>=` -> comparison
  - `not`
  - `and`
  - `or`

### [match/case Statement](https://launchschool.com/books/python/read/flow_control#matchstatement)

- it's switch syntax

```
value = 'box'

match value:
  case 5: 
    print('value is 5')
  case 6:
    print ('value is 6')
  case _:
    print('value is neither 5 nor 6')
```

### [Ternary Expressions](https://launchschool.com/books/python/read/flow_control#ternaryexpressions)

- `value1 if condition else value2`
- `print("Triangle" if shape.sides() == 3 else "Square")`

### Summary
### Exercises

```
# 1.

False or (True and False) # False
True or (1 + 2) # True
(1 + 2) or True # 3
True and (1 + 2) # True WRONG -> 3
False and (1 + 2) # False
(1 + 2) and True # True
(32 * 4) >= 129 # False
False != (not True) # False
True == 4 # False
False == (847 == '847') # True

# 2.

def even_or_odd(n):
  if (n % 2 == 1):
    print('odd')
  else:
    print('even')

# 3.

# product2
# product3 NOPE -> product not found
# print(142 == '142') # False

# 4.

def foo():
  return True

def qux():
  return 1

def baz():
  if (foo()):
    return 'bar'
  else:
    return qux()
  
# 5.

def is_list_empty(my_list):
    if my_list:
        print('Not Empty')
    else:
        print('Empty')

# is_list_empty([]) # Empty

# 6. 

def capitalise_long_words(word):
   if len(word) > 10:
      return word.upper()
   else:
      return word
   
# print(capitalise_long_words('bar'))
# print(capitalise_long_words('barnabussyl'))

# 7.

def number_range(n):
  if n < 0:
    print(f'{n} is less than 0')
  elif n <= 50:
    print(f'{n} is between 0 and 50')
  elif n < 100:
    print(f'{n} is between 51 and 100')
  else:
     print(f'{n} is greater than 100')

number_range(0)     # 0 is between 0 and 50
number_range(25)    # 25 is between 0 and 50
number_range(50)    # 50 is between 0 and 50
number_range(75)    # 75 is between 51 and 100
number_range(100)   # 100 is between 51 and 100
number_range(101)   # 101 is greater than 100
number_range(-1)    # -1 is less than 0
```

## COLLECTIONS AND ITERATION


## [Intro to Collections](https://launchschool.com/books/python/read/intro_collections)
### [Collection Types](https://launchschool.com/books/python/read/intro_collections#collectiontypes)

- python has a lot
- 3 main categories:
  - sequences
    - ranges
    - tuples (tuples are just frozen lists)
    - lists
    - strings as text sequences, although simultaneously strings are not collections since the characters inside are not objects. This seems to be a contradiction, but I do not have the time to pin down the precise nature of the truth now.
  - mappings
    - dictionaries
  - sets
    - sets
    - frozen sets

### [What are Sequences?](https://launchschool.com/books/python/read/intro_collections#whatsequences)

- collections of elements with an integer index value -> so analogous to JS arrays)
- "heterogeneous" -> composed of parts of different kinds. (Unlike ranges which are homogeneous -> they always contain integers)
- Strings are text sequences

### [What are Sets?](https://launchschool.com/books/python/read/intro_collections#whataresets)

- unordered collection

```
letters = {'a', 'b', 'c'}
letters.add('d')
print(letters)
# {'a', 'b', 'c', 'd'} (order may differ)

frozen_letters = frozenset(letters)
frozen_letters.add('e')
# AttributeError: 'frozenset' object has no
# attribute 'add'
```

- python will ignore any attempt to add duplicate members to a set:

```
letters = {'a', 'b', 'c', 'b', 'a'}
print(letters)
# {'a', 'c', 'b'} (order may differ)

letters.add('c')
print(letters)
# {'a', 'c', 'b'} (order may differ)
```

- Since Python 3.7 sets of integers appear to be ordered, but this is an illusion, easy to trick and not to be relied upon:

```
numbers = { 1, 2, 37, 4, 5 }
print(numbers)      # {1, 2, 4, 37, 5}
```

### [What are Mappings?](https://launchschool.com/books/python/read/intro_collections#whataremappings) 

- types tha maintain an unordered collection of k/v pairs. (so JS objects?)
- There's a few, but this book only looks at `dict` types.
- Keys must be unique.
- Keys must be hashable values (usually immutable)
- since Python 3.7 order is preserved, but you should think of them as unordered.

### [Sequence Constructors](https://launchschool.com/books/python/read/intro_collections#sequenceconstructors)

#### String constructor:

- `str()` => `''`
- `str(something)` 
```
str()            # returns '' (empty string)
str('abc')       # returns 'abc'
str(42)          # returns '42'
str(3.141592)    # returns '3.141592'
str(False)       # returns 'False'
str(None)        # returns 'None'
str(range(3, 7)) # returns 'range(3, 7)'
str([1, 2, 3])   # returns '[1, 2, 3]'
str(int)         # returns "<class 'int'>"
str(list)        # returns "<class 'list'>"

class Person: pass
str(Person())
# returns "<__main__.Person object at 0x1006d21e0>"
```

#### Range Constructor
1. `range(start, stop, step)`
```
r = range(5, 12, 2)
print(list(r))            # [5, 7, 9, 11]

r = range(12, 8, -1)
print(list(r))            # [12, 11, 10, 9]

r = range(12, 5, -2)
print(list(r))            # [12, 10, 8, 6]
```
- empty ranges are often bugs:

```
r = range(5, 5, 1)
print(list(r))           # []

r = range(5, 7, -1)
print(list(r))            # []
```
2. `range(start, stop)`
- defaults to 1 step

3. `range(stop`
- start defaults to `0`
- so `range(5)` is the same as `range(0, 5, 1)`

- ranges are "lazy sequences"

#### The List, Tuple, Set, and Frozen Set Constructors

- without argument they create an empty collection:
  - `list()`
  - `tuple()`
  - `set()`
  - `frozenset()`
- args must be iterables

```
my_str = 'Python'

my_list = list(my_str)
print(my_list)  # ['P', 'y', 't', 'h', 'o', 'n']

my_tuple = tuple(my_list)
print(my_tuple) # ('P', 'y', 't', 'h', 'o', 'n')

my_set = set(my_tuple)
print(my_set)   # {'t', 'o', 'n', 'h', 'P', 'y'}
```
- one can use these constructors to duplicate a collection:

```
my_list = [5, 12, 2]
another_list = list(my_list)

print(my_list)                          # [5, 12, 2]
print(another_list)                     # [5, 12, 2]

print(my_list == another_list)          # True
print(my_list is another_list)          # False
# so `is` is like === in JS, right?
```

- This demonstrates that copying nested lists results in shallow copies being copied:

```
my_list = [[1, 2, 3], [4, 5, 6]]
another_list = list(my_list)

print(my_list)                          # [[1, 2, 3], [4, 5, 6]]
print(another_list)                     # [[1, 2, 3], [4, 5, 6]]

print(my_list == another_list)          # True
print(my_list is another_list)          # False
print(my_list[0] is another_list[0])    # True
print(my_list[1] is another_list[1])    # True
```

### Summary
### Exercises

```
# 2.
stuff = ('hello', 'world', 'bye', 'now')
# LS1
stuff = ('hello', 'world', 'goodbye', 'now')
# LS2
stuff = stuff[0:2] + ('goodbye', stuff[3])
# LS3
stuff = stuff[0:2] + ('goodbye', stuff[3])

# 3


# Similarities
  # both tuples and lists have number indexes
  # both heterogenous

# 4

# 5

# 6

pi = 3.141592
str_pi = str(pi)

# 7

range(7) # 0, 1, 2, 3, 4, 5, 6. correct
range(1, 6) # 1, 2, 3, 4, 5 correct
range(3, 15, 4) # 3, 7, 11 
range(3, 8, -1) # []
range(8, 3, -1) # 8, 7, 6, 5, 4

# 8

# print(range(3, 17, 4)) # => range(3, 17, 4)
result = tuple(range(3, 17, 4))
# print(result) # => (3, 7, 11, 15)
# since ranges are lazy sequences you have to convert the range to a non-lazy sequence

# 9.
# 1 -> yes they are equal
# 2 -> no they are not the same object
# 3 -> yes the nested lists are equal
# 4 -> Yes they are the same object because they copy did not create a new nested list, it only created a reference to the first nested list. This is the nature of shallow copies, they only copy down one level (as it were)

# 10
# no it will jumble them up. Sets by definition are unordered collections
names = { 'Chris', 'Clare', 'Karis', 'Karl',
          'Max', 'Nick', 'Victor' }
# print(names)

# 11
# use a dict:

countries = {
  'Alice': 'USA',
  'Francois': 'Canada',
  'Inti':	'Peru',
  'Monika':	'Germany',
  'Sanyu':	'Uganda',
  'Yoshitaka':	'Japan',
}
print(countries['Alice'])
```


## [Using Collections](https://launchschool.com/books/python/read/using_collections)
### [Indexing](https://launchschool.com/books/python/read/using_collections#indexing)

- nothing new here.

### [Slicing](https://launchschool.com/books/python/read/using_collections#slicing)

```
string = 'abcdefghi'
print(string[3:7])       # defg
print(string[-6:-2])     # defg
print(string[2:8:2])     # ceg
print(repr(string[3:3])) # ''
print(string[:])         # abcdefghi
print(string[::-1])      # ihgfedcba

seq = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(seq[3:7])          # [4, 5, 6, 7]
print(seq[-6:-2])        # [5, 6, 7, 8]
print(seq[2:8:2])        # [3, 5, 7]
print(seq[3:3])          # []
print(seq[:])            # [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(seq[::-1])         # [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]

seq = [[1, 2], [3, 4]]
seq_dup = seq[:]
print(seq[0] is seq_dup[0])   # True
```

### [Key-Based Access](https://launchschool.com/books/python/read/using_collections#keybasedaccess)

- dict keys must be immutable

### [Common Collection Operations](https://launchschool.com/books/python/read/using_collections#commoncollectionoperations)

#### Non-Mutating Operations for Collections
##### collection membership
- ie `in` and `not in`

```
seq = [4, 'abcdef', (True, False, None)]
print(4 in seq)                         # True
print(4 not in seq)                     # False
print('abcdef' in seq)                  # True
print('abcdef' not in seq)              # False
print('cde' in seq[1])                  # True
print('cde' not in seq[1])              # False
print('acde' in seq[1])                 # False
print('acde' not in seq[1])             # True
print((True, False, None) in seq)       # True
print((True, False, None) not in seq)   # False
print(3.14 in seq)                      # False
print(3.15 not in seq)                  # True
```

#### minimum and maximum members

- can't use min max with heterogenous collections:

```
  my_set = {1, 4, '-9', 16, '25', -36, -63, -1}
min(my_set)
# TypeError: '<' not supported between instances of 'str' and 'int'

max(my_set)
# TypeError: '>' not supported between instances of 'str' and 'int'
```

#### Sum

```
nums = (1, 2, 3, 4, 5)
print(sum(nums))
```

#### Locating Indices and Counting

- which just means using `.index('value')` to return an index.
  - (if you do it with a string it tells you where that string begins)
- and `.count(number)` to count how many occurences in a list.
```
names = ['Karl', 'Grace', 'Clare', 'Victor',
         'Antonina', 'Allison', 'Trevor']
print(names.index('Clare'))   # 2
print(names.index('Trevor'))  # 6
print(names.index('Chris'))
# ValueError: 'Chris' is not in list
```

```
numbers = [1, 3, 6, 5, 4, 10, 1, 5, 4, 4, 5, 4]
print(numbers.count(1))       # 2
print(numbers.count(3))       # 1
print(numbers.count(4))       # 4
print(numbers.count(7))       # 0
```

#### Merging Collections

- zip
```
iterable1 = [1, 2, 3]
iterable2 = ('Kim', 'Leslie', 'Bertie')
iterable3 = [None, True, False]

zipped_iterables = zip(iterable1, iterable2, iterable3)
print(list(zipped_iterables))
# Pretty printed for clarity
# [
#   (1, 'Kim', None),
#   (2, 'Leslie', True),
#   (3, 'Bertie', False)
# ]
```

`zipped_iterables = zip(iterable1, iterable2, strict=True)`

- iterators can only be consumed once!

#### Operations on Dictionaries

```
dict.keys
dict.values
dict.items
```

#### Operations for Mutable Sequences

- `append` `insert` and `extend`
- `seq.append`

#### Removing Elements from Mutable Sequences

- remove
- pop
- clear

#### Sorting Collections

- `sorted` doesn't mutate the list,`list.sort` does.

```
names = ('Grace', 'Clare', 'Allison', 'Trevor')
print(sorted(names))
# ['Allison', 'Clare', 'Grace', 'Trevor']

print(names)
# ('Grace', 'Clare', 'Allison', 'Trevor')

names = list(names)
print(names)
# ['Grace', 'Clare', 'Allison', 'Trevor']

print(names.sort())   # None
print(names)
# ['Allison', 'Clare', 'Grace', 'Trevor']
```

- sort string numbers like this:

```
numbers = ['1', '5', '100', '15', '534', '53']
numbers.sort()
print(numbers)   # ['1', '100', '15', '5', '53', '534']

numbers.sort(key=int)
print(numbers)   # ['1', '5', '15', '53', '100', '534']
```

#### Reversing Sequences and Dictionaries


### [String Operations](https://launchschool.com/books/python/read/using_collections#stringoperations)

#### Letter Case

- `str.capitalize`
- `str.title`
- `capwords`:
```
import string
print(string.capwords("i can't believe it's already mid-july."))
# I Can't Believe It's Already Mid-july.
```
- `swapcase`

#### Character Classification

- `str.isalpha`
- str.isdigit()
- str.isalnum()
- str.islower()
- str.isupper()
- str.isspace() 
- `text.isalpha() and text.isascii()` to exclude non ASCII letters

#### Stripping Characters

- str.strip
- with `repr`
```
text = ' \t  abc def    \n\r'
print(repr(text))             # ' \t  abc def    \n\r'
print(repr(text.strip()))     # 'abc def'
```

#### Splitting and Joining Strings

- `split`:

```
text = '  Four     score and   seven years ago.   '
print(text.split())
# ['Four', 'score', 'and', 'seven', 'years', 'ago.']

print('no-spaces'.split()) # ['no-spaces']
```

#### Finding Substrings

- str.find and str.rfind

### [Nested Collections](https://launchschool.com/books/python/read/using_collections#nestedcollections)

- you can't nest mutable collections inside some collections. For instance, you can't nest a mutable collection such as a list, dictionary, or another set inside a set:

```
>>> my_set = {1, 2, 3, [4, 5]}
TypeError: unhashable type: 'list'

>>> my_set = {1, 2, 3, {4, 5}}
TypeError: unhashable type: 'set'
```

### [Comparing Collections](https://launchschool.com/books/python/read/using_collections#comparingcollections)

```
print([2, 3] == [2, 3])    # True
print([2, 3] == [3, 2])    # False (diff sequence)
print([2, 3] == [2])       # False (diff lengths)
print([2, 3] == (2, 3))    # False (diff types)
print({2, 3} == {3, 2})    # True (same members)

dict1 = {'a': 1, 'b': 2}
dict2 = {'b': 2, 'a': 1}
dict3 = {'a': 1, 'b': 2, 'c': 3}

print(dict1 == dict2)      # True (same pairs)
print(dict1 == dict3)      # False
```

### Summary
### Exercises
- done

## [Loops and Iterating](https://launchschool.com/books/python/read/loops_iterating)
- `for` and `while`
### [while Loops](https://launchschool.com/books/python/read/loops_iterating#whileloops)

```
names = ['Chris', 'Max', 'Karis', 'Victor']
upper_names = []
index = 0

while index < len(names):
    upper_name = names[index].upper()
    upper_names.append(upper_name)
    index += 1

print(upper_names)
# ['CHRIS', 'MAX', 'KARIS', 'VICTOR']
```

### [for Loops](https://launchschool.com/books/python/read/loops_iterating#forloops)

```
names = ['Chris', 'Max', 'Karis', 'Victor']
upper_names = []

for name in names:
    upper_name = name.upper()
    upper_names.append(upper_name)

print(upper_names)
# ['CHRIS', 'MAX', 'KARIS', 'VICTOR']
```

```
# Looping over a set
my_set = {1000, 2000, 3000, 4000, 5000}
for member in my_set:
    print(member)
```

#### Nested Loops

### [Controlling Loops](https://launchschool.com/books/python/read/loops_iterating#controllingloops)

-`continue` and `break`

#### Continuing a Loop With Next Iteration

```
names = ['Chris', 'Max', 'Karis', 'Victor']
upper_names = []

for name in names:
    if name == 'Max':
        continue

    upper_name = name.upper()
    upper_names.append(upper_name)

print(upper_names);
# ['CHRIS', 'KARIS', 'VICTOR']
```

```
for value in collection:
    if not some_condition():
        continue

    # some code here

    if not another_condition():
        continue

    # some more code here
```

#### Breaking Out of a Loop

````
numbers = [3, 1, 5, 9, 2, 6, 4, 7]
found_item = -1
index = 0

while index < len(numbers):
    if numbers[index] == 5:
        found_item = index
        break

    index += 1

print(found_item)
````

#### Emulating Do/While Loops
### [Simultaneous Iteration](https://launchschool.com/books/python/read/loops_iterating#simultaneousiteration)

- use `zip`

### [Comprehensions](https://launchschool.com/books/python/read/loops_iterating#comprehensions)

- 3 types
  - list
  - dict
  - set

#### List Comprehensions

- the most common.
- `[ expression for element in iterable if condition ]` is the format

```
squares = [ number * number for number in range(5) ]
print(squares)      # [0, 1, 4, 9, 16]
```
#### Dictionary Comprehensions

```
squares = { f'{number}-squared': number * number
            for number in range(1, 6) }
print(squares)
# pretty-printed for clarity.
{
    '1-squared': 1,
    '2-squared': 4,
    '3-squared': 9,
    '4-squared': 16,
    '5-squared': 25
}
```

#### Set Comprehensions

```
squares = { number * number for number in range(1, 6) }
print(squares)      # {1, 4, 9, 16, 25}
```

#### Why No Tuple, Range, or String Comprehensions?

- it would be something called a "generator expression" for some reason.

### [Summary](https://launchschool.com/books/python/read/loops_iterating#summary)
### Exercises

```
# 1. because it doesn't increment

# 2.
# age = int(input('How old are you? '))
# print(f'You are {age} years old.')
# print()

# for future in range(10, 50, 10):
#   print(f'In {future} years, you will be {age + future} years old.')

# 3.

# my_list = [6, 3, 0, 11, 20, 4, 17]
# index = 0
# while index < len(my_list):
#   print(my_list[index])
#   index += 1

# 4.

# my_list = [6, 3, 0, 11, 20, 4, 17]
# index = 0
# while index < len(my_list):
#   if (my_list[index] % 2 == 0):
#     print(my_list[index])
#   index += 1

# for n in my_list:
#   if (n % 2 == 1):
#     print(n)

# 5.

my_list = [
    [1, 3, 6, 11],
    [4, 2, 4],
    [9, 17, 16, 0],
]

# for list in my_list:
#   for n in list:
#     if (n % 2 == 0):
      # print(n)

#6

new_list = []
my_list = [
    1, 3, 6, 11,
    4, 2, 4, 9,
    17, 16, 0,
]
for n in my_list:
  if (n % 2 == 1):
    new_list.append('odd')
  else:
    new_list.append('even')

# print(new_list)

# 7
def find_integers(tuple):
  return [ elem
           for elem in tuple
           if type(elem) is int ]

my_tuple = (1, 'a', '1', 3, [7], 3.1415,
            -4, None, {1, 2, 3}, False)
integers = find_integers(my_tuple)
# print(integers)  

# 8

# Write a comprehension that creates a dict object whose keys are strings and whose values are the length of the corresponding key. Only keys with odd lengths should be in the dict. Use the set given by my_set as the source of strings.

my_set = {
    'Fluffy',
    'Butterscotch',
    'Pudding',
    'Cheddar',
    'Cocoa',
}

name_lengths = { name: len(name) for name in my_set 
                            if (len(name)) % 2 == 1}
# print(name_lengths)

# 9
def factorial(n):
  if (n == 1):
    return n
  else:
    return n * factorial(n-1)

# print(factorial(1))   # 1
# print(factorial(2))   # 2
# print(factorial(3))   # 6
# print(factorial(4))   # 24
# print(factorial(5))   # 120
# print(factorial(6))   # 720
# print(factorial(7))   # 5040
# print(factorial(8))   # 40320
# print(factorial(25))  # 15511210043330985984000000

# 10

import random

highest = 10
while True:
  number = random.randrange(highest + 1)
  # print(number)
  if number == highest:
    break

# 11.

index = 0
while (index < len(my_list)):
  if (my_list[index] % 2 == 0):
    print(my_list[index])
  index += 1
```


## ADDITIONAL TOPICS
## [Variables As Pointers](https://launchschool.com/books/python/read/variables_pointers)

- nothing new here.

### [Variables As Pointers](https://launchschool.com/books/python/read/variables_pointers#variablesaspointers)

- 

### [Variables and Objects](https://launchschool.com/books/python/read/variables_pointers#variablesobjects)

### [Variables and Shared Objects](https://launchschool.com/books/python/read/variables_pointers#variablessharedobjects)

- I'm tired and not a lot of this is going in, but I'm assuming that most of it is the same as Javascript

### [Equality and Identity](https://launchschool.com/books/python/read/variables_pointers#equality)



### [Shallow vs. Deep Copies](https://launchschool.com/books/python/read/variables_pointers#shallowdeepcopies)
#### Shallow Copies
#### Deep Copies
#### Should I Make Deep or Shallow Copies?
### Summary
### Exercises

```
# 1

# the == is asking whether the 2 comparees have equal value.
# the is statement is asking whether the two variables are pointing to he same object in memory.

# 2

set1 = {42, 'Monty Python', ('a', 'b', 'c')}
set2 = set1
set1.add(range(5, 10))
print(set2)
# this will print the two objects added together

# 3 will print an error because dict2 is a shallow copy, so Monty Python doesn't exist on dict1 -ok I misread the question, but I got the concept right.

# 4 the original dict 1 object values -> no

# You may modify this line
# import copy

dict1 = {
    'a': [[7, 1], ['aa', 'aaa']],
    'b': ([3, 2], ['bb', 'bbb']),
}

# dict2 = copy.deepcopy(dict1) # You may modify the `???` part
            # of this line

# All of these should print False
# print(dict1         is dict2)
# print(dict1['a']    is dict2['a'])
# print(dict1['a'][0] is dict2['a'][0])
# print(dict1['a'][1] is dict2['a'][1])
# print(dict1['b']    is dict2['b'])
# print(dict1['b'][0] is dict2['b'][0])
# print(dict1['b'][1] is dict2['b'][1])

# 6 

dict1 = {
    'a': [{7, 1}, ['aa', 'aaa']],
    'b': ({3, 2}, ['bb', 'bbb']),
}

dict2 = dict(dict1) # You may modify the `???` part
            # of this line

print(dict1         is dict2) # false
print(dict1['a']    is dict2['a']) # true
print(dict1['a'][0] is dict2['a'][0]) # true
print(dict1['a'][1] is dict2['a'][1]) # true
print(dict1['b']    is dict2['b']) # true
print(dict1['b'][0] is dict2['b'][0]) # true
print(dict1['b'][1] is dict2['b'][1]) # true
```

## [More Stuff](https://launchschool.com/books/python/read/more_stuff)
### [Function Composition](https://launchschool.com/books/python/read/more_stuff#functioncomposition)

- composing function calls, AKA composition.

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
