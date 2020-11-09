# Algo Review
## Description
In this file, I tried to sum up very shortly all the notions that one should keep in mind when we are dealing with algorithmics. The main material is from [geeksforgeeks](https://www.geeksforgeeks.org) and google.

# 1. Asymptotic analysis
The purpose is being able to compare two algorithms and decide which one is better. In algorithmics, the criteria to decide so, is based on the input size which should be large, the one that takes the least time is the better. This is the performance in time rendering point of view. Note that:
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

# 1. Worst Case - Best Case - Average Case
  
  #### A) Worst Case Analysis (Usually Done) 
The worst case analysis, we calculate upper bound on running time of an algorithm. We must know the case that causes maximum number of operations to be executed. For example for the Linear Search algorithm that works as follow: in array of lenght n we look for the index for a given an element x, starting by the index 0 of the array, once we find the x we render the index and we stop iterating over the array. Otherwise, we return -1, that means that the x is not in the array. For this algorithm, the worst case scenario is when x is not in the array, we should then iterate all over the array to make sure that is the case. We can say the worst case time complexity of linear search would be Θ(n). The idea is to look for the input that is going to give this worst case.

 ##### B) Average Case Analysis (Sometimes Done)
In average case analysis, we take all possible inputs and calculate computing time for all of the inputs. Sum all the calculated values and divide the sum by total number of inputs. We must know (or predict) distribution of cases. For the Linear Search Algortihm, we can verify that the average case time complexity is Θ(n). 
