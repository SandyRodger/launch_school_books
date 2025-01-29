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

- Using a `Node` class.
- Each `Node` object stores:
  - `val`
  - `left`
  - `right`

```javascript
class Node {
  constructor(value) {
    this.val = value;
    this.left = null;
    this.right = null;
  }
}

const root = new Node(1);
root.left = new Node(2);
root.right = new Node(3);
root.right.left = new Node(4);
```

### [Time and Space COmplexities of Binary Tree Operations](https://launchschool.com/books/advanced_dsa/read/binary_trees#timeandspacecomplexity)

- If you're searching/inserting/deleting it's just `O(N)` complexity because there isn't an order for the nodes, which means you have to look through all of them to find the one you need.
- Insertion and deletion is `O(1)`, but finding the right node is still `O(N)`
- Space complexity is usually the tree's height (`O(h)`). That's because a lot of tree operations are recursive. If we're using an iterative approach it depends on if we choose DFS or BFS. (more on that later)

## [Types of Binary Trees](https://launchschool.com/books/advanced_dsa/read/types_of_binary_trees)

### [Full Binary Tree](https://launchschool.com/books/advanced_dsa/read/types_of_binary_trees#full)

- all node has either 2 or 0 children. No single children.

### [Complete Binary Tree](https://launchschool.com/books/advanced_dsa/read/types_of_binary_trees#complete)

- All levels are fully filled, with the possible exception of the last level, built even that has to be filled left to right completely.

### [Perfect Binary Tree](https://launchschool.com/books/advanced_dsa/read/types_of_binary_trees#perfect)

- Both full and complete. The most symmetrical type.
- All leaf nodes are at the same level.
- Total nodes doubles at each level. Therefore the height of the tree grows logarithmically.
- The number of nodes at the lowest level = the sum of all other nodes + 1.

### [Balanced Binary Tree](https://launchschool.com/books/advanced_dsa/read/types_of_binary_trees#balanced)

- The height of left and right sides differs by max 1.

## [Divide & Conquer in Tree Problems](https://launchschool.com/books/advanced_dsa/read/divide_and_conquer_binary_trees)

- D&C is really good for binary trees. 

### [A complimentary duo](https://launchschool.com/books/advanced_dsa/read/divide_and_conquer_binary_trees#complementary)

- The structures of each match intuitively. D&C is therfore an effective and efficient approach for solving tree-related problems.
- Like this:
  - Natural Segmentation: Each node in a binary tree acts as the root of its own left and right sub-trees. This breaks up the tree into smaller self-contained units. This is just like the "divide" bit of D&C.
  - Recursive nature: Binary trees are inherently recursive. Each subtree is a binary tree. So just like in D&C sub-problems are solved in the same way as the original problem.
  - Combining solutions: The heirarchical natue of binary trees makes combining solutions quite simple.

## [Practice: Binary Tree Height](https://launchschool.com/books/advanced_dsa/read/binary_tree_height)

- Hmmm, I'll come back when I have a fresh brain.

## [Tree Traversal: DFS and BFS](https://launchschool.com/books/advanced_dsa/read/binary_tree_traversal)

### Binary Tree Traversal
#### [Depth-First Search](https://launchschool.com/books/advanced_dsa/read/binary_tree_traversal#dfs)

- Go as deep as you can before exploring side-caves (laterally)
- Can be iterative or recursive.
- Three DFS traversal strategies:
  - preorder
  - inorder
  - postorder
- These determine the order in which the nodes are "processed".

##### [Preorder Traversal](https://launchschool.com/books/advanced_dsa/read/binary_tree_traversal#preorder)

- 'pre' here meaning that the node is processed before it's subtrees are traversed. (In this example the processing will involve adding the node's value to the `result` array.
- `NLR` is the pattern we follow for this:
  - Node
  - Left
  - Right
- Processing a `Left` node will begin a new `NLR` sub-process for that node. (recursion)

##### [Inorder Traversal](https://launchschool.com/books/advanced_dsa/read/binary_tree_traversal#inorder)

- We process the node between L and R (`LNR`)

##### [PostOrder Traversal](https://launchschool.com/books/advanced_dsa/read/binary_tree_traversal#postorder)

- `LRN`

##### [Breadth-First Search](https://launchschool.com/books/advanced_dsa/read/binary_tree_traversal#bfs)

- Explores nodes level by level, moving outward to all its children.
- Uses a queue data-structure. This helps nodes be processed as FIFO.

## [Practice: Preorder Traversal](https://launchschool.com/books/advanced_dsa/read/binary_tree_preorder_traversal)

```javascript
  function processNode(currentNode) {
    // console.log(currentNode.val);
    output.push(currentNode.val);
    if (currentNode.left) {
        processNode(currentNode.left);
      } 
    if (currentNode.right) {
        processNode(currentNode.right);
      }
    }

  processNode(rootNode);
  return output;
}
```

## [Practice: Inorder Traversal](https://launchschool.com/books/advanced_dsa/read/binary_tree_inorder_traversal)

- same as above, but move the push to after the L:

```javascript
function inorderTraversal(rootNode) {
  // LNR
  let output = [];

  function processNode(currentNode) {
    // console.log(currentNode.val);
    if (currentNode.left) {
        processNode(currentNode.left);
      } 
    output.push(currentNode.val);
    if (currentNode.right) {
        processNode(currentNode.right);
      }
    }

  processNode(rootNode);
  return output;
}
```

## [Practice: Postorder Traversal](https://launchschool.com/books/advanced_dsa/read/binary_tree_postorder_traversal)

- This time LRN, so just move 1 line:

```javascript
function postorderTraversal(rootNode) {
  // LRN
    let output = [];
  
    function processNode(currentNode) {
      if (currentNode.left) {
          processNode(currentNode.left);
        } 
      if (currentNode.right) {
          processNode(currentNode.right);
        }
      output.push(currentNode.val);
      }
  
    processNode(rootNode);
    return output;
  }
```

## [Practice: Level Order Traversal](https://launchschool.com/books/advanced_dsa/read/level_order_traversal)

```javascript
function bfs(rootNode) {
  let queue = [rootNode];
  let output = [];

  while (queue.length) {
    if (queue[0].left) {queue.push(queue[0].left)};
    if (queue[0].right) {queue.push(queue[0].right)};
    output.push(queue.shift().val);
  }

  return output;
}
```

## [Binary Search Tree](https://launchschool.com/books/advanced_dsa/read/binary_search_tree)

- like a binary tree, but ordered. ie each left is less than the parent and each right is greater.
- Each sub-tree must also be a valid BST.

### [Time and Space Complexities of Binary Search Tree Operations](https://launchschool.com/books/advanced_dsa/read/binary_search_tree#timeandspacecomplexity)

- Search:
  - On average `O(logN)`
  - Each step down the tree halves the search path (similar to binary searching a sorted array).
- Insertion and deletion:
  - Takes `O(logN)` assuming the tree remains balanced.

- Unbalanced Trees:
  - If you change the nodes on either side too much it will affect the performance.
  - Lists can become "left-heavy" or "right heavy".
  - For insdtance if you keep adding elements in ascending or descending order.
- Space complexity:
  - Usually `O(h)`, where h represents the tree's height.
  - It's rare to do a BFS on a binary search tree.

## [Practice: Find Node in a BST](https://launchschool.com/books/advanced_dsa/read/find_node_in_bst)

```javascript
function findNodeInBST(root, searchVal) {
  if (Object.is(null, root)) {return false};
  let currentNode = root;

  while (currentNode.left || currentNode.right ) {
    if (currentNode.val === searchVal) {
      return true;
    } else if (currentNode.val < searchVal) {
      currentNode = currentNode.right;
    } else {
      currentNode = currentNode.left;
    }
  }

  return currentNode.val === searchVal;
}
```

- LS solution:

```javascript
function findNodeInBST(root, target) {
  if (root === null) {
    return false;
  }
  if (root.val === target) {
    return true;
  }
  return findNodeInBST(target > root.val ? root.right : root.left, target);
}
```

# GRAPHS
## [Introduction to Graphs](https://launchschool.com/books/advanced_dsa/read/introduction_to_graphs)
- vertex
- edge
### [why graphs matter in the real world](https://launchschool.com/books/advanced_dsa/read/introduction_to_graphs#whygraphsmatter)

- they mirror real relationships like:
  - facebook friends
  - ancestors
  - customers who bought this also...
  - maps find routes like this

## [Types of Graphs](https://launchschool.com/books/advanced_dsa/read/types_of_graphs)

### [Directed and Undirected graphs](https://launchschool.com/books/advanced_dsa/read/types_of_graphs#directedandundirected)

- Undirected graphs:
  - The edges between vertices (points) don't have specific direction. So like two facebook firneds are just friends, the frendship doesn't go in one way or another. It's equal.
- Directed graphs:
  - like following someone on Insta.

### [Neighbour nodes in directed and undirected graphs](https://launchschool.com/books/advanced_dsa/read/types_of_graphs#neighbornodes)

- neighbour nodes are what they sound like.
- In undirected graphs:
  - straightforward
- In directed graphs:
  - more nuanced:
    - incoming neighbour
      - "incoming neighbour to 2"
    - outgoing neighbour
      - "outgoing neighbout to 2"
#### [weighted and unweighted graphs](https://launchschool.com/books/advanced_dsa/read/types_of_graphs#weightedandunweighted)

- unweighted graphs:
  - all edges are equal.
- weighted graphs
  - each edge is assigned a weight which represents a value like:
    - distance
    - cost
    - time
  - so for instance in google maps the edges help to find the shortest route.

#### [cyclic and acyclic graphs](https://launchschool.com/books/advanced_dsa/read/types_of_graphs#cyclicandacyclic)

- cyclic graphs
  - these graphs have at least one loop where you can start and stop on the same vertex.
  - Good for modelling systems that can return to their original state
- acyclic graphs
  - No loops here
  - No ways back
  - Can be used for heirarchies/processes with a clear direction and no repetition.

## [Graphs with Adjacency List](https://launchschool.com/books/advanced_dsa/read/representing_graphs_adjacency_list)

- One of the most common and efficient ways to represent graphs.

### [What is it?](https://launchschool.com/books/advanced_dsa/read/representing_graphs_adjacency_list#whatisanadjacencylist)

- Each vertex stores a list of the vertices it is connected to.
- Implemented as a dictionary or `Map`, in which each key represents a vertex and its value is an array of connected vertexes. The value array therefore holds all outgoing neighbours.

### [Why use an adjacency list](https://launchschool.com/books/advanced_dsa/read/representing_graphs_adjacency_list#whyuseanadjacencylist)

- Efficient storage:
  - particilarly good at storing sparse graphs where most vertices have relatively few connections. Other methods might track all possible connections, which would be a waste of resources.
- Quick look up:
  - just by accessing the key.
- Easy implementation:
  - easy to code.

### [Adjacency List in JavaScript](https://launchschool.com/books/advanced_dsa/read/representing_graphs_adjacency_list#adjacencylistinjs)

- `Map`s are better, because in a javascript Object the keys would need to be strings. 

```javascript
const adjList = new Map();
adjList.set(1, [2, 3]);
adjList.set(2, [4]);
adjList.set(3, [5]);
adjList.set(4, []);
adjList.set(5, [6]);
adjList.set(6, []);
```

## [Graph Traversal Part I](https://launchschool.com/books/advanced_dsa/read/graph_traversal_part_1)

- searching though a directed acyclic graph with DFS and BFS.

- DFS
  - With graphs it usually makes most sense to do DFS traversal.

### [LS bot on DFS and BFS in graphs]

- I asked @LSBot:
  - can you clarify what a depth-first-search and a breadth-first-search do in undirected graphs and how they differ?

- LSBot replied

  - Certainly! I'd be happy to clarify the concepts of depth-first search (DFS) and breadth-first search (BFS) in the context of undirected graphs, and explain how they differ.
Both DFS and BFS are graph traversal algorithms used to explore or search through all the vertices of a graph. In an undirected graph, the edges between vertices don't have a direction, meaning you can traverse from one vertex to another in either direction.
Let's start with Depth-First Search (DFS):
1.  Depth-First Search (DFS):
    DFS explores as far as possible along each branch before backtracking. In an undirected graph, it works as follows:
    •   Start at a chosen vertex.
    •   Explore one of its unvisited neighbors.
    •   Continue this process, always choosing an unvisited neighbor of the current vertex.
    •   If there are no unvisited neighbors, backtrack to the previous vertex and explore its other neighbors.
    •   Repeat until all vertices have been visited.
    DFS tends to go "deep" into the graph before exploring other branches. It's like exploring a maze by following one path as far as you can before backtracking.
2.  Breadth-First Search (BFS):
    BFS explores all the neighbors of a vertex before moving to the next level. In an undirected graph, it works like this:
    •   Start at a chosen vertex.
    •   Explore all of its immediate neighbors.
    •   Then move to the next level and explore all neighbors of those vertices.
    •   Continue this process, level by level, until all vertices have been visited.
    BFS explores the graph in "waves", moving outward from the starting point in all directions equally.
