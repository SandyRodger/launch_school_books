# Object Oriented javascript

## [Introduction](https://launchschool.com/books/oo_javascript/read/introduction)
### [Why JavaScript?](https://launchschool.com/books/oo_javascript/read/introduction#whyjavascript)
- It's ubiquitous (front and back end)
- Javaascript implements OOP with prototypes rather than classes like most other languages
### What is Object-Oriented Programming?
### Who is this Book For?
## [Types and Objects](https://launchschool.com/books/oo_javascript/read/types_and_objects)
- sounds a lot like RB120
### [Objects](https://launchschool.com/books/oo_javascript/read/types_and_objects#objects)
  - type v class:
    - type usually refers to a primitive object
    - Class refers to an object defined with teh `class` keyword
  - objects are sometimes called instances or instance objects and are often created by a constructor function

```javascript
function Cat(name) {
  this.name = name;
}

let butterscotch = new Cat("Butterscotch");
let pudding = new Cat("Pudding");
```
- here calling the `cat` function with the `new` keyword makes it a constructor function.

### [Classes and Types](https://launchschool.com/books/oo_javascript/read/types_and_objects#classestypes)
-  Confusion
### [Creating Objects](https://launchschool.com/books/oo_javascript/read/types_and_objects#creatingobjects)
- You can create functions inside Object classes so instances are created with the behaviour to manipulate its data.
- When object properties have functons we call them methods
### [Concise Method Syntax](https://launchschool.com/books/oo_javascript/read/types_and_objects#concisemethodsyntax)

- covered before
### [The `this` Keyword](https://launchschool.com/books/oo_javascript/read/types_and_objects#this)
```javascript
let student = {
  name: 'Joanna',
  age: 27,

  study() {
    console.log(`${this.name} is studying`);
  },

  pass() {
    console.log(`${this.name} has passed this course`)
  },
};

student.study();  // Joanna is studying
student.pass();   // Joanna has passed this course
```
- `this` is apparently a source of much confusion. I'm not sure why as it appears to do the same job as `.self` in Ruby
### [State and Behavior](https://launchschool.com/books/oo_javascript/read/types_and_objects#statebehavior)
- This is all familiar from RB 120

### [Summary](https://launchschool.com/books/oo_javascript/read/types_and_objects#summary)

- yup

### [Exercises](https://launchschool.com/books/oo_javascript/read/types_and_objects)

1. 
```javascript
let Cessna152Aircraft = {
  fuelCapacity: 24.5,
  cruisingSpeedInKnots: 111,
  takeOff() {
    console.log('I am taking off');
  },
  land() {
    console.log('I am landing');
  }
}
```
  - fuelCapacity and cruisingSpeedInKnots are states, the 2 functions are behaviours.
2.
```javascript
function Book(title, author, year) {         // this is the constructor function
  this.title = title,
  this.author = author,
  this.yearPublished = year
}

let neuromancer = new book('Neuromancer', 'William Gibson', '1984')     // these are the object instance, their type is 'object' - apparently this is incorrect. Their object type is Book even though calling typeof with them will return 'object'
let doomsdayBook = new book('Doomsday Book', 'Connie Willis', '1992')
```

3. 

```javascript
**// this is the constructor function
function Album(title, artist, released) { 
  this.title = title,
  this.artist = artist,
  this.released = released
}

// these are the instance objects
let thriller = new Album('Thriller', 'Michael Jackson', 1982); // type = Album, 
let darkSide = new Album('The Dark Side of the Moon', 'Pink Floyd', 1973);
```
4. 
```javascript

function SmartPhone(brand, model, releaseYear) {
  
  this.brand = brand,
  this.model = model,
  this.releaseYear = releaseYear

  this.checkBattery = function() {
    return `${this.brand}, ${this.model} has 75% battery remaining`
  }
  this.displayInfo = function() {
    return `${this.brand}, ${this.model} was released in ${releaseYear}`;
  }
}

let phone1 = new SmartPhone('Apple',	'iPhone 12',	2020)
let phone2 = new SmartPhone('Samsung',	'Galaxy S21',	2021)

console.log(phone1.checkBattery());
console.log(phone2.displayInfo());
```
