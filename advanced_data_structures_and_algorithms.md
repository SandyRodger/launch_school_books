# INTRODUCTION TO RECURSION
## [Understanding Recursion](https://launchschool.com/books/advanced_dsa/read/understanding_recursion)

- functions calling themselves

### [Example Problem](https://launchschool.com/books/advanced_dsa/read/understanding_recursion#example)

```javascript
function populationCount(number) {
  console.log(number);
  if (number === 0) {
    return;
 }
  populationCount(number - 1);
}

populationCount(5);
```

### [More Terminology](https://launchschool.com/books/advanced_dsa/read/understanding_recursion#terminology)

- the recursive case: the apt of the function where it calls itself:
  - `populationCount(number - 1);`
- the reduction step: the part where the input is modified to move closer to the base case:
  - `number - 1`

## [Call Stack in Recursive Algorithms](https://launchschool.com/books/advanced_dsa/read/exploring_call_stack)

- yup.

### [Understanding the Call Stack](https://launchschool.com/books/advanced_dsa/read/exploring_call_stack#understandingcallstack)

- LIFO

### [The Call Stack and Non-recursive Function Calls](https://launchschool.com/books/advanced_dsa/read/exploring_call_stack#nonrecursivefunctioncalls)

- yup

### [The Call Stack and Recursive Function Calls](https://launchschool.com/books/advanced_dsa/read/exploring_call_stack#recursivefunctioncalls)

#### The factorial function

```javascript
function factorial(n) {
  if (n === 1) {
    return 1; // Base case: factorial of 1 is 1
 } else {
    return n * factorial(n - 1); // Recursive case
 }
}
```

### [Stack Overflow](https://launchschool.com/books/advanced_dsa/read/exploring_call_stack#stackoverflow)

- there needs to be a well-defined base case to prevent this.

## [Recursion: Time & Space Analysis](https://launchschool.com/books/advanced_dsa/read/time_and_space_complexity_recursive)

### [Time Complexity](https://launchschool.com/books/advanced_dsa/read/time_and_space_complexity_recursive#timecomplexity)

- counting recursive calls.
- determining the work done.
- combining recursive calls and work done
- drawing a recursion tree

### [Factorial Function](https://launchschool.com/books/advanced_dsa/read/time_and_space_complexity_recursive#factorial)

- O(N)

### [Fibonacci Function](https://launchschool.com/books/advanced_dsa/read/time_and_space_complexity_recursive#fibonacci)


### [Space Complexity](https://launchschool.com/books/advanced_dsa/read/time_and_space_complexity_recursive#spacecomplexity)

#### Space Complexity of the Factorial Algorithm:

- determined by maximum depth.

#### Space Complexity of the Fibonacci Algorithm:

- actually linear - despite time complexity being exponential.

### [Fibonacci Call Stack](https://launchschool.com/books/advanced_dsa/read/time_and_space_complexity_recursive#fibonaccicallstack)

- go over this again. brain is mush.

## [The Function Signature](https://launchschool.com/books/advanced_dsa/read/function_signature)

- 

### [Helper Functions](https://launchschool.com/books/advanced_dsa/read/function_signature#helperfunctions)

#### dynamic programming

## [Demo: Valid Palindrome String](https://launchschool.com/books/advanced_dsa/read/valid_palindrome_string)


### [Problem Description](https://launchschool.com/books/advanced_dsa/read/valid_palindrome_string#problemdescription)
### [Recursive Definition](https://launchschool.com/books/advanced_dsa/read/valid_palindrome_string#recursivedefinition)
### [Implementation](https://launchschool.com/books/advanced_dsa/read/valid_palindrome_string#implementation)
## [Practice: Sum of Natural Numbers](https://launchschool.com/books/advanced_dsa/read/sum_of_natural_numbers)

- Did it in seconds: I am good at this.

# DIVIDE AND CONQUER ALGORITHMS

## [Intro to Divide and Conquer Algorithms](https://launchschool.com/books/advanced_dsa/read/introduction_to_divide_and_conquer)

### [Divide:](https://launchschool.com/books/advanced_dsa/read/introduction_to_divide_and_conquer#divide)

### [Conquer:](https://launchschool.com/books/advanced_dsa/read/introduction_to_divide_and_conquer#conquer)

### [Combine](https://launchschool.com/books/advanced_dsa/read/introduction_to_divide_and_conquer#combine)

## [Quicksort: Partitioning](https://launchschool.com/books/advanced_dsa/read/quicksort_partitioning)

- A popular sorting algorithm used by many programming languages beacuse it's fast and efficient (in average scenarios)
-  Partitioning:
  -  Select a pivot point("somewhat random"?)

### [Algorithm](https://launchschool.com/books/advanced_dsa/read/quicksort_partitioning#algorithm)

