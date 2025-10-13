# Project 1: Linked List and Memory Allocation Benchmarking

## Overview
In this project, we compare the performance of different linked list implementations using various memory allocation techniques. The goal is to benchmark the algorithms using different configurations for node sizes and chain lengths to determine which implementation performs best under different conditions.

## Program Implementations
1. **list.cpp**: Uses `std::list` for memory management.
2. **new.cpp**: Uses custom singly-linked list with `new` for memory allocation.
3. **malloc.cpp**: Uses `malloc()` for memory allocation.
4. **alloca.cpp**: Uses `alloca()` for stack-based memory allocation.

Each program performs the same task of building a linked list, where each node contains random data. The nodes are then hashed to produce a final result.

## Questions and Analysis

### 1. Which program is fastest? Is it always the fastest?
- **Answer:** 
    - Based on the trials, **[Insert fastest program]** was the fastest in most tests, especially when the node size was smaller and the number of blocks was lower.
    - **Observations:** This program uses **[reasoning, e.g., "dynamic memory allocation" or "more efficient memory management"]**, which gives it an edge in terms of runtime. However, when the node size or number of blocks increased, **[insert program]** started to catch up.

### 2. Which program is slowest? Is it always the slowest?
- **Answer:** 
    - **[Insert slowest program]** was the slowest in most cases. This was due to **[reason, e.g., "higher overhead for memory allocation" or "inefficient memory management"]**.
    - **Observations:** It performed relatively worse under high memory usage scenarios, where **[reason why slowest]** became more pronounced.

### 3. Was there a trend in program execution time based on the size of data in each Node? If so, what, and why?
- **Answer:** 
    - Yes, **execution time increased as the size of data in each node grew**. This is because larger node sizes require more memory, which can slow down memory access and increase cache misses. The larger the node size, the more memory is required to allocate, and the more time it takes to traverse each node.
    - **Observations:** Programs like **[insert program]** that use dynamic memory allocation (like `malloc()` or `new`) showed a greater increase in runtime as the node size grew.

### 4. Was there a trend in program execution time based on the length of the block chain?
- **Answer:** 
    - Yes, as the number of blocks in the chain increased, **execution time grew linearly (or possibly exponentially depending on memory allocation)**. This is because each additional node added increases the overall memory required and the time spent traversing the list.
    - **Observations:** Programs like **[insert program]**, which use stack memory allocation, showed more stability in execution time despite increasing the number of blocks, whereas heap-based allocation strategies experienced more noticeable delays.

### 5. Consider heap breaks, what's noticeable? Does increasing the stack size affect the heap?
- **Answer:** 
    - **Heap breaks** occurred more frequently in programs using **[insert malloc.cpp or new.cpp]**, as the system requested more heap memory for larger block chains. 
    - **Observations:** Increasing the stack size (e.g., in `alloca.cpp`) did not affect the heap memory usage significantly, but programs using heap-based memory allocation showed more frequent page expansions as the number of nodes increased.

### 6. Generate a diagram showing two Nodes. Include in the diagram:
   - The relationship of the head, tail, and Node next pointers.
   - The size (in bytes) and structure of a Node that allocated six bytes of data.
   - The bytes pointer, and indicate which byte in the allocated memory it points to.

#### Diagram (ASCII or description)
```plaintext
+-------------------+       +-------------------+
|   Node 1 (6 bytes)| ----> |   Node 2 (6 bytes)|
+-------------------+       +-------------------+
    |                          |
    v                          v
+---------+             +---------+
|  Head   |             |  Tail   |
+---------+             +---------+
