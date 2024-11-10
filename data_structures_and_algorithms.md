# [data structures and algorithms](https://launchschool.com/books/dsa)


## [Introduction](https://launchschool.com/books/dsa/read/introduction)

### [How DSA gives you an edge](https://launchschool.com/books/dsa/read/introduction#dsagivesedge)

#### Technical interviews: many focus on DSA

- questions will test your ability to:
  -  solve problems
  -  analyse different approaches
  -  optimize solutions for time/space complexity
-  This course teaches strategies for nailing these.

#### Efficient Problem solving:
  - DSA provides the tools/techniques to solve coding challenges systematically/optimally
  - You will learn to
    - analyse problems
    - select appropriate data-structures
    - apply efficient algorithms
#### Building a strong foundation
  - These concepts are fundamental to computer science and software engineering.
  - These are the building blocks for more advanced topics you'll encounter as a programmer

### [What we'll cover](https://launchschool.com/books/dsa/read/introduction#whatwellcover)

#### PEDAC

- SKIP
##### sorting algorithms

- fundamental sorting algorithms to arrange data.

##### algorithm techniques

- various strategies:
  -  binary search.
  -  pointer-based techniques
  -  and more...
-  How to choose the right algorithm

##### essential data structures

- linked lists
- stacks
- queues
- versatile structures for organizing and manipulating data

#### Practice for mastery

##### going deeper

- there's a 2nd book
- capstone also takes this further

##### let's get started

## THE PEDAC APPROACH TO PROBLEM SOLVING

SKIP

## [INTRODUCTION TO DATA STRUCTURES AND ALGORITHMS](https://launchschool.com/books/dsa/read/why_data_structures_matter#whatareds)

### [Why Data Structures Matter](https://launchschool.com/books/dsa/read/why_data_structures_matter#whatareds)

- Data structures are rhe backbone of efficient sata organisation/manipulation.
- They are like have a well-organised toolbox in which each tool has its specific place and purpose  enabling us to write code that's not just functional, but streamlined.
- Here we will look at why they are such a big deal and the impact of understanding them thoroughly.

#### What are Data Structures?

- Data is the information a program processes and manipulates. Could be simple like numbers, or complex like objects.
- It's the foundation for any program and will be the input/output for different operations.
- So data-structures are sort of sophisticated storage units. Think of them as specialized cabinets in a workshop, each for a particular set of objects. They are designed to make your access to and operating of these objects as efficient and effective as possible.
- Cluttered desk analogy: "data-structures keep data tidy and accessible, boosting efficiency and making coding taks less of a headache." HALLELUJAH!
- Arrays:
  -  one of the most widely used data-structures.
  -  Incredibly flexible.
  -  Allow you to quickly pick out a specific item.
  -  They make reading/inserting/deleting data easy.

#### The Benefits of Data Structures

#### Code Efficiency
- selecting the most appropriate structure allows us to write more efficient code
- Each data structure has unique characteristics that make it suited for particular operations.
-  Understanding these characteristics allows us to choose the most efficient structure resulting in faster and more optimised code.

#### Algorithm design

- data structures are closely linked to algorithm design.
- This is because different data-structures provide different ways to store and access data.
- If we understand the data-structure we can leverage their strengths to design efficient algorithms.

##### Problem solving

- Many programming problems require the use of specific data-structures.
- Knowing these data-structures means we are able to identify and apply the right tools for the job.

#### A Real-world Example

- Organizing a guest list:
  - Array:
    - if there are 1000 guest, iterating through the array to find who's RSVP'd is inefficient.
  - Set:
    -  one can use the `add` and `has` methods and it won't take much time at all.

### [Why Algorithms Matter](https://launchschool.com/books/dsa/read/why_algorithms_matter)

- Even similar data structures can has significant differences.
- Now we look at how algorithm choice can have similar consequences.

#### What are algorithms?

- A set of instructions to solve a task.
- These provide a systematic approach to accomplishing a desired outcome.
- Analogy of a restaurant kitchen and the role of recipes.

#### Choosing an algorithm

- different algos can do the same task, but with varying efficiency.
- **linear search**
- **binary search** depends on the array being sorted and searches halves going up or down depending on where the middle value is.
  - for a list of 1,000 elements a linear search might take 1,000 steps, where a binary search would take at most 10 steps.
