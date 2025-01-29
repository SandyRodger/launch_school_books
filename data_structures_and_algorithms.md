# [data structures and algorithms](https://launchschool.com/books/dsa)

#### Prerequisites

- not relevant

## [Introduction](https://launchschool.com/books/dsa/read/introduction)

- master this to create efficient, scalable and maintainable code. (lucrative skills).

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
- We sort each pair of elements. At the end of the first iteration we know the largest element is at the end. Then we do the same with all the elements - 1 and so on.

```javascript
function bubbleSort(arr) {
  const len = arr.length;

  for (let i = 0; i < len - 1; i++) {
    // Flag to track if any swaps were made
    let swapped = false;

    // Last i elements are already in place
    for (let j = 0; j < len - 1 - i; j++) {
      // Check if the element in the current iteration
      // is greater than the one in the next iteration
      if (arr[j] > arr[j + 1]) {
        // Swapping elements
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
        swapped = true;
      }
    }

    if (!swapped) {
      // If no swaps were made in this iteration, the array is already sorted
      break;
    }
  }

  return arr;
}

const array = [5, 3, 8, 7, 2];
console.log(bubbleSort(array)); // Output: [2, 3, 5, 7, 8]
```

### [Selection Sort](https://launchschool.com/books/dsa/read/selection_sort)

- I have a crate of lego. I put my hand at the left most side creating a barrier. Then I look in the crate for the smallest piece and place that on the left side of my hand. I do this over and over placing the lego pieces in size order on the right side of my hand-barrier. As I do this the amount of pieces on the right side of my hand diminishes and my hand edges towards the left inner wall of the crate. At the end of this process the lego pieces are lined up in size order.

```javascript
function selectionSort(arr) {
  const len = arr.length;

  for (let i = 0; i < len - 1; i++) {
    // Initialize `minIndex` as the first element in
    // the unsorted portion of the array
    let minIndex = i;

    // Iterate over the rest of the unsorted part of the array
    for (let j = i + 1; j < len; j++) {
      // Check if the element in the current iteration is
      // less than the element at the current `minIndex`
      if (arr[j] < arr[minIndex]) {
        minIndex = j;
      }
    }

    // If the minimum element is already at
    // index `i`, we don't need to swap
    if (minIndex !== i) {
      // Swap the first element of the unsorted portion
      // with the element at `minIndex`
      [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
    }
  }

  return arr;
}

const array = [3, 8, 2, 1];
console.log(selectionSort(array)); // Output: [1, 2, 3, 8]
```

- Selection sort and bubble sort are similar in terms of efficiency, but Selection sort is slightly better because it reduces the number of swaps necessary. Note that swapping can be more performance-expensive than comparing.

### [Insertion Sort](https://launchschool.com/books/dsa/read/insertion_sort)

- My narrative
  - We have a plate full of differently sized chips.
  - I take my knife and put it to the right of the left-most chip.
  - I compare the chip to the right of my knife with all the chips on the left.
  - At the beginning this is just a single chip.
  - When I find the chip that is smaller than "current chip" I insert chip in its right place.

- Conceptual v implementation

- In theory this algorithm had `O(N^2)` complexity and is the same as selection sort and bubble sort, but in reality it often outperforms these in certain scenarios. Sometimes it can even outperform more complex algorithms like Merge sort or quick sort.
- So how to choose? It depends on how costly the comparisons are. Insertion sort makes fewer comparisons and therefore in situations where comparisons are costly it is to be preferred. 


## POINTER-BASED MENTAL MODELS

### [Pointer-Based Strategies](https://launchschool.com/books/dsa/read/introduction_to_pointer_based_optimization)

- a powerful technique for sorting lists that can transform big O complexity from quadratic solutions to linear solutions, while preserving O(1) space complexity.
- Start/end pointers
  - uses 2 pointers (start and end)
  - manipulates the elements within that segment of the list
  - good for:
    -  finding longest increasing subarray
    -  determining is an array is a palindrome