The main differences between DFS and BFS in undirected graphs are:
1.  Order of exploration: DFS goes deep into one path before exploring others, while BFS explores all neighbors at the current depth before moving deeper.
2.  Implementation: DFS is typically implemented using a stack (or recursion), while BFS uses a queue.
3.  Memory usage: DFS can use less memory in some cases, especially in trees, as it only needs to store the nodes on the current path. BFS needs to store all nodes at the current level, which can be memory-intensive for wide graphs.
4.  Shortest path: In unweighted graphs, BFS guarantees finding the shortest path between two nodes, while DFS doesn't.
5.  Completeness: Both are complete, meaning they will find a solution if one exists, but BFS is often preferred when you need to find the optimal solution in unweighted graphs.
These algorithms are crucial in solving various graph problems.
8:03
For example, as mentioned in the "Advanced Data Structures and Algorithms" book (https://launchschool.com/books/advanced_dsa/read/graph_traversal_part_1), DFS can be used to detect cycles in a graph or to perform topological sorting, while BFS is often used to find the shortest path in unweighted graphs.
Remember, the choice between DFS and BFS depends on the specific problem you're trying to solve and the structure of your graph. Both have their strengths and are valuable tools in a programmer's toolkit.

### [DFS recursive exercise](https://launchschool.com/books/advanced_dsa/read/graph_traversal_part_1#dfsrecursive)

```javascript
function dfs(adjList, source) {
  let output = [];

  function recursiveNodeprocessing(node) {
    output.push(node)
    let neighbours = adjList.get(node)
    while (neighbours.length) {
      recursiveNodeprocessing(neighbours.pop());
    }
  }

  recursiveNodeprocessing(source);
  return output
}
```

- LS solution:

```javascript
function dfs(adjList, source) {
  console.log(source);
  let neighbors = adjList.get(source);
  for (let neighbor of neighbors) {
    dfs(adjList, neighbor);
  }
}
```

### [Breadth-first search](https://launchschool.com/books/advanced_dsa/read/graph_traversal_part_1#bfs)

- a common way to explore vertices level by level.

```javascript
function bfs(adjList, source) {
  let output = [source];

  function processNode(node) {
    let neighbours = adjList.get(node)
    for (i = 0; i < neighbours.length; i ++) {
      output.push(neighbours[i]);
    }
    while (neighbours.length) {
      processNode(neighbours.shift());
    }
  }

  processNode(source)
  return output;
}

// LS solution:

function bfs(adjList, source) {
  let queue = [source];

  while (queue.length !== 0) {
    let current = queue.shift();
    console.log(current);

    let neighbors = adjList.get(current);
    for (let neighbor of neighbors) {
      queue.push(neighbor);
    }
  }
}
```

## [Edge List to Adjacency List](https://launchschool.com/books/advanced_dsa/read/edge_list_to_adjacency_list)

- It's common (in graph theory) to have an edge list as input.
- A graph can be represented with an array of arrays with each subarray containing two connected nodes:

```javascript
[
  [1, 2],
  [1, 3],
  [2, 4],
  [3, 4],
  [3, 5],
  [5, 6],
];
```

```javascript
function createAdjList(edgeList) {
  const adjList = new Map();

  edgeList.forEach(([vertex1, vertex2]) => {
    if (!adjList.has(vertex1)) adjList.set(vertex1, []);
    adjList.get(vertex1).push(vertex2);

    if (!adjList.has(vertex2)) adjList.set(vertex2, []);
    adjList.get(vertex2).push(vertex1);
  });
  return adjList;
}

// Helper Function
function printAdjList(adjList) {
  console.log(
    "{\n" +
      Array.from(
        adjList,
        ([key, value]) => `  ${key}: [${value.join(", ")}]`
      ).join(",\n") +
      "\n}"
  );
}

const edgeList1 = [
  [1, 2],
  [2, 3],
  [3, 1],
];

const adjList1 = createAdjList(edgeList1);
printAdjList(adjList1);
// {
//   1: [2, 3],
//   2: [1, 3],
//   3: [2, 1]
// }

const edgeList2 = [
  [1, 2],
  [1, 3],
  [2, 4],
  [3, 4],
  [3, 5],
  [5, 6],
];

const adjList2 = createAdjList(edgeList2);
printAdjList(adjList2);
// {
//  1: [2, 3],
//  2: [1, 4],
//  3: [1, 4, 5],
//  4: [2, 3],
//  5: [3, 6],
//  6: [5]
// }
```

## [Graph Traversal Part II](https://launchschool.com/books/advanced_dsa/read/graph_traversal_part_2)

```javascript
function dfs(adjList, source, visited = new Set()) {
  console.log(source);
  visited.add(source);

  let neighbors = adjList.get(source);
  for (let neighbor of neighbors) {
    if (!visited.has(neighbor)) {
      dfs(adjList, neighbor, visited);
    }
  }
}
```

- solution with stack:

```javascript
function dfs(adjList, source) {
  let stack = [source];
  let visited = new Set();
  visited.add(source);

  while (stack.length) {
    let current = stack.shift();
    let neighbours = adjList.get(current);
    neighbours.forEach((neighbour) => {
      if (!visited.has(neighbour)) {
        stack.push(neighbour);
        visited.add(neighbour);
      }
    })
    console.log(current)
  }
}
```

- LS solution (close to mine. I should have popped, not unshifted. That's what a stack does)

```javascript
function dfs(adjList, source) {
  let stack = [source];
  let visited = new Set([source]);

  while (stack.length !== 0) {
    let current = stack.pop();
    console.log(current);

    let neighbors = adjList.get(current);
    for (let neighbor of neighbors) {
      if (!visited.has(neighbor)) {
        visited.add(neighbor);
        stack.push(neighbor);
      }
    }
  }
}
```

- BFS solution: (LS solution pretty much the same)

```javascript
function bfs(adjList, source) {
  let stack = [source];
  let visited = new Set([source])

  while (stack.length) {
    let current = stack.shift();
    console.log(current);

    let neighbours = adjList.get(current);
    neighbours.forEach((neighbour) => {
      if (!visited.has(neighbour)) {
        stack.push(neighbour);
        visited.add(neighbour);
      }
    })
  }
}
```

## [Practice: Has Path](https://launchschool.com/books/advanced_dsa/read/has_path)

```javascript
function hasPath(edgeList, src, dst) {
  let stack = [src];
  let visited = new Set([src]);

  while (stack.length) {
    if (stack.includes(dst)) { return true }
    let current = stack.shift();
    for (i = 0; i < edgeList.length; i += 1) {
      if (edgeList[i][0] === current && !visited.has(edgeList[i][1])) {
        stack.push(edgeList[i][1]);
        visited.add(edgeList[i][1]);
      } else if (edgeList[i][1] === current && !visited.has(edgeList[i][0])) {
        stack.push(edgeList[i][0]);
        visited.add(edgeList[i][0]);
      }
    }
  }
```

## [Demo: Number of Forests](https://launchschool.com/books/advanced_dsa/read/number_of_forests)


- you can achieve the same result wihtout using a set if you reassign trees to 'O's once they've been counted: `grid[row][col] = 'O';`

## [Practice: Largest Forest Area](https://launchschool.com/books/advanced_dsa/read/largest_forest_area)

- an easy tweak of the previous exercise solution.

# BACKTRACKING
## [Introduction to Backtracking](https://launchschool.com/books/advanced_dsa/read/introduction_to_backtracking)

#### [Efficiency](https://launchschool.com/books/advanced_dsa/read/introduction_to_backtracking#efficiency)

- Generally poor. Often exponential or even factorial.
- Calculating the complexities can be complicated, so it's not a focus of this section.

## [Terminology](https://launchschool.com/books/advanced_dsa/read/terminology)


- State Space: the set of all possible states in our problemn. All possible configurations we could get to when solving the problem.

- State Space Tree: Were we to draw this out as a tree

- Candidate: A potential choice we could add to our current incomplete solution.

- Solution: AKA "candidate solution" because it has all the candidates we've selected at each step.

- Dead End: self-explanatory.

- Terminal Condition: either a dead-end or because the solution has been found. Or could be something else.

- A Backtrack step: Returning to a previous step. (Obvs).

- Pruning: cutting off logic branches when we can.

### [Permutations](https://launchschool.com/books/advanced_dsa/read/terminology#permutations)

- ok

### [Optimization](https://launchschool.com/books/advanced_dsa/read/terminology#optimization)

- 

## [Problem Solving Approach](https://launchschool.com/books/advanced_dsa/read/problem_solving_approach)

### [Naive Steps](https://launchschool.com/books/advanced_dsa/read/problem_solving_approach#naivesteps)

- Step 1: Draw it out on a piece of paper.
- Step 2: Define Naive branching logic.
- Step 3: Define the Dead-end conditions.
- Step 4: define the success conditions

### [Optimization](https://launchschool.com/books/advanced_dsa/read/problem_solving_approach#optimization)


## [Template](https://launchschool.com/books/advanced_dsa/read/template)

1. Initializaton and main function call
2. success condition
3. Exploration loop
4. Dead-end condition

## [Demo: Permutations](https://launchschool.com/books/advanced_dsa/read/permutations)

- Walkthrough
- Optimization
  - Option 1: check for inclusion.
  - Option 2: filtering the collection

## [Practice: Combinations](https://launchschool.com/books/advanced_dsa/read/combinations)



# CONCLUSION
## [Conclusion & Next Steps](https://launchschool.com/books/advanced_dsa/read/conclusion_and_next_steps)

First pass complete: 18.12.24
