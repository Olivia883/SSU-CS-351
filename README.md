# SSU-CS-351
Sonoma State Computer Architecture Class
* Project 1

## Questions:
1. Which program is fastest? Is it always the fastest?
    - Based on the trials, the alloca.cpp was the fastest in most tests because it uses stack memory, which is quicker to allocate. As the number of blocks increases, the difference in speed becomes smaller.

2. Which program is slowest? Is it always the slowest?
    - The malloc.cpp was slower because it uses heap memory, which takes more time to manage. For small data sizes, the difference may not be as big.

3. Was there a trend in program execution time based on the size of data in each Node? If so, what, and why?
  - Yes, the program takes longer when the data size in each Node increases. This happens because bigger data requires more time to process and hash.

4. Was there a trend in program execution time based on the length of the block chain?
    - Yes, the more blocks you have in the chain, the longer the program takes. This is because each block needs to be processed, and more blocks mean more work. 

5. Consider heap breaks, what's noticeable? Does increasing the stack size affect the heap?
    - The program needs more memory from the operating system as the heap grows. Increasing the stack size only affects the alloca program since it uses stack memory. The heap in malloc is not affected by stack size changes. The two programs handle memory differently: alloca is faster but more limited, while malloc can handle bigger data but with more overhead.

6. Generate a diagram showing two Nodes. Include in the diagram:
   - The relationship of the head, tail, and Node next pointers.
   - The size (in bytes) and structure of a Node that allocated six bytes of data.
   - The bytes pointer, and indicate which byte in the allocated memory it points to.

Diagram:
+-------------------+       +-------------------+
|   Node 1 (6 bytes)| ----> |   Node 2 (6 bytes)|
+-------------------+       +-------------------+
    |                          |
    v                          v
+---------+             +---------+
|  Head   |             |  Tail   |
+---------+             +---------+

7. There's an overhead to allocating memory, initializing it, and eventually processing (in our case, hashing it). For each program, were any of these tasks the same? Which one(s) were different?
   - The memory allocation part is different between the two programs. The malloc allocates memory on the heap, which takes more time. The alloca uses the stack, which is faster but has limited size. Both programs still initialize the data and hash it, but the overhead of memory allocation is higher in malloc.cpp.
    
8. As the size of data in a Node increases, does the significance of allocating the node increase or decrease?
   - As the size of data in a Node increases, the importance of allocating the node increases. Since larger data requires more memory, the time to allocate and process also increases.
