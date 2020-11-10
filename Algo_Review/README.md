# Algo Review
## Description
In this file, I tried to sum up very shortly all the notions that one should keep in mind when we are dealing with algorithmics. The main material is from [geeksforgeeks](https://www.geeksforgeeks.org) and google.

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

##### O(<a href="https://www.codecogs.com/eqnedit.php?latex=n^c" target="_blank"><img src="https://latex.codecogs.com/gif.latex?n^c" title="n^c" /></a>) Complexity:













