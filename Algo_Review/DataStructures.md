
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

**Important**:
The complexity time to reach an element at a given index (and write there) is O(1)

The complexity time to insert an element at a given index is O(n).

The memory usage of an array is exactly the number of elements in the array.


| Method 	| Worst-case time |
|-----------|------------------|
| add(int i, E element)| 	n - i|
|remove(int i)| 	n - i|
|removeRange(int i, int j)| 	n - i|
|remove(Object o) 	|n|
|contains(Object o) 	|n|
|indexOf(Object o) 	|n|
|lastIndexOf(Object o) 	|n|

# Linked Lists


##### A) Definition of a linked list:

Linked list is a linear collection of data elements whose order is not given by their physical placement in memory. Instead, each element points to the next. It is a data structure consisting of a collection of nodes which together represent a sequence. In its most basic form, each node contains: data, and a reference (in other words, a link) to the next node in the sequence. This structure allows for efficient insertion or removal of elements from any position in the sequence during iteration. **Like arrays, Linked List is a linear data structure. Unlike arrays, linked list elements are not stored at a contiguous location; the elements are linked using pointers**.

![alt text](https://github.com/WalidHadri-Iron/DSA/blob/main/Algo_Review/images/linkedlists.png)

##### B) Why linked lists:
Arrays can be used to store linear data of similar types, but arrays have the following limitations.

1) The size of the arrays is fixed: So we must know the upper limit on the number of elements in advance. Also, generally, the allocated memory is equal to the upper limit irrespective of the usage.
2) Inserting a new element in an array of elements is expensive because the room has to be created for the new elements and to create room existing elements have to be shifted. 

For example, in a system, if we maintain a sorted list of IDs in an array id[], id[] = [1000, 1010, 1050, 2000, 2040]. And if we want to insert a new ID 1005, then to maintain the sorted order, we have to move all the elements after 1000 (excluding 1000).

Deletion is also expensive with arrays until unless some special techniques are used. For example, to delete 1010 in id[], everything after 1010 has to be moved. 

**Advantages over arrays**
    
    1) Dynamic size
    2) Ease of insertion/deletion
**Drawbacks:**
    
    1) Random access is not allowed. We have to access elements sequentially starting from the first node. So we cannot do binary search with linked lists efficiently with its default implementation. Read about it here.
    2) Extra memory space for a pointer is required with each element of the list.
    3) Not cache friendly. Since array elements are contiguous locations, there is locality of reference which is not there in case of linked lists.

**Representation**:
A linked list is represented by a pointer to the first node of the linked list. The first node is called the head. If the linked list is empty, then the value of the head is NULL.
Each node in a list consists of at least two parts:
1) Data
2) Pointer (Or Reference) to the next node

See the jupyter notebook **HERE** for an idea about the construction of a linked list using OOP.

|       Array                                                 |    Linked List                                                             |
|-------------------------------------------------------------|----------------------------------------------------------------------------|
| An array is the data structure that contains a collection of similar type data elements |     Linked list is considered as a non-primitive data structure contains a collection of unordered linked elements known as nodes                                                             |
| In the array the elements belong to indexes, i.e., if you want to get into the fourth element you have to write the variable name with its index or location within the square bracket|For the linked list you have to start from the head and work your way through until you get to the fourth element|
| Accessing an element in an array is fast| Linked list takes linear time, so it is quite a bit slower|
| Operations like insertion and deletion in arrays consume a lot of time|The performance of these operations in Linked lists are fast. |
| Arrays are of fixed size | Linked lists are dynamic and flexible and can expand and contract its size |
| Memory is assigned during compile time | Memory is allocated during execution or runtime |
| Elements are stored consecutively in arrays | They are stored randomly in Linked lists |
| The requirement of memory is less due to actual data being stored within the index in the array | There is a need for more memory in Linked Lists due to storage of additional next and previous referencing elements|
| In addition memory utilization is inefficient in the array | Memory utilization is efficient in the linked list |

 
|       |Worst case|Average Case|
|-------|----------|------------|
|Search |O(n)|O(n)|
|Insert |O(1)|O(1)|
|Delection|O(1)|O(1)

 # Stack
 
 #### A) Stack definition:
 
 A stack is a basic data structure that can be logically thought of as a linear structure represented by a real physical stack or pile, a structure where insertion and deletion of items takes place at one end called top of the stack. The basic concept can be illustrated by thinking of your data set as a stack of plates or books where you can only take the top item off the stack in order to remove things from it. This structure is used all throughout programming. 


