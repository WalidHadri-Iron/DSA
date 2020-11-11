
# Data Stuctures

# Arrays

##### A) Definition of an array:
each identified by at least one array index or key. An array is stored such that the position of each element can be computed from its index tuple by a mathematical formula.The simplest type of data structure is a linear array, also called one-dimensional array.

*For example*: an array of 10 32-bit (4-byte) integer variables, with indices 0 through 9, may be stored as 10 words at memory addresses 2000, 2004, 2008, ..., 2036, so that the element with index i has the address 2000 + (i × 4).

##### B) Array’s size:
In C language array has the fixed size meaning once size is given to it. It can’t change i.e. can’t shrink it, can’t expand it. The reason was that for expanding if we change the size we can’t be sure ( it’s not possible every time) that we get the next memory location to us as free. The shrinking will not work because array, when declared, it gets memory statically, and thus compiler is the only one to destroy it.

##### C) Advantages of using arrays:
* Arrays allow random access of elements. This makes accessing elements by position faster.
* Arrays have better cache locality that can make a pretty big difference in performance.

##### D) Arrays in Python:
Other than some generic containers like **list**, Python in its definition can also handle containers with specified data types. The array can be handled in python by a module named **“array“**. They can be useful when we have to manipulate only a specific data type values. See the jupyter notebook on DataStructures where it is shown how to deal with array on python with some applications programs **HERE**.

# Linked Lists:


##### A) Definition of a linked list:

Linked list is a linear collection of data elements whose order is not given by their physical placement in memory. Instead, each element points to the next. It is a data structure consisting of a collection of nodes which together represent a sequence. In its most basic form, each node contains: data, and a reference (in other words, a link) to the next node in the sequence. This structure allows for efficient insertion or removal of elements from any position in the sequence during iteration. **Like arrays, Linked List is a linear data structure. Unlike arrays, linked list elements are not stored at a contiguous location; the elements are linked using pointers**.

![alt text](https://github.com/WalidHadri-Iron/DSA/blob/main/Algo_Review/images/linkedlists.png)

##### B) Why linked lists:
Arrays can be used to store linear data of similar types, but arrays have the following limitations.

1) The size of the arrays is fixed: So we must know the upper limit on the number of elements in advance. Also, generally, the allocated memory is equal to the upper limit irrespective of the usage.
2) Inserting a new element in an array of elements is expensive because the room has to be created for the new elements and to create room existing elements have to be shifted. 