- out choice of algorithm ensures that our programmes are performant and scalable. 

### [Introduction to Big O Notation](https://launchschool.com/books/dsa/read/introduction_to_big_o_notation)

- Above we looked at how many steps an algorithm might take. This is not the best way to discuss efficiency.

#### Time complexities

- How an algorithm's performace scales with the size of input is a key part of knowing its performance. This is **time complexity**.
- Number of steps will change based on input, so **big O Notation** looks at the scalability of an algorithm.
- It allows us to compare and analyze different algorithms more effectively by showing how the number of steps changes based on the size of input instead of some fixed notion of number-of-steps.

#### Big O

- "O" stands for order, as in order of magniture of the algorithm's growth rate.
- Basically it looks at which part of the algorithm has the most significant impact on how its run-time increases with larger inputs.
- The "big" part is concerned with the biggest factor that affects an algorithm's time complexity.
  - it ignores less significant terms and constants that don't really change as inoput size grows.
- **upper-limit** is the worst case scenario, as in the longest possible time taken.
  -  this happens when the element we're looking for is the last place we look, or not there at all. So in the cases where the algorithm has to check all the things.
-  O(N) is the time complexity of linear search, where N is the size of the input.
  -  WIth linear search the worst case number of steps to complete the algorithm increases at the same rate as the input.
-  In big O we look at the worst case because it is a limit.
  -  It can also be useful to ahve average-case and best-case scenarios when designing/evaluating algorithms. But worst-case is the most useful guarantee.

### [Exploring Time Complexities](https://launchschool.com/books/dsa/read/exploring_time_complexities)

#### O(1)

- The number of steps required to complete an operation stays the same regardless of input size.
- It does NOT mean there's only one step.
- Note that `N` does not appear in this description. That it because it is irrelevant to how many steps will be taken.
- An example is searching for a value in a hash table:

```javascript
function getName(obj) {
  return obj['name']
}

let person = {"name": "Srdjan", "age": 39, "job": "Software Engineer"}
getName(person) // 'Srdjan'
```

- Another example is accessing an array element by its index:

```javascript
function sumFirstAndLast(arr) {
  if (arr.length > 1) {
    return arr[0] + arr[arr.length - 1]
  }
  return 0
}
sumFirstAndLast([1,2,3,4,5,6]) // 7
```

- Time complexity in this operation is derived from these things:
    - Array.length check is constant - it does not require iteration over the array.
    - Accessing and summing elements:
        - accessing the first element
        - accessing the last element
        - sums these two elements

### O(logN)

(I am tired and distractable today, so do go over this again with that in mind)

- This refers to an operation where the number of steps necessary to complete a task increases in proportion to the logarithm of the input size.
- Logarithm of the input size means the number of times we need to halve the input size until we reach 1

#### logarithms

- The logarithm of a number is a mathematical operation that indicates the exponent to which a fixed value ("the base")

##### exponent

- **exponent** is number of times you should multiply a number by itself. (AKA the power of).

#### O(N)

- This is what we looked at with the linear search above. They're no synonymous though.
- copying each element from one list to another also fits this time complexity.

#### O(NlogN)

- The time an algorithm takes grows in proportion to the size of input (`N`) times `logN` in the logarithm of `N`. It's like iteratting linearly over an array and for each element doing a logarithmic algorithm. So combining the two previous time complexities..

#### O(N^2)

- Quadratic time complexity: the number of steps is proportional to the square of the input size.
- So if input doubles, time increases by a factor of 4.
- Can be written as `N²` or `N^2`
- An example of this would be finding all pairs between two arrays, where for each element in one array we look at all elements in the seconds array:

```javascript
function findPairs(array) {
  for (let i = 0; i < array.length; i++) {
    for (let j = 0; j < array.length; j++) {
      console.log(`Pair: ${array[i]}, ${array[j]}`);
    }
  }
}

findPairs([1, 2]); // Input length of 2, prints out 4 pairs
findPairs(['a', 'b', 'c', 'd', 'e']); // Input length of 5, prints out 25 pairs
```
- PEDAC often leads one to such a soluton, but they are too slow for large data-sets.

