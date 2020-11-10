# Algo Review
## Description
In this file, I tried to sum up very shortly all the notions that one should keep in mind when we are dealing with algorithmics. The main material is from [geeksforgeeks](https://www.geeksforgeeks.org) and Google.

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
 

 
 
 
 
 
 
 
 
