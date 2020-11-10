

# 1. Asymptotic analysis
The purpose is being able to compare two algorithms and decide which one is better. In algorithmics, the criterion to decide so, is based on the input size which should be large, the one that takes the least time is the better. This is the performance in time rendering point of view. Note that:
  1. It might be possible that for some inputs, first algorithm performs better than the second. And for some inputs second performs better.
  2. It might also be possible that for some inputs, first algorithm perform better on one machine and the second works better on other machine for some other inputs.
 Take the example of the two following algortihms:
            
            Linear Search running time in seconds on A: 0.2 * n
            Binary Search running time in seconds on B: 1000*log(n)


|n      | Running time on A | Running time on B |
|-------|-------------------|-------------------|
|10     | 2 sec             | ~ 1 h             |
|100    | 20 sec            | ~ 1.8 h           |
|10^6   | ~ 55.5 h          | ~ 5.5 h           |
|10^9   | ~ 6.3 years       | ~ 8.3 h           |

Asymptotic Analysis is not perfect, but that’s the best way available for analyzing algorithms. For example <img src="https://latex.codecogs.com/gif.latex?20log(n)" title="20log(n)" /> and  <img src="https://latex.codecogs.com/gif.latex?log(n)" title="log(n)" /> are asymptotically same.

# 2. Worst Case - Best Case - Average Case
  
  #### A) Worst Case Analysis (Usually Done) 
The worst case analysis, we calculate upper bound on running time of an algorithm. We must know the case that causes maximum number of operations to be executed. For example for the Linear Search algorithm that works as follow: in array of lenght n we look for the index for a given an element x, starting by the index 0 of the array, once we find the x we render the index and we stop iterating over the array. Otherwise, we return -1, that means that the x is not in the array. For this algorithm, the worst case scenario is when x is not in the array, we should then iterate all over the array to make sure that is the case. We can say the worst case time complexity of linear search would be Θ(n). The idea is to look for the input that is going to give this worst case.

 ##### B) Average Case Analysis (Sometimes Done)
