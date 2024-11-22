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

- 

### Fibonacci Function
### Space Complexity
### Fibonacci Call Stack
## The Function Signature
### Helper Functions
## Demo: Valid Palindrome String
### Problem Description
### Recursive Definition
### Implementation
## Practice: Sum of Natural Numbers
### Problem Description
### Walkthrough & Solution
# DIVIDE AND CONQUER ALGORITHMS
## Intro to Divide and Conquer Algorithms
## Quicksort: Partitioning
## Quicksort: Adding Recursion
## Quicksort: Pivot Element Position
## Divide & Conquer in Quicksort
## QuickSort Time Complexity
# DYNAMIC PROGRAMMING
## Intro to Dynamic Programming
### Two Strategies
### Time Complexity
### When to use DP
### DP vs DnC
## Demo: Hopping Chaos I
## Demo: Hopping Chaos II
## DP Caching: Arrays vs. Maps
## Demo: Chaos in the Grid (Bottom-Up)
## Demo: Chaos in the Grid (Top-Down)
## Top-Down vs. Bottom-Up Approach
## Practice: Chaos in Grid with Cats
# BINARY TREES
## Intro to Trees
## Binary Trees
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