-  Anchor/runner pointers
  -  (AKA slow/fast pointers)
  -  2 pointers with different speeds
  -  Good for:
    - finding the mid-point in an array
    - determining if an array has anny duplicates

### [Two Pointers: Start/End](https://launchschool.com/books/dsa/read/two_pointers_start_end)

- my solution was the same as the LS one (-: 

```javascript

function findPair(nums, target) {
  let s = 0;
  let e = nums.length - 1;
  const currentSum = (n1, n2) => n1 + n2;

  while (s !== e) {
    let sum = currentSum(nums[s], nums[e]);
    if (sum === target) {
      return [nums[s], nums[e]];
    } else if (sum < target) {
      s += 1;
    } else if (sum > target) {
      e -= 1;
    }
  }
  return null;
}

const nums1 = [1, 3, 6, 7, 8, 12];
const target1 = 14;
console.log(findPair(nums1, target1)); // Output: [6, 8]

const nums2 = [2, 6, 8, 10];
const target2 = 17;
console.log(findPair(nums2, target2)); // null
```

### [Two Pointers: Anchor/Runner](https://launchschool.com/books/dsa/read/two_pointers_anchor_runner)

- the slinky dog from toy story with his fore-legs moving faster than his hind legs

#### Reader-writer variant

  - Instead of swapping the elements, we just take the reader elements and write them at the writer and when we've found all the non-1 elements we insert 1s at the writer point.
  - In the majority of cases the distinction between the two is merely a question of style. (it's different with linked lists)

### [Practice: Reverse Consonants](https://launchschool.com/books/dsa/read/reverse_consonants)

```javascript

// brute force
function reverseConsonants(str) {

  let consonants = str.match(/[^aeiou]/ig);
  let chars = str.split('');
  const isConsonant = (char) => !"aeiou".includes(char.toLowerCase());

  for (i = 0; i < str.length; i++) {
    if (isConsonant(str[i])) {
      chars[i] = consonants.pop();
    }
  }
  return chars.join('');
}

// optimised:

function reverseConsonants(str) {

  if (str.length < 2) {return str};
  let start = 0;
  let end = str.length - 1;
  let chars = str.split('');

  const isConsonant = (char) => !"aeiou".includes(char.toLowerCase());
  const bothConsonants = (start,end) => isConsonant(chars[start]) && isConsonant(chars[end]);

  while (start < end) {
    if (bothConsonants(start, end)) {
      let firstChar = chars[start];
      let secondChar = chars[end];
      chars[start] = secondChar;
      chars[end] = firstChar;
      start++;
      end--;
    } else if (isConsonant(chars[start])) {
      end--;
    } else if (isConsonant(chars[end])) {
      start++;
    } else {
      end--;
      start++;
    }
  }
  return chars.join('');
}

console.log(reverseConsonants("") === "");
console.log(reverseConsonants("s") === "s");
console.log(reverseConsonants("HELLO") === "LELHO");
console.log(reverseConsonants("leetcode") === "deectole");
console.log(reverseConsonants("example") === "elapmxe");
console.log(reverseConsonants("Consonants") === "sotnonasnC");
```

- that sucked

### [Practice: Compress to Distinct](https://launchschool.com/books/dsa/read/compress_to_distinct_elements)

- brute force:

```javascript
/*

Given a sorted array of integers, your task is to implement a function
`compressToDistinct` that modifies the array in-place to ensure
it starts with a sequence of distinct elements in their original order.
After making these modifications, the function should return
the count of these distinct elements.

The elements in the latter part of the array, after the distinct ones, are not important.

Example:

If the input array is [3, 3, 5, 7, 7, 8], there are four distinct elements: 3, 5, 7, and 8.
After modifying the array to place these distinct elements at the beginning,
the resulting array should look like this -> [3, 5, 7, 8, _, _].
The underscores (_) represent the elements that are no longer important.

You should name the function `compressToDistinct` for the tests to work correctly.

P: Write a function that takes a sorted array and does 2 things:
  1. modifies the array:
    - by putting all distinct elements in ascending order at the beginning of the array.
    - leaves the remaining duplicates at the right hand extremity of the array.
  2. returns an integer representing total distinct elements

E:

testCompressToDistinct([3, 3, 5, 7, 7, 8], 4);
  - 3, 5, 7, 8, 3, 7
testCompressToDistinct([1, 1, 2, 2, 2, 3, 4, 4, 5], 5);
  - 
testCompressToDistinct([0], 1);
testCompressToDistinct([-5, -3, -3, -1, 0, 0, 0, 1], 5);
testCompressToDistinct([6, 6, 6, 6, 6, 6, 6], 1);


D:

- arrays
- counting distinct elements

MM1:
  - create a whole new array of distinct elems
  - then copy the values onto original array 
  - and return a counter fro distinct Elems

MM2:

- reduce (acc, elem, idx)
- acc counts distinct elems
- ...


A:
testCompressToDistinct([-5, -3, -3, -1, 0, 0, 0, 1], 5);

- make an arry of distinct elems (distinctElems) => [-5, -3, -1, 0, 1]

- iterate over inputArray deleting the first occurances of distinct elems => [-3, 0, 0]
- iterate over inputArray unshifting in values from distinct elems => [-5, -3, -1, 0, 1, -3, 0, 0]
- return distinct elems.length=> 5
C:
*/

function testCompressToDistinct(array, expectedLength) {
  const originalReference = array;
  const resultLength = compressToDistinct(array);
  const isSameObject = originalReference === array;
  const isLengthCorrect = resultLength === expectedLength;
  const isModifiedCorrectly = array.slice(0, expectedLength).every((val, idx, arr) => idx === 0 || val > arr[idx - 1]);

  return isSameObject && isLengthCorrect && isModifiedCorrectly;
}

function compressToDistinct(array) {

  let distincts = [];
  let duplicates = [];

  array.forEach((elem) => {
    !distincts.includes(elem) ? distincts.push(elem) : duplicates.push(elem);
  })

  let correctOrder = distincts.concat(duplicates)

  for (i = 0; i < distincts.length; i += 1) {
    array[i] = correctOrder.shift();
  }

  return distincts.length;
}

console.log(testCompressToDistinct([3, 3, 5, 7, 7, 8], 4));
console.log(testCompressToDistinct([1, 1, 2, 2, 2, 3, 4, 4, 5], 5));
console.log(testCompressToDistinct([0], 1));
console.log(testCompressToDistinct([-5, -3, -3, -1, 0, 0, 0, 1], 5));
console.log(testCompressToDistinct([6, 6, 6, 6, 6, 6, 6], 1));

// All tests should log true.
```

- optimised:

```javascript
function compressToDistinct(array) {
  
let anchor = 0;
let runner = 1;
let limit = array.length

while (array[anchor] <= array[runner]) {
  if (array[anchor] === array[runner]) {
    array.push(...array.splice(runner,1));
    } else {
      runner += 1;
      anchor += 1;
    };

    limit -= 1
    if (limit === 0) { return anchor+1 };

  }

return anchor + 1;
}
```

LS solution:

```javascript
function compressToDistinct(nums) {
  if (nums.length <= 1) return nums.length;

  let anchor = 0;

  for (let runner = 1; runner < nums.length; runner++) {
    if (nums[runner] !== nums[anchor]) {
      anchor++;
      nums[anchor] = nums[runner];
    }
  }

  return anchor + 1;
}
```

## BINARY SEARCH
### [Intro to Binary Search](https://launchschool.com/books/dsa/read/introduction_to_binary_search)


### [Binary Search Template](https://launchschool.com/books/dsa/read/binary_search_template)

- off-by-one errors.

#### Tempate:

```javascript
let left = 0;
let right = array.length - 1;

while (left <= right) {
  let mid = Math.floor((left + right) / 2);

  if (array[mid] === target) {
    // Optional early return
  } else if (***comparison***) {
    left = mid + 1;
  } else {
    right = mid - 1;
  }
}
```

// Most often, if the target is not found, additional handling
// or returning a specific value is needed. In many cases it will
// be the index that `left` variable holds, which would indicate
// where the target *would* fit into the array.
### [Demo: Find Zero Position](https://launchschool.com/books/dsa/read/find_zero_position)
### [Demo: Find The Range of Threes](https://launchschool.com/books/dsa/read/find_range_of_threes)

```javascript

// brute force

function findRange(arr) {
  let output = [-1, -1];
  let firstFound = false;
  for ([idx, n] of arr.entries()) {
    if (n === 3 && !firstFound) {
      output[0] = idx;
      firstFound = true;
    } else if (n === 3) {
      output[1] = idx;
    }
  }
  return output;
}
```

- I got peaked at the first 3 steps of the breakdown to solve the binary search version.
- 2 helper functions to find left most and right-most threes.

```javascript
function findLeftMostIndex(array, target) {
  let left = 0;                 // 0
  let right = array.length - 1; // 8
  let leftMostThree = -1;

  while (left <= right) {
    let mid = Math.floor((left + right) / 2);
  
    if (array[mid] === target) {
      leftMostThree = mid;
      right = mid - 1;
    } else if (array[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return leftMostThree;
}

function findRightMostIndex(array, target) {
  let left = 0;                 // 0
  let right = array.length - 1; // 8
  let rightMostThree = -1;

  while (left <= right) {
    let mid = Math.floor((left + right) / 2);
  
    if (array[mid] === target) {
      rightMostThree = mid;
      left = mid + 1;
    } else if (array[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return rightMostThree;
}

function findRange(arr) {
  let left = findLeftMostIndex(arr, 3);
  let right = findRightMostIndex(arr, 3);
  return [left, right];
}

console.log(findRange([1, 2, 3, 3, 3, 3, 3, 4, 5])) // [2, 6]
console.log(findRange([1, 2, 5, 5, 6, 9, 10])) // [-1, -1]
```

### [Practice: Minimum Count](https://launchschool.com/books/dsa/read/minimum_count)

- brute force:

```javascript
// brute force

 function minimumCount(array) {
  let positives = array.filter((n) => n > 0).length;
  let negatives = array.filter((n) => n < 0).length;
  return [positives, negatives].sort((a, b) => a - b)[0];
 }
```

- optimised

```javascript

function indexOfMidBetweenPositiveAndNegative(array) {
  let target = 0;
  let left = 0;
  let right = array.length - 1;
  let mid;

  while (left <= right) {
    mid = Math.floor((left + right) / 2);
    if (array[mid] === target) {
      return mid;
    } else if (array[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return left;
}

function minimumCount(array) {
  let mid = indexOfMidBetweenPositiveAndNegative(array);
  let positives = array.slice(mid)
  let negatives = array.slice(0, mid)
  if (positives[0] === 0) { positives.shift() };
  return [positives, negatives].sort((a, b) => a.length - b.length)[0].length;
}
```

- LS solution: Assumes that there can be multiple zeroes, and so uses two binary search helper methods:

```javascript

```


## LINKED LISTS
### [Intro to Linked Lists](https://launchschool.com/books/dsa/read/introduction_to_linked_lists)
#### [Arrays vs Linked Lists](https://launchschool.com/books/dsa/read/introduction_to_linked_lists#arraysvslinkedlists)
#### T[he Structure of a Linked List](https://launchschool.com/books/dsa/read/introduction_to_linked_lists#structureoflinkedlists)
#### [Types of Linked Lists](https://launchschool.com/books/dsa/read/introduction_to_linked_lists#typesoflinkedlists)
- singly linked
  - commonly encountered in job interviews/coding challenges
- doubly linked
- circular linked
#### [Implementing a Linked List](https://launchschool.com/books/dsa/read/introduction_to_linked_lists#implementingalinkedlist)

- For this course we're only looking at singly linked lists.
- For this course we will focus on the `Node-as-a-class` approach to implementing.
- The class will contain 2 things:
  - a reference to the next node
  - the data we want to store
- This will allow us to encapsulate properties and behaviour of each node into a single entity
- Example:

```javascript
class ListNode {
  constructor(val = 0, next = null) {
    this.val = val;
    this.next = next;
  }
}
```

- Other implementations are available. For instance containing all nodes as node objects in a class called `LinkedList`.
- This waty means the only access point to the LL is via the head node, like accessing a water-slide.
   
### [Arrays vs Linked Lists Performance](https://launchschool.com/books/dsa/read/comparing_arrays_and_linked_lists)

- Choosing whether an array or a linked list is better depends on the program's specific needs.
- One must understnad the performance characteristics of these data structures.

#### [Reading](https://launchschool.com/books/dsa/read/comparing_arrays_and_linked_lists#reading)

- Arrays offer direct access in constant time: `O(1)`
- With linked lists you start only with access to the first node, so you have to traverse the section of the list that precedes your target. This is the notable drawback of linked-lists: their read-efficiency becomes `O(1)`.

#### [Searching](https://launchschool.com/books/dsa/read/comparing_arrays_and_linked_lists#searching)

- Both arrays and linked-lists have linear time-complexity `O(N)`
- (not sure exactly how this is different to reading)

#### [Inserting](https://launchschool.com/books/dsa/read/comparing_arrays_and_linked_lists#inserting)

- In an array inserting at 0 means shifting all the values, but LL have an advantage because it's easy to create another element. It's `O(1)`. However inserting at the end of an LL would be `O(N)`
- Interesting to note is that the worst case scenario for LL (appending) is the best case for arrays and vice-versa
- Sometimes this is a negligible consideration, but sometimes it makes a huge difference.

#### [Deleting](https://launchschool.com/books/dsa/read/comparing_arrays_and_linked_lists#deleting)

- similar to insertion, LLs outperform arrays at the beginning of a list.
  - LL: `O(1)`
  - array: `O(N)` because you have to shift all the other elems.
- But at the end a linked list deletes the element by redirecting the penultimate node to point towards `null`. However, to gether there it needs to traverse the entire list. So `O(N)`
- As with inserting the best case for LLs is the worst case for Arrs and vice-versa.

### [When to Use Linked Lists?](https://launchschool.com/books/dsa/read/when_and_why_to_choose_linked_lists)

#### [Insertion & Deletion](https://launchschool.com/books/dsa/read/when_and_why_to_choose_linked_lists#insertiondeletion)

- With arrays insertion and deletion involve shifting all the other elements in the list. For this reason LL can be better.
- The example given is of a list of 2000 telephone numbers where 400 are incorrectly formatted and need to be deleted.
  - In an array each deletion would create another `O(N)` steps to shift the remaining data to the left and close the gap. If for each 400 elements we shift all the telephonenumbers (2000) that's 800,000 steps
  - In a LL the time complexity of searching is O(N) (2000) plus 400 for each deletion.

### [Demo: Remove Twos](https://launchschool.com/books/dsa/read/remove_twos_from_linked_list)

- How to solve problems with linked lists? With pointers:
  - `prev`
  - `curr`
  - `next` (sometimes)

#### [Problem Description](https://launchschool.com/books/dsa/read/remove_twos_from_linked_list#description)

- Given the head of a linked list, remove all 2s from the LL:
  -  input: 1, 2, 3, 2, 4, null
    -  output: 1, 3, 4, null
  -  input: 2, 3, 2, null
    -  output: 3, null

#### [Algorithm](https://launchschool.com/books/dsa/read/remove_twos_from_linked_list#algorithm)

- Initialize 2 pointers:
  - `prev` = null
  - `curr`=  head of the linked list
- Begin iterating, checking the value of `curr` each iteration:
  - if `curr` is null:
    - break from the loop. This means we're at the end and there are no more elements to check/remove. If it happens right at the beginning it means the list was empty.
    - if `curr` is 2:
      - and `prev` is null
        - save the head as `curr.next`
      - otherwise: set `prev.next` to `curr.next` in order to skip the current node. (like leaving a dance in which all are holding hands in a circle, by connecting the dancers to each side, so you can depart).
    - otherwise: update the `prev` pointer to `curr`
  - Move the `curr` pointer to the next node. (`curr` advances one node regardless of what has happened in this iteration).

#### [Walkthrough](https://launchschool.com/books/dsa/read/remove_twos_from_linked_list#walkthrough)

- The confusing thing for me here is:
  - `prev` and `curr` are pointers. Variables whose only task is to link to the appropriate node. They point to nodes objects (objects of the `ListNode` class), which contain variables pointing to values. The pointers do not point to values.

#### [Solution Code](https://launchschool.com/books/dsa/read/remove_twos_from_linked_list#solution)

```javascript
class ListNode {
  constructor(val = 0, next = null) {
      this.val = val;
      this.next = next;
  }
}

function deleteTwos(head) {
let prev = null;
let curr = head;

if (!head) {
  return head;
}

while (curr) {
  if (curr.val === 2) {
    if (!prev) {
      head = curr.next;
    } else {
      prev.next = curr.next;
    }
  } else {
    prev = curr;
  }
  curr = curr.next;
}

return head;
}

// Helper function to format the linked list into a string
function stringifyList(head) {
let curr = head;
let result = "";
while (curr !== null) {
  result += curr.val + " -> ";
  curr = curr.next;
}
result += "null";
return result;
}

// Test case 1
const head1 = new ListNode(1);
head1.next = new ListNode(2);
head1.next.next = new ListNode(3);
head1.next.next.next = new ListNode(2);
head1.next.next.next.next = new ListNode(4);

console.log("Input: ", stringifyList(head1));
console.log("Output:", stringifyList(deleteTwos(head1)));
// Input:  1 -> 2 -> 3 -> 2 -> 4 -> null
// Output: 1 -> 3 -> 4 -> null

// Test case 2
const head2 = new ListNode(2);
head2.next = new ListNode(3);
head2.next.next = new ListNode(2);

console.log("Input: ", stringifyList(head2));
console.log("Output:", stringifyList(deleteTwos(head2)));
// Input:  2 -> 3 -> 2 -> null
// Output: 3 -> null
```

### [Pointers in Linked Lists](https://launchschool.com/books/dsa/read/understanding_pointers_in_linked_lists)

- cat analogy
- I prefer an analogy of ceilidh dancers.

###  [Dummy Nodes in Linked Lists](https://launchschool.com/books/dsa/read/dummy_nodes_in_linked_lists)

- Fictitious temporary nodes to simplify complex scenarios.
- For the most part we use dummy nodes as references to a head node. By introducing a dummy node before the head, we create a stable reference point.
- This is to avoid the part of the code that has to do something different when deleting the first element of the LL.

```javascript
function deleteTwos(head) {
  let dummy = new ListNode();
  dummy.next = head;
  let prev = dummy;
  let curr = head;

  while (curr) {
    if (curr.val === 2) {
      prev.next = curr.next;
    } else {
      prev = curr;
    }
    curr = curr.next;
  }

  return dummy.next;
}
```

### [Demo: Reverse Linked List](https://launchschool.com/books/dsa/read/reverse_linked_list)

- We introduce a new variable called `nextNode`.
- We iterate over a LL looking at 3 adjacent nodes at a time, resetting their `next` properites to point backwards.
- The `nextNode` variable is necessary to keep a reference to the next node in the LL.
- We return `prev` at the end, because it's become the new `head`.
- When solving such problems drawing out what happens at each stage can be a real necessity. It will help you to catch overseen errors.

```javascript
class ListNode {
  constructor(val = 0, next = null) {
    this.val = val;
    this.next = next;
  }
}

function reverseLinkedList(head) {
  if (!head) {
    return head;
  }

  let prev = null;
  let curr = head;

  while (curr !== null) {
    let nextNode = curr.next;
    curr.next = prev;
    prev = curr;
    curr = nextNode;
  }
  return prev;
}

function printList(head) {
  let curr = head;
  let result = "";
  while (curr !== null) {
    result += curr.val + " -> ";
    curr = curr.next;
  }
  result += "null";
  return result;
}

const head1 = new ListNode(1);
head1.next = new ListNode(2);
head1.next.next = new ListNode(3);
head1.next.next.next = new ListNode(4);

console.log("Input: ", printList(head1));
console.log("Output: ", printList(reverseLinkedList(head1)));
```

### [Practice: Remove Every Second](https://launchschool.com/books/dsa/read/remove_every_second)

my solution:

```javascript

function removeEverySecondNode(head) {

  //DEALING WITH LISTS OF LENGTH 0 - 2
  if (head === null) { return null };
  if (head.next === null) { return head };
  if (head.next.next === null) { 
    head.next = null;
    return head; 
  };

  // POINTERS
  let first = head;
  let second = first.next;
  let third = second.next;

  while(true) {
    first.next = third;
    // reset pointers:
    if (third.next === null) { 
      return head 
    } else if (third.next.next === null) {
      third.next = null;
      return head;
    }
    first = third;
    second = first.next;
    third = second.next;
  }
}
```

LS solution:

```javascript
function removeEverySecondNode(head) {
  let curr = head;
  while (curr && curr.next) {
    curr.next = curr.next.next;
    curr = curr.next;
  }
  return head;
}
```

## STACKS & QUEUES
### [Intro to Stacks and Queues](https://launchschool.com/books/dsa/read/introduction_stacks_queues)

- abstract data-types that devs must know about.
- AKA "data-structures", but really stacks and queues describe how we interact with the data, rather than the structure of the data itself.
- We can build stacks and queues with structures like linked-lists, arrays, dynamically resizing arrays.

#### [Core Characteristics](https://launchschool.com/books/dsa/read/introduction_stacks_queues#corecharacteristics)

- Linear Structure:
  - we travels Stacks and queues sequentially, always looking at one element at a time.
- Operational efficiency:
  - adding and removing elements are typically `O(1)` operations making them very efficient for certain tasks.
- Controlled access:
  - The limited access to data simplifies control of the data-flow. This is a significant advantage.

### [Stacks](https://launchschool.com/books/dsa/read/stacks)

- Last in first out (LIFO).

#### Key operations

- Push : `O(1)`
- Pop: `O(1)`
- Peek

#### Practical Applications of Stacks

##### Function call management

- Whenever a function is called, information about where the function was called from and its internal variables are stored in a stack.These bundles of information stack up. When one function call ends the program returns to the place that function was called. 

##### Undo mechanisms in Applications

- Control z in a word-doc/image-editing programme etc.

##### Web Browser Nevigation

- the back button

##### Depth-first Search (DFS) in Graphs

- Graphs come later in this lesson.
- Depth-first search algorithm.

### [Implement Stack with Linked List](https://launchschool.com/books/dsa/read/implement_stack_with_linked_list)

- I will try this again later. My solution didn't quite work, but I don't want to get bogged down at this stage.

### [Queues](https://launchschool.com/books/dsa/read/queues)

- FIFO, like a stack

#### [Key operations](https://launchschool.com/books/dsa/read/queues#keyoperations)

- Enqueue:
  - Adding an element to the back of the queue (like when you join a queue).
  - O(1) because it doesn't shift or move the exisiting elements.
- Dequeue:
  - Remove the front element
  - Also O(1) because one needn't look through or rearrange the rest of the elements.
- Peek
  - Look at who is at the front of the line.

#### [Practical applications of queues](https://launchschool.com/books/dsa/read/queues#practicalapplications)

- Process scheduling:
  - In operating systems processes are managed in a queue format, with the CPU taking the front element when it can.
- Print job management
  - Especially a printer connected to multiple computers. The system is fair because documents are printed in the order they are received.
- Real time systems.
  - eg. traffic lights/ customer service lines.
- Breadth-first Search (BFS) in Graphs
  - We'll look at this later, but it searches nodes on a graph ("vertex") systematically.

### [Implement Queue using Linked List](https://launchschool.com/books/dsa/read/implement_queue_with_linked_list)

My solution:

```javascript:
class ListNode {
  constructor(val = 0, next = null) {
    this.val = val;
    this.next = next;
  }
}

class Queue {
  constructor() {
    this.front = null;
    this.back = null;
  }
  peek() {
    // Returns the value of the top most element without removing it.
    return this.front ? this.front.val : null;
    // If the queue is empty, it returns `null`.
  }

  enqueue(value) {
    // Adds an item to the queue
    let newNode = new ListNode(value);
    // if the queue is empty, newNode becomes front and back
    if (this.back === null) {
      this.back = newNode;
      this.front = newNode;
    } else {
    // otherwise the person at the back sets their 'next' to the new node
      this.back.next = newNode;
    // and the 'back' pointer points the this new node.
      this.back = newNode;
    }
  }

  dequeue() {
    // Removes the item from the queue and returns it
    let output = null;
    if (this.front) {
      output = this.front;

      if (this.front.next) {
        this.front = this.front.next;
      } else {
        this.back = null;
        this.front = null;
      }

    }
    // If the queue is empty, it returns `null`.
    return output;
  }
}

const myQueue = new Queue();
myQueue.enqueue(1);
console.log('Front element:', myQueue.peek());  // logs 'Front element: 1'
myQueue.enqueue(2);
console.log('Front element:', myQueue.peek());  // logs 'Front element: 1'
myQueue.enqueue(3);
console.log('Front element:', myQueue.peek());  // logs 'Front element: 1'
myQueue.dequeue();
console.log('Front element after dequeue:', myQueue.peek());  // logs 'Front element after dequeue: 2'
myQueue.dequeue();
console.log('Front element after dequeue:', myQueue.peek());  // logs 'Front element after dequeue: 3'
myQueue.dequeue();
console.log('Peek on empty queue:', myQueue.peek());  // logs 'Peek on empty queue: null'
console.log('`back` on empty queue:', myQueue.back);  // logs '`back` on empty queue: null'
```

LS solution: Pretty similar to mine - but more elegant.

### [Stacks and Queues in Interviews](https://launchschool.com/books/dsa/read/stacks_and_queues_in_interviews)

- In many technical interviews stacks and queues aren't explicitly mentioned, so you need to know when one is an appropriate tool for he problem at hand.

#### [When to use a Stack](https://launchschool.com/books/dsa/read/stacks_and_queues_in_interviews#whentouseastack)
- Reversal properties:
  - ie string reversal, or undo operations in text editors.
- Balancing symbols:
  - ie. matching parentheses
- Depth-first search(DFS)
  - Learn about this later, but we use this to search tree/graph data-structures.
- A problem that requires a stack could also be solved with recursion, which uses a stack to keep track of function calls.

#### [When to use a queue](https://launchschool.com/books/dsa/read/stacks_and_queues_in_interviews#whentouseaqueue)

- order maintenance:
  - Task scheduling
  - managing printing jobs
- Breath-first-search
  - more on this later
- Buffering or pipeline
  - streaming data
  - load-balancing

### [Practice: Matching Brackets](https://launchschool.com/books/dsa/read/matching_brackets)

- nailed it

## CONCLUSION
### [Conclusion & Next Steps](https://launchschool.com/books/dsa/read/conclusion_and_next_steps)

- tick

|  | 1st: 1st read | 2nd: deep-dive | 3rd: find/fill gaps |
| :--- | :---: | :---: | :---: | 
| Introduction to data-structures and algorithms | start 7.11.24 | start 29.1.25 |
| Sorting algorithms | 
| Pointer-based mental models | 
| linked lists |
| Binary search | 
| Stacks & queues | 21.11.24

