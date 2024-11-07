# [data structures and algorithms](https://launchschool.com/books/dsa)


### [Introduction](https://launchschool.com/books/dsa/read/introduction)
#### [How DSA gives you an edge](https://launchschool.com/books/dsa/read/introduction#dsagivesedge)
##### Technical interviews: many focus on DSA
    - questions will test your ability to:
      -  solve problems
      -  analyse different approaches
      -  optimize solutions for time/space complexity
    -  This course teaches strategies for nailing these.
##### Efficient Problem solving:
  - DSA provides the tools/techniques to solve coding challenges systematically/optimally
  - You will learn to
    - analyse problems
    - select appropriate data-structures
    - apply efficient algorithms
##### Building a strong foundation
  - These concepts are fundamental to computer science and software engineering.
  - These are the building blocks for more advanced topics you'll encounter as a programmer
#### [What we'll cover](https://launchschool.com/books/dsa/read/introduction#whatwellcover)
##### PEDAC
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
###### Practice for mastery
###### going deeper
- there's a 2nd book
- capstone also takes this further
###### let's get started
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
##### Code Efficiency
- selecting the most appropriate structure allows us to write more efficient code
- Each data structure has unique characteristics that make it suited for particular operations.
-  Understanding these characteristics allows us to choose the most efficient structure resulting in faster and more optimised code.

##### Algorithm design

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

##### Big O

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

- 

### Space Complexity
### Fine-tuning Time Complexity
### Time & Space Complexity Problems
### Algorithm Discovery Process
### Practice: Find a Majority Element
## SORTING ALGORITHMS
### Intro to Sorting Algorithms
### Bubble Sort
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
| L1 | start 7.11.24 |
| L2 | 
| L3 | 
| L4 | 
| L5 |
| L6 |