#### O(N^3)

- Cubic time complexity.
- The number of steps is proportional to the cube of the input size
    - If size of input doubles, number of steps increases by ^8 (because 2^2 = 8)
- To illustrate this we can exten the above example with an added nested loop:

```javascript
function findTriplets(array) {
  for (let i = 0; i < array.length; i++) {
    for (let j = 0; j < array.length; j++) {
      for (let k = 0; k < array.length; k++) {
        console.log(`Triplet: ${array[i]}, ${array[j]}, ${array[k]}`);
      }
    }
  }
}

findTriplets([1, 2]); // Input length of 2, prints out 8 triplets
findTriplets(['a', 'b', 'c']); // Input length of 3, prints out 27 triplets
```

- So for an array of 10 elements the function will perform 1000 iterations.
- So far we're simply incrementing the exponent by one:
    - 2 nested loops = quadratic
    - 3 nested loops = cubic
    - 4 nested loops = quartic
- As we add more nested loops the complexity grows exponentially. This means nested loops are often targets for optimisation.
- The are often found in naive solutions to problems with multi-dimentional data or certain graph algorithms.

#### O(2^N)

- Exponential time complexity.
- For each additional element in the input the execution time of the algorithm doubles. This exponential growth occurs because the algorithm generates an increasing number of subproblems (or recursive calls) with each inoput element.
- Sometimes written as `2N`
- A common example of this is non-memoized recursion, where the algorithm often recalculates the same subproblem multiple times.
- For example below we have a naive recursive implementation of the Fibonacci sequence, where each call generates two additional calls:

```javascript
function fibonacci(n) {
  if (n <= 1) {
    return n;
  }
  return fibonacci(n - 1) + fibonacci(n - 2);
}
```

#### O(N!)

- Factorial time complexity. ("N factorial").
- Even more rapid growth in execution time.
- Referes to all positive integers up to `N`. For example if `N` === 5, then `5!` is 5 x 4 x 3 x 2 x 1 (=120)
- Typically found in scenarios requiring the exploration of all possible permutations/combinations.
    - A pathfinding problem like the Travelling Salesman Problem.

### [Space Complexity](https://launchschool.com/books/dsa/read/space_complexity)

- time complexity was how an algorithm's performance scales with input size.
- space complexity is the max memory the algorithm requires to solve a problem.
- An algorithm's memory usage can significantly impact its efficiency/practicality. This is really important in situations where memory resources are limited.
- Time complexity measures computational time required by an algorithm, but Space complexity measures the memory space requirements.
- Also expressed with Big O notation. The growth of the space complexity represents an upper limmit, rather than a consistent outcome.
- We will look at how time complexity and space complexity can affect each other. FOr example increassing space usage can improve time complexity.

#### [Auxiliary Space Complexity](https://launchschool.com/books/dsa/read/space_complexity#auxiliaryspacecomplexity)

- extra space / temporary space used by an algorithm
- For instance if we need to split a string into an array of chars, because javascript strings are immutable, additional space is required. This is considered an auxiliary requirement because it is the minimum additional space needed to solve the problem in this language.

### [Fine-tuning Time Complexity](https://launchschool.com/books/dsa/read/fine_tuning_time_complexity_analysis)

- Removing constants
- simplifying complex expressions
- using appropriate variable names
- consider different collections seperately
#### [Removing constants from time complexity](https://launchschool.com/books/dsa/read/fine_tuning_time_complexity_analysis#removingconstants)

- You must focus on the dominant term that determines the growth rate as the input size increases.
- For example:

```javascript
function exampleFunction(arr) {
  for (let i = 0; i < arr.length; i++) {
    // O(N) operations
  }

  for (let j = 0; j < arr.length; j++) {
    // O(N) operations
  }
}
```

- The second loop is negligible. We focus on the dominant terms rather than precise numbers.
- What we are interested in is the relationship between the size of input and the number of operations.

#### [The arbitrary name "N"](https://launchschool.com/books/dsa/read/fine_tuning_time_complexity_analysis#arbitraryn)

- The length of the input collection. But its arbitary. You could use another name.
- We could, for instance, use `U` for a list of users.

