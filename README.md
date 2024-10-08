Q1) What is garbage collection in the context of Python, and why is it important? Can you explain how memory management is handled in Python?

Garbage collection in Python entails the automatic management of memory to ensure that applications run smoothly by freeing up memory that is not in use. Garbage collection helps in :
Preventing Memory Leaks: By automatically cleaning up unused objects, garbage collection reduces the risk of memory leaks, where memory that is no longer needed is not released.
Optimizing Performance: By freeing up memory, garbage collection helps maintain the performance of your application, especially in long-running programs or those that handle large amount of data.
Simplifying Development: Since Python handles memory management automatically, developers can focus on writing code rather than managing memory.
 Python primarily uses reference counting and a cyclic garbage collector to handle memory management.

Reference Counting: Each object in Python has a reference count, which tracks how many references point to the object. When this count drops to zero (i.e., no variables or data structures reference the object anymore), Python automatically deallocates the memory for that object.

Cyclic Garbage Collector: Reference counting alone cannot handle reference cycles (when objects reference each other). Python’s cyclic garbage collector detects and breaks reference cycles to free up memory, which makes memory management more robust.



Q2) What are the key differences between NumPy arrays and Python lists, and can you explain the advantages of using NumPy arrays in numerical computations?


Homogeneous vs. Heterogeneous: NumPy arrays are homogeneous, meaning all elements must be of the same type (usually numerical types like floats or integers), whereas Python lists can hold elements of different types (e.g., strings, integers, objects).

Memory Efficiency: NumPy arrays are more memory-efficient because they store data in contiguous blocks of memory, whereas Python lists are dynamic arrays with more overhead for each element due to pointers and type information.

Performance: NumPy arrays provide better performance for numerical computations because they leverage optimized C code under the hood, allowing for vectorized operations. Operations on NumPy arrays are usually faster than equivalent operations on Python lists.

Broadcasting: NumPy supports broadcasting, which allows operations between arrays of different shapes in a way that’s mathematically logical. Python lists don’t support this concept natively.

Advantages of using NumPy arrays in computation is that they provide optimized functions for matrix operations, linear algebra, and element-wise operations, making them significantly faster and more suitable for large-scale numerical computations.


Q3) How does list comprehension work in Python, and can you provide an example of using it to generate a list of squared values or filter a list based on a condition?

List comprehension provides a concise way to create lists. It allows for more readable and efficient code by combining the creation of a list with a loop and, optionally, a condition.

For example, Generating a list of squared values includes:
squares = [x**2 for x in range(10)]
print(squares)  The Output will be: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

Flitering a lsit based on a condition includes:
even_squares = [x**2 for x in range(10) if x % 2 == 0]
print(even_squares)  Output will be: [0, 4, 16, 36, 64]



Q4)Can you explain the concepts of shallow and deep copying in Python, including when each is appropriate, and how deep copying is implemented?
Q5)Explain with examples the difference between list and tuples. 

Mutability: The primary difference between lists and tuples is that lists are mutable, meaning their contents can be changed (elements can be added, removed, or modified), while tuples are immutable, meaning once they are created, their contents cannot be altered.

Performance: Tuples are generally faster than lists due to their immutability and the fact that they use less memory, making them ideal for fixed collections of items.

Use Cases: Lists are used when you need a collection of items that can change over time. Tuples are preferred when you want to ensure the data remains constant.

Example:

my_list = [1, 2, 3]
my_list[0] = 99   Modifying the first element
print(my_list)  Output: [99, 2, 3]

In tuple, if we try the above example, an error will occur since they cannot be changed.