In average case analysis, we take all possible inputs and calculate computing time for all of the inputs. Sum all the calculated values and divide the sum by total number of inputs. We must know (or predict) distribution of cases. For the Linear Search Algorithm, we can verify that the average case time complexity is Θ(n). 

 ##### C) Best Case Analysis
 We should know the case that minimizes the number of operations. For the Linear Search Algorithm, it is when x is the first element of the array
 
 
 # 3. Asymptotic Notations
 There are a lot of asymptotic notations, I am going to talk about the three more important and used ones.
 ##### A) Θ Notation
 The theta notation bounds a functions from above and below, so it defines exact asymptotic behavior.
  
     Θ(g(n)) = {f(n): there exist positive constants c1, c2 and n0 such that 0 <= c1*g(n) <= f(n) <= c2*g(n) for all n >= n0}

 ##### B) Big O Notation
 The Big O notation defines an upper bound of an algorithm, it bounds a function only from above.

    O(g(n)) = { f(n): there exist positive constants c and n0 such that 0 <= f(n) <= c*g(n) for all n >= n0}
   
 ##### C) Ω Notation:
 The Ω notation defines a lower bound of an algorithm, it bounds a function only from below.

    Ω (g(n)) = {f(n): there exist positive constants c and n0 such that 0 <= c*g(n) <= f(n) for all n >= n0}.
 ##### D) Properties:
 Think about the possible properties for each one, reflexivity, transitivity, symmetry, multiplying by a constant, the relationship between the three notations... For more information, see [Here](https://www.geeksforgeeks.org/analysis-of-algorithms-set-3asymptotic-notations/) or Lecture 1 of the MIT introduction to Algortihms [Here](https://www.youtube.com/watch?v=JPyuH4qXLZ0)
 
 # 3. Analysis of loops
 
 ##### O(1) Complexity:
    // set of non-recursive and non-loop statements (make sure there is no function of non constant time is called)
    
 When a loop runs a **constant** number of times it is also considered to be **O(1)**
     
     // Here c is a constant   
     for (int i = 1; i <= c; i++) {  
          // some O(1) expressions
     }
 
 ##### O(n) Complexity:
 Time Complexity of a loop is considered as O(n) if the loop variables is incremented / decremented by a constant amount
 
      // Here c is a positive integer constant   
       for (int i = 1; i <= n; i += c) {  
            // some O(1) expressions
       }

       for (int i = n; i > 0; i -= c) {
            // some O(1) expressions
       }

##### O(<a href="https://www.codecogs.com/eqnedit.php?latex=\mathbf{n^c}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\mathbf{n^c}" title="\mathbf{n^c}" /></a>) Complexity:
Time complexity of nested loops is equal to the number of times the innermost statement is executed. For the exampls below, the complexity is **O(<a href="https://www.codecogs.com/eqnedit.php?latex=\mathbf{n^2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\mathbf{n^2}" title="\mathbf{n^2}" /></a>)**
       
       for (int i = 1; i <=n; i += c) {
         for (int j = 1; j <=n; j += c) {
            // some O(1) expressions
         }
       }

     
       for (int i = n; i > 0; i -= c) {
         for (int j = i+1; j <=n; j += c) {
            // some O(1) expressions
         }
       }

 ##### O(Log(n)) Complexity:
  Time Complexity of a loop is considered as O(Logn) if the loop variables is divided / multiplied by a constant amount.
  
       for (int i = 1; i <=n; i *= c) {
           // some O(1) expressions
       }
       for (int i = n; i > 0; i /= c) {
           // some O(1) expressions
       }


 ##### O(LogLog(n)) Complexity:
Time Complexity of a loop is considered as O(LogLogn) if the loop variables is reduced / increased exponentially by a constant amount.

    // Here c is a constant greater than 1   
       for (int i = 2; i <=n; i = pow(i, c)) { 
           // some O(1) expressions
       }
       //Here fun is sqrt or cuberoot or any other constant root
       for (int i = n; i > 1; i = fun(i)) { 
           // some O(1) expressions
       }
*Proof*: i takes the following values: 2, <a href="https://www.codecogs.com/eqnedit.php?latex=2^c" target="_blank"><img src="https://latex.codecogs.com/gif.latex?2^c" title="2^c" /></a>, <a href="https://www.codecogs.com/eqnedit.php?latex=(2^c)^c" target="_blank"><img src="https://latex.codecogs.com/gif.latex?(2^c)^c" title="(2^c)^c" /></a>, <a href="https://www.codecogs.com/eqnedit.php?latex=((2^c)^c)^c" target="_blank"><img src="https://latex.codecogs.com/gif.latex?((2^c)^c)^c" title="((2^c)^c)^c" /></a>, ..... <a href="https://www.codecogs.com/eqnedit.php?latex=2^{c^{log_{c}(log(n))}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?2^{c^{log_{c}(log(n))}}" title="2^{c^{log_{c}(log(n))}}" /></a> . The last termn is equal to n, gives that the number of iterations is **O(Log(Log(n))**
##### Consecutive loops:
With consecutive loops, the time complexity ais calculated s sum of time complexities of individual loops.
##### If and else statements inside loops:
 We calculate the complexity for the worst case
 
 # 3. Analysis of recursive functions
 For recusrsive functions, the time complexity can be written in mathematical recurrence relation. We have to be able to solve the recusrsion to find the complexity. There are some techniques to do that:
 ##### Substitution Method:
 We make a guess for the solution and then we use mathematical induction to prove the guess is correct or incorrect.
 
      For example consider the recurrence T(n) = 2T(n/2) + n

      We guess the solution as T(n) = O(nLogn). Now we use induction
      to prove our guess.

      We need to prove that T(n) <= cnLogn. We can assume that it is true
      for values smaller than n.

      T(n) = 2T(n/2) + n
          <= 2cn/2Log(n/2) + n
          =  cnLogn - cnLog2 + n
          =  cnLogn - cn + n
          <= cnLogn

##### Recurrence Tree Method:
 In this method, we draw a recurrence tree and calculate the time taken by every level of tree. Finally, we sum the work done at all levels. To draw the recurrence tree, we start from the given recurrence and keep drawing till we find a pattern among levels. The pattern is typically a arithmetic or geometric series.
 
       For example consider the recurrence relation 
      T(n) = T(n/4) + T(n/2) + cn2

                 cn2
               /      \
           T(n/4)     T(n/2)

      If we further break down the expression T(n/4) and T(n/2), 
      we get following recursion tree.

                      cn2
                 /           \      
             c(n^2)/16      c(n^2)/4
            /      \          /     \
        T(n/16)     T(n/8)  T(n/8)    T(n/4) 
      Breaking down further gives us following
                       cn^2
                  /            \      
             c(n^2)/16          c(n^2)/4
             /      \            /      \
      c(n^2)/256   c(n^2)/64  c(n^2)/64    c(n^2)/16
       /    \      /    \    /    \       /    \  

      To know the value of T(n), we need to calculate sum of tree 
      nodes level by level. If we sum the above tree level by level, 
      we get the following series
      T(n)  = c(n^2 + 5(n^2)/16 + 25(n^2)/256) + ....
      The above series is geometrical progression with ratio 5/16.

      To get an upper bound, we can sum the infinite series. 
      We get the sum as (n^2)/(1 - 5/16) which is O(n^2)
 

 #####  Master Method
 It works only for recurrences that can be written in the following format:
            
            T(n) = aT(n/b) + f(n) where a >= 1 and b > 1, a,b constants
            
   ![alt text](https://github.com/WalidHadri-Iron/DSA/blob/main/Algo_Review/images/MasterTheorem.png?raw=true)
 
For practicing, see this [document](https://www.csd.uwo.ca/~mmorenom/CS424/Ressources/master.pdf)

If interested in proof, check [here](https://www.cs.cornell.edu/courses/cs3110/2012sp/lectures/lec20-master/mm-proof.pdf) .

![alt text](https://github.com/WalidHadri-Iron/DSA/blob/main/Algo_Review/images/treeproof.png?raw=true)

We can say that, for this tree, we have a height of <a href="https://www.codecogs.com/eqnedit.php?latex=\boldsymbol{log_&space;{b}(n)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\boldsymbol{log_&space;{b}(n)}" title="\boldsymbol{log_ {b}(n)}" /></a> , and a branching factor of **a**. The work done at the root is **f(n)** and the work done at the leaves is <a href="https://www.codecogs.com/eqnedit.php?latex=\boldsymbol{\Theta&space;(n^c)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\boldsymbol{\Theta&space;(n^c)}" title="\boldsymbol{\Theta (n^c)}" /></a> where <a href="https://www.codecogs.com/eqnedit.php?latex=\boldsymbol{c=log_{b}(a)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\boldsymbol{c=log_{b}(a)}" title="\boldsymbol{c=log_{b}(a)}" /></a>

*Case 1: the work done at leaves is polynomially more, then leaves are the dominant part, and our result becomes the work done at leaves
*Case 2: the work done at leaves and root is asymptotically same, then our result becomes height multiplied by work done at any level. 
*Case 3: the work done at root is asymptotically more, then our result becomes work done at root.
 
 # 4. Short insight on Amortized analysis
 The motivation for amortized analysis is that looking at the worst-case run time per operation, rather than per algorithm, can be too pessimistic. See [here](https://en.wikipedia.org/wiki/Amortized_analysis) for more details. The example about dynamic arrays shows why we use amortized analysis.
 
 # 5. Space Complexity
 First of all, we are going to define precisely two terms that most of the time misused and confused.
 
     . Auxiliary Space is the extra space or temporary space used by an algorithm.

     . Space Complexity of an algorithm is total space taken by the algorithm with respect to the input size. Space complexity includes both Auxiliary space and space used by input.
 
 For example, if we want to compare standard sorting algorithms on the basis of space, then Auxiliary Space would be a better criteria than Space Complexity. Merge Sort uses O(n) auxiliary space, Insertion sort and Heap Sort use O(1) auxiliary space. Space complexity of all these sorting algorithms is O(n) though.
 
 
 # 6. Pseudo-polynomial Algorithms and NP-Completeness
 
##### A) Pseudo-polynomial Algorithms
 An algorithm whose worst case time complexity depends on **numeric value of input** (not number of inputs) is called **Pseudo-polynomial algorithm**. Of course,  polynomial time algorithms are pseudo-polynomial.
 
 *Example*: Consider the problem of counting frequencies of all elements in an array of positive numbers. A pseudo-polynomial time solution for this is to first find the maximum value, then iterate from 1 to maximum value and for each value, find its frequency in array. This solution requires time according to maximum value in input array, therefore pseudo-polynomial. On the other hand, an algorithm whose time complexity is only based on number of elements in array (not value) is considered as polynomial time algorithm.
 *More examples*: Primality testing, Knapsack problem.
 
##### B) P and NP problems
 Let start by reminding that:
 
    . P is set of problems that can be solved by a deterministic Turing machine in Polynomial time.
    . NP  is set of decision problems that can be solved by a Non-deterministic Turing Machine in Polynomial time. P is subset of NP (any problem that can be solved by deterministic machine in polynomial time can also be solved by non-deterministic machine in polynomial time).
    The Turing machine consists of two phases, the first of which consists of a guess about the solution, which is generated in a non-deterministic way, while the second phase consists of a deterministic algorithm that verifies if the guess is a solution to the problem.
    
To sump up:  
         
         . P (all problems solvable, deterministically, in polynomial time) 
         . NP (problems where solutions can be verified in polynomial time)
         . P ⊂ NP
 We can identify a decision problem with the subset of inputs that have answer YES. This simplifies notation and allows us to write x∈Q in place of Q(x)=YES and x∉Q in place of Q(x)=NO.
 
 **P** is the class of decision problems that can be solved efficiently, i.e. decision problems which have polynomial-time algorithms.

More formally, we say a decision problem Q is in P iff:

      there is an efficient algorithm A such that for all inputs x
            
            if Q(x)=YES, then A(x)=YES
           
            if Q(x)=NO, then A(x)=NO.
 
 NP: Problems with Efficient Algorithms for Verifying Proofs/Certificates/Witnesses 
 
 Sometimes we do not know any efficient way of finding the answer to a decision problem, however if someone tells us the answer and gives us a proof we can efficiently verify that the answer is correct by checking the proof to see if it is a valid proof. This is the idea behind the complexity class NP.

    Partition
    
    Input: a finite set of natural numbers S,
    
    Question: is it possible to partition S into two sets A and B (A∪B=S and A∩B=∅)
    
    such that the sum of the numbers in A is equal to the sum of number in B (∑x∈Ax=∑x∈Bx)?

If I give you S and ask you if we can partition it into two sets such that their sums are equal, you do not know any efficient algorithm to solve it. You will probably try all possible ways of partitioning the numbers into two sets until you find a partition where the sums are equal or until you have tried all possible partitions and none has worked. If any of them worked you would say YES, otherwise you would say NO. 

But there are exponentially many possible partitions so it will take a lot of time. However if I give you two sets A and B, you can easily check if the sums are equal and if A and B is a partition of S. Note that we can compute sums efficiently. 

**NP** is the class of problems which have efficient verifiers, i.e. there is a polynomial time algorithm that can verify if a given solution is correct. 

More formally, we say a decision problem Q is in NP iff
 
     there is an efficient algorithm V called verifier such that for all inputs x
     
     if Q(x)=YES then there is a proof y such that V(x,y)=YES
     
     if Q(x)=NO then for all proofs y, V(x,y)=NO.
 
 
 For more details, check this [discussion](https://cs.stackexchange.com/questions/9556/what-is-the-definition-of-p-np-np-complete-and-np-hard/9566#9566)
 
 ##### C) NP-Complete and NP-Hard:
NP-complete problems are the hardest problems in NP set. A decision problem L is NP-complete if:
    
    1) L is in NP (Any given solution for NP-complete problems can be verified quickly, but there is no efficient known solution).
    2) Every problem in NP is reducible to L in polynomial time (Reduction is defined below).
 
A problem is NP-Hard if it follows property 2 mentioned above, doesn’t need to follow property 1. Therefore, NP-Complete set is also a subset of NP-Hard set.
 
 ![alt text](https://github.com/WalidHadri-Iron/DSA/blob/main/Algo_Review/images/NP-Completeness-1.png?raw=true)
 
 
 ##### C) Reduction:
 
 Let L1 and L2 be two decision problems. Suppose algorithm A2 solves L2. That is, if y is an input for L2 then algorithm A2 will answer Yes or No depending upon whether y belongs to L2 or not.
The idea is to find a transformation from L1 to L2 so that the algorithm A2 can be part of an algorithm A1 to solve L1.
 
 ![alt text](https://github.com/WalidHadri-Iron/DSA/blob/main/Algo_Review/images/Reduction.png?raw=true)
 
 
 ##### C) Proving that a problem is NP-complete: 
 From the definition of NP-complete, it appears impossible to prove that a problem L is NP-Complete.  By definition, it requires us to that show every problem in NP is polynomial time reducible to L.   Fortunately, there is an alternate way to prove it.   The idea is to take a known NP-Complete problem and reduce it to L.  If polynomial time reduction is possible, we can prove that L is NP-Complete by transitivity of reduction (If a NP-Complete problem is reducible to L in polynomial time, then all problems are reducible to L in polynomial time).
 
 
##### D) Some NP-Complete porblems:

* Boolean satisfiability problem (SAT)
* Knapsack problem
* Hamiltonian path problem
* Travelling salesman problem (decision version)
* Vertex cover problem
* Subset sum problem
 
 
 
 
 
 
 
 
 
 
 
 
 
 