#### [Distinct variable names for different collections](https://launchschool.com/books/dsa/read/fine_tuning_time_complexity_analysis#distinctvariables)

- Distinguishing between collections and data structures is crucial when performing time complexity analysis.
- By recognising that collections can have different sizes we can come to a more comprehensive understanding of how the algorithm's performace scales in different scenarios.

### [Time & Space Complexity Problems](https://launchschool.com/books/dsa/read/time_and_space_complexity_problems)

#### Practice problems

1.

```javascript
function test(n) {
  for (let i = 0; i < n; i++) {
    console.log("Hello!");
  }
}
```

Time Complexity is O(N) - correct
Space Complexity is O(N) - incorrect O(1), because it does not use any additional memory outside of the input size.

2. 

```javascript
function test(n) {
  for (let i = 0; i < n; i++) {
    for (let j = i; j < n; j++) {
      console.log("Hello!");
    }
  }
}
```

Time Complexity: O(N^2) (quadratic time complexity)
Space Complexity: O(1) as above

3. 
```javascript
function test(n) {
  let result = [];
  for (let i = 0; i < n; i++) {
    result.push(i);
  }
  return result;
}
```

Time complexity: O(1) incorrect: O(N) because the loop will run N times
Space complexity: O(2) incorrect O(N) because the result array grows linearly with the input size `n`.

4.

```javascript
function test(n) {
  let sum = 0;
  for (let i = 1; i <= n; i++) {
    for (let j = 1; j <= i; j++) {
      sum += 1;
    }
  }
  return sum;
}
```

Time: O(N^2) - correct
Space: O(n) - incorrect - O(1) : number of steps stays the same regardless of the input

5.
```javascript
function test(n) {
  let result = [];
  for (let i = 0; i < n; i++) {
    result.push(i);
    for (let j = 0; j < n; j++) {
      result[i] += j;
    }
  }
  return result;
}
```

Time: O(N^2) as above - correct
Space: O(2N) - incorrect O(N) because we are not adding more values to result, we are only modifiying those values.

6.

```javascript
function test(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 0; j < n; j++) {
      for (let k = 0; k < n; k++) {
        console.log("Hello!");
      }
    }
  }
}
```

Time: cubic complexity = correect
Space: O(1) stays the same = correct

7. 

```javascript
function test(n) {
  let result = [];
  for (let i = 0; i < n; i++) {
    result.push(new Array(n).fill(0));
  }
  return result;
}
```

Time: O(N) = incorrect, O(N^2)
    - this is becasue the `.fill(0)` method adds another `0(n)` which fills the empty array iteratively.
Space: O(logN) = incorrect, also O(N^2)
    - the result array grows quadratically with the input size (holding n arrays of n size).

8. 

```javascript
function test(n) {
  for (let i = n; i >= 1; i /= 2) {
    console.log("Hello!");
  }
}
```

Time: O(logN) like binary search = correct
Space: O(1) = correct

9.

```javascript
function test(n) {
  let matrix = [];
  for (let i = 0; i < n; i++) {
    matrix[i] = [];
    for (let j = 0; j < n; j++) {
      matrix[i][j] = i + j;
    }
  }
  return matrix;
}
```

Time: O(NlogN) incorrect - `O(N^2)` because it involves 2 nested loops each running `n` times. So the number of operations is proportional to `n * n = n^2`
Space: O(NlogN) - corrent insofar as it mirrors the time complexity, which make it `O(N^2)`

10.

```javascript
function test(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 1; j < n; j *= 2) {
      console.log("Hello!");
    }
  }
}
```

time: O(logN) like binary search (like question 8) - incorrect:
  - `O(NlogN)` because there are 2 nested loops. The inner loop runs `logN` times and the total number of operations is proportional to `N * logN`
space: O(1) - correct

11.

```javascript
function test(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 0; j < 100; j++) {
      console.log("Hello!");
    }
  }
}
```

Time: O(100N^2) - incorrect
  - The 100 is a constant factor and as such does not affect the overall time-complexity
Space: 0(1) - correct

12.

```javascript
function test(n, m) {
  for (let i = 0; i < n; i++) {
    console.log("Hello!");
  }
  for (let j = 0; j < m; j++) {
    console.log("World!");
  }
}
```