- We use 2 pointers coming from the far left and far right.
  - left starts from the left and ensures that everything from here to the meeting point is less than the pivot
  - right moves from the right ensuring that the elements are more than the pivot.
  - When we encounter elements that aren't in the right place we can swap them and continue.

#### steps:

1. Set the pivot as the first element in the array
2. assign left and right pointers to the leftmost and rightmost indeces of the remaining elements.
3. Incremenet left until it reaches a value greater than or equal to the pivot or the right pointer
4. Decrement the right pointer until it reaches a value less than pivot or less than left pointer (can't be equal).
5. If at this point left has gone beyond right move to step 6, otherwise go back to step 3.
6. Swap the value at the pivot index witht he value at the right pointer, placing the pivot in the correct position in the array.

- the result will not be sorted, but the pivot will seperate the numbers less than and greater than it.

## [Quicksort: Adding Recursion](https://launchschool.com/books/advanced_dsa/read/quicksort_recursion)

- if we take each side and do a quick sort on it, recursively, then we end up with a sorted array.

## [Quicksort: Pivot Element Position](https://launchschool.com/books/advanced_dsa/read/quicksort_pivot_selection)

#### implementation

## [Divide & Conquer in Quicksort](https://launchschool.com/books/advanced_dsa/read/understanding_divide_and_conquer_quicksort)

### Divide

- In the `partition` function. The array is divided into 2 subarrays based on the pivot.

### Conquer

- This is recursively implementing the `quickSort` on the sections of the array until it's all sorted.

### Combine

- This isn't a step, it just happens implicitly during the partitioning
## [QuickSort Time Complexity](https://launchschool.com/books/advanced_dsa/read/quicksort_time_complexity)

- Two main factors:
  - partitioning
  - recursion
### Partitioning Step

- Scan the array once and partition it based on the pivot.
  - Linear time complexity (`O(N)`.

### Recursive step

- Until each subarray contains either 0 or 1 element.
  - `log N`

### Combining the Partitioning and recursion steps

- Because we know partitioning is `O(N)` and the recursion is `log N` we can multiply these and see that the the overall time complexity of quickSort is `O(NlogN)`
- This reflects the average time complexity, but in worst case scenarios quickSort degrades to `O(N^2)`

# DYNAMIC PROGRAMMING
## [Intro to Dynamic Programming](https://launchschool.com/books/advanced_dsa/read/introduction_to_dynamic_programming)

- A technique used to solve tricky problems (not just in computer sccience). It is used to avoid repeating a task when a problem involves going over the same data-set a few times (my words).
- DP has a reputation as being difficult.

- break down:
  - ... the problem into sub-problems
- solve and store
  - ... the smaller problems (like building a jig-saw).
- reuse solutions
  -  When we encounter the same smaller problem again we don't have to solve it from scratch.

### [Two Strategies](https://launchschool.com/books/advanced_dsa/read/introduction_to_dynamic_programming#twostrategies)

- Top-down ("Memoization") : the recursive approach
  - Focus on the original problem: Begin by expressing the solution to the OG problem in terms of solutons to smaller problems.
  - Recursive break-down: Break the problem down into smaller sub-problems - often with a recursive element.
  - Memoization for efficiency: store the results of each sib-problem, so you can check if the problem has already been solved before attempting it.

- Bottom-up (tabulation): the iterative approach
  - Solves in order of increasing complexity: Start with the smallest and simplest subproblem (Often the base-case), then use those solutions to solve bigger problems.
  - Builds-up solutions: systematically builds solutions to the sub-problems using a table of some kind (maybe an array, maybe a hash-map object). The table is filled iteratively with each entry being a solution to a particular subproblem.
  - Iterative Computation: relies on loops to fill in the table avoiding the overhead of recursive function calls.

### Time complexity

- Efficiency can vary significantly depending on the implementation strategy. Without Memoization it can be exponentially complex  (`O(2^n)`), but when memoizatin is implemented it goes down to `O(N)` if the problem has a linear number of states, or `O(N^2)` if the problem starts from a 2d space.

### When to use DP

- Good for problems that require optimizing specific criteria/ accumulating results over several computations:
  - determine min/max value
  - assess possibilities (true/false)
  - optimise an outcome
  - calculate totals
  - count distince ways to achieve a goal
- (Not appropriate when you need to find all possible solutions without optimization. Then a combinatorial approach like back-tracking would be better.

### DP vs DnC

 - It's not divide and conquer. It looks the same, but:
   - DnC you solve each sub-problem only once, then combine results - done.
   - Dynamic programming is for when sub-problems overlap (meaning they share common calculations). DP stores the results of these overlapping subproblems so you needn't repeat it.

## [Demo: Hopping Chaos I](https://launchschool.com/books/advanced_dsa/read/hopping_chaos_top_down)

```javascript
function hoppingChaos(n) {
  const memo = new Map();

  function waysToN(n) {
    if (n === 1) {
      return 1;
    }
    if (n === 2) {
      return 2;
    }
    if (memo.has(n)) {
      return memo.get(n);
    }
    const result = waysToN(n - 1) + waysToN(n - 2);
    memo.set(n, result);
    return result;
  }

  return waysToN(n);
}
```

### [Time and space complexity](https://launchschool.com/books/advanced_dsa/read/hopping_chaos_top_down#timeandspacecomplexity)


## [Demo: Hopping Chaos II](https://launchschool.com/books/advanced_dsa/read/hopping_chaos_bottom_up)

### [Problem description](https://launchschool.com/books/advanced_dsa/read/hopping_chaos_bottom_up#problemdescription)

### [Bottom-up walkthrough](https://launchschool.com/books/advanced_dsa/read/hopping_chaos_bottom_up#bottomup)

### [Solution](https://launchschool.com/books/advanced_dsa/read/hopping_chaos_bottom_up#solution)

### [Time and space complexity](https://launchschool.com/books/advanced_dsa/read/hopping_chaos_bottom_up#timeandspacecomplexity)

- same as the solution with recursion & memoization (`O(N)`)
- It can be solved with `O(1)` time complexity in the following way:

```javascript
function hoppingChaos(n) {
  if (n === 1) {
    return 1;
  }
  if (n === 2) {
    return 2;
  }

  let prev2 = 1;
  let prev1 = 2;

  for (let i = 3; i <= n; i++) {
    const temp = prev1 + prev2;
    prev2 = prev1;
    prev1 = temp;
  }

  return prev1;
}
```

## [DP Caching: Arrays vs. Maps](https://launchschool.com/books/advanced_dsa/read/cache_strategies_dynamic_programming)

- Arrays:
  - Performance:
    - Generally more performant than hashes (which `Map` is a kind of)
    - better memory locality
      - always use contiguous memory locations which helps CPU performance
    - avoid hashing overhead
      - The cost of computing the value of a key and avoiding potential collisions(...?)
  - Simplicity:
    - Straightforward IF the problem involves a fixed range of integer indeces, like in the Hopping Chaos problem.
- Maps:
  - Flexibility:
    - more flexible than arrays
      - can handle keys of various types (not just integers, like indexes)

- In Hopping chaos one solution uses a map, the other uses an array, to show that these choices are often interchangeable.
- A key point is if the keys aren't integers a hashmap is usually better.

## [Demo: Chaos in the Grid (Bottom-Up)](https://launchschool.com/books/advanced_dsa/read/chaos_in_the_grid_bottom_up)



## [Demo: Chaos in the Grid (Top-Down)](https://launchschool.com/books/advanced_dsa/read/chaos_in_the_grid_top_down)



## [Top-Down vs. Bottom-Up Approach](https://launchschool.com/books/advanced_dsa/read/top_down_vs_bottom_up)
## [Practice: Chaos in Grid with Cats](https://launchschool.com/books/advanced_dsa/read/chaos_in_the_grid_with_cats)

- I'm going to come back to this.
- I'm supposed to be practiscing what I've learnt in the previous sections, but It's been a minute and I need to go over these methods again. 

# BINARY TREES

## [Intro to Trees](https://launchschool.com/books/advanced_dsa/read/introduction_to_trees)

### [Terminology](https://launchschool.com/books/advanced_dsa/read/introduction_to_trees#terminology)

- Nodes: The basic unit of a tree. Each node contains data.
- Edges: they have direction. Incoming and outgoing.
- Parent and child nodes. They can all be either or both, but the rott can only be parent.
- Leaf nodes: nodes that have no children.
- levels and heights- what you think they are.

## [Binary Trees](https://launchschool.com/books/advanced_dsa/read/binary_trees)

### Key properties of Binary trees

- each node has max 2 children. ("left child", "right child")
- One unique root node (so all nodes start in the same place)
- Unique path.
- (Can be an empty tree)

### [Representing a Binary Tree in Javascript](https://launchschool.com/books/advanced_dsa/read/binary_trees#representingatree)


## Types of Binary Trees
## Divide & Conquer in Tree Problems
## Practice: Binary Tree Height
## Tree Traversal: DFS and BFS
## Practice: Preorder Traversal
## Practice: Inorder Traversal
## Practice: Postorder Traversal
## Practice: Level Order Traversal
## Binary Search Tree
## Practice: Find Node in a BST
# GRAPHS
## Introduction to Graphs
## Types of Graphs
## Graphs with Adjacency List
## Graph Traversal Part I
## Edge List to Adjacency List
## Graph Traversal Part II
## Practice: Has Path
## Demo: Number of Forests
## Practice: Largest Forest Area
# BACKTRACKING
## Introduction to Backtracking
## Terminology
## Problem Solving Approach
## Template
## Demo: Permutations
## Practice: Combinations
# CONCLUSION
## Conclusion & Next Steps