![alt text](https://github.com/WalidHadri-Iron/DSA/blob/main/Algo_Review/images/stack.png)

When we are dealing with a stack, there are four operations that one can do, all with O(1) time complexity:

* **Push**: Adds an item in the stack. If the stack is full, then it is said to be an Overflow condition.
* **Pop**: Removes an item from the stack. The items are popped in the reversed order in which they are pushed. If the stack is empty, then it is said to be an Underflow condition.
* **Peek** or **Top**: Returns top element of stack.
* **isEmpty**: Returns true if stack is empty, else false.

#### B) Stack in Python:
Stacks in Python can be implemented using:

       Lists: The biggest issue is that it can run into speed issue as it grows. The items in list are stored next to each other in memory, if the stack grows bigger than the block of memory that currently hold it, then Python needs to do some memory allocations. This can lead to some append() calls taking much longer than other ones.
       
       Deque class from the collections module: Deque is preferred over list in the cases where we need quicker append and pop operations from both the ends of the container, as deque provides an O(1) time complexity for append and pop operations as compared to list which provides O(n) time complexity. 
       
       Queue module also has a LIFO Queue, which is basically a Stack. Data is inserted into Queue using put() function and get() takes data out from the Queue.
       
       Implementation using singly linked list (OOP), the linked list has two methods addHead(item) and removeHead() that run in constant time. These two methods are suitable to implement a stack.
       
To check the four implementations, check the jupyter notebook **HERE**


 # Queue
 
 #### A) Queue definition:
 
 A queue is a collection of entities that are maintained in a sequence and can be modified by the addition of entities at one end of the sequence and the removal of entities from the other end of the sequence.
 
 ![alt text](https://github.com/WalidHadri-Iron/DSA/blob/main/Algo_Review/images/queue.png)
 
 
 

The main operations that can be executed on a queue are:

* **Enqueue**: Adds an item to the queue. If the queue is full, then it is said to be an Overflow condition.
*  **Dequeue**: Removes an item from the queue. The items are popped in the same order in which they are pushed. If the queue is empty, then it is said to be an Underflow condition.
*    **Front**: Get the front item from queue.
*    **Rear**: Get the last item from queue. 
 
 
 #### B) Queue in Python:
 
 Queues in Python can be implemented using:
 
        Using lists: List is a Python’s built-in data structure that can be used as a queue. Instead of enqueue() and dequeue(), append() and pop() function is used. However, lists are quite slow for this purpose because inserting or deleting an element at the beginning requires shifting all of the other elements by one, requiring O(n) time.
        
        Using deque: Queue in Python can be implemented using deque class from the collections module. Deque is preferred over list in the cases where we need quicker append and pop operations from both the ends of container, as deque provides an O(1) time complexity for append and pop operations as compared to list which provides O(n) time complexity. Instead of enqueue and deque, append() and popleft() functions are used.
 
        Implementation using queue.Queue
 
 
 
 #  Binary Tree
  
  Check this reminder on trees [here](https://www.programiz.com/dsa/trees). [Here] a reminder on the notions; height, depth, level...
  
 #### A) Binary Tree definition:
A tree whose elements have at most 2 children is called a binary tree. Since each element in a binary tree can have only 2 children, we typically name them the left and right child.

Unlike Arrays, Linked Lists, Stack and queues, which are linear data structures, trees are hierarchical data structures.

**Properties**:

    The maximum number of nodes at level l of a binary tree is 2^l
    The maximum number of nodes for a binary a tree tree with heigh h is 2^h - 1
    In a binary tree with N nodes, minimum possible height or the minimum number of levels is: Log2(N+1)
    A Binary Tree with L leaves has at least? Log2(L) + 1   levels 
    
 ![alt text](https://github.com/WalidHadri-Iron/DSA/blob/main/Algo_Review/images/binarytree.png)
 
 **Important definitions**:
 
The depth and the height are properties of a node:

    The depth of a node is the number of edges from the node to the tree's root node. A root node will have a depth of 0.

    The height of a node is the number of edges on the longest path from the node to a leaf. A leaf node will have a height of 0.

Properties of a tree:

    The height of a tree would be the height of its root node, or equivalently, the depth of its deepest node.

    The diameter (or width) of a tree is the number of nodes on the longest path between any two leaf nodes. The tree below has a diameter of 6 nodes.

 
 Types of binary trees: Full Binary Tree, Complete Binary Tree, Perfect Binary Tree, Balanced Binary Tree, Degenerate tree.
 
  #### B) Traversals (DFS VS BFS):
 BFS (Breath First Traversal or level order traversal)
 
 DFS (Depth First Traversal) has three different types:
 
        Inorder Traversal (Left-Root-Right)
        Preorder Traversal (Root-Left-Right)
        Postorder Traversal (Left-Right-Root)

Example Tree
 There is no difference in time complexity, both have to visit all nodes. In space complexity, for DFS the complexity is h (where h is the height of the binary tree) and for BFS is w (where w is the maximum width of Binary tree).
 
 Keep in mind that: 
 
        Depth First Traversals are typically recursive and recursive code requires function call overheads.
        
        The most important points is, BFS starts visiting nodes from root while DFS starts visiting nodes from leaves. So if our problem is to search something that is more likely closer to root, we would prefer BFS. And if the target node is close to a leaf, we would prefer DFS. 
 
 
 
 
 
 
 
 
 
 
 
 