time: O(M+N)
space: O(1)

13.

```javascript
function test(n) {
  for (let i = 0; i < 2 * n; i++) {
    console.log("Hello!");
  }
}
```

Time: O(2N) - incorrect
  - although the loop does run 2N times we can simplify the time complexity by removing the constant factor. Therefore the time complexity is O(N)
Space: O(1)

14.

```javascript
function test(n) {
  let count = 0;
  for (let i = n; i > 1; i = Math.floor(i / 2)) {
    for (let j = 0; j < n; j++) {
      count++;
    }
  }
  return count;
}
```

time: O(logN^N) - half right. yes it is binary then linear, but the combination of those looks like this: `O(NlogN)`
space: O(1) - correct

### [Algorithm Discovery Process](https://launchschool.com/books/dsa/read/algorithm_discovery_process)

- The algorithm discovery process and how PEDAC fits into it.
- The naive solution: the solution pedac guides us to before considering O(N).

#### [Pushing the Big O curve down 1 level](https://launchschool.com/books/dsa/read/algorithm_discovery_process#pushingthecurve)

- 
#### [Hash Tables](https://launchschool.com/books/dsa/read/algorithm_discovery_process#hashtables)

```javascript
function findPair(nums) {
  const numMap = new Map();
  const targetNumber = 10;

  for (let idx = 0; idx < nums.length; idx++) {
    const complement = targetNumber - nums[idx];

    if (numMap.has(complement)) {
      return [complement, nums[idx]];
    }

    numMap.set(nums[idx], idx);
  }

  return null;
}
```

### [Practice: Find a Majority Element](https://launchschool.com/books/dsa/read/find_majority_element)

#### [Problem descrption](https://launchschool.com/books/dsa/read/find_majority_element#description)

```javascript
// Given an array of numbers, return its majority element.

// The majority element is the value in the array that appears
// as at least half of the elements in the array.

// It is guaranteed that only one majority element exists in the array.

// Test Cases:

console.log(findMajority([6, 4, 4, 6, 4]) === 4);
console.log(findMajority([4, 5, 2, 5, 5, 5, 1]) === 5);
console.log(findMajority([1, 2, 1, 2, 2, 1, 2]) === 2);
console.log(findMajority([1, 2, 3, 1, 4, 4, 1, 1]) === 1);
console.log(findMajority([5, 5, 5]) === 5);

// All test cases should log true
```

## SORTING ALGORITHMS

### Intro to Sorting Algorithms

- The fundamental importance of sorting in computer science

#### Real World Applications

- Databases
- Information retrieval
- Computational Biology
- Operating systems
- Network routing

### [Bubble Sort](https://launchschool.com/books/dsa/read/bubble_sort)

- One of the simplest. Easy to understand, but not one of the more efficient ones.
- Algorithm: 

### Selection Sort
### Insertion Sort
## POINTER-BASED MENTAL MODELS
### Pointer-Based Strategies
### Two Pointers: Start/End
### Two Pointers: Anchor/Runner
### Practice: Reverse Consonants
### Practice: Compress to Distinct
## BINARY SEARCH
### Intro to Binary Search
### Binary Search Template
### Demo: Find Zero Position
### Demo: Find The Range of Threes
### Practice: Minimum Count
## LINKED LISTS
### Intro to Linked Lists
### Arrays vs Linked Lists Performance
### When to Use Linked Lists?
### Demo: Remove Twos
### Pointers in Linked Lists
###  Dummy Nodes in Linked Lists
### Demo: Reverse Linked List
### Practice: Remove Every Second
## STACKS & QUEUES
### Intro to Stacks and Queues
### Stacks
### Implement Stack with Linked List
### Queues
### Implement Queue using Linked List
### Stacks and Queues in Interviews
### Practice: Matching Brackets
## CONCLUSION
### Conclusion & Next Steps

|  | 1st: John the Baptist | 2nd: deep-dive | 3rd: find/fill gaps |
| :--- | :---: | :---: | :---: | 
| Introduction to data-structures and algorithms | start 7.11.24 |
| Sorting algorithms | 
| Pointer-based mental models | 
| Binary search | 
| Stacks & queues |

