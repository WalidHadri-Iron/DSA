# Algo Review
## Description
In this file, I tried to sum up very shortly all the notions that one should keep in mind when we are dealing with algorithmics. The main material is from [geeksforgeeks](https://www.geeksforgeeks.org).

# 1. Asymptotic analysis
The purpose is being able to compare two algorithms and decide which one is better. In algorithmics, the criteria to decide so, is based on the input size which should be large, the one that takes the least time is the better. This is the performance in time rendering point of view. Note that:
  1. It might be possible that for some inputs, first algorithm performs better than the second. And for some inputs second performs better.
  2. It might also be possible that for some inputs, first algorithm perform better on one machine and the second works better on other machine for some other inputs.
 Take the example of the two following algortihms:
            
            *Linear Search running time in seconds on A: 0.2 * n
            *Binary Search running time in seconds on B: 1000*log(n)


|n      | Running time on A | Running time on B |
|-------|-------------------|-------------------|
|10     | 2 sec             | ~ 1 h             |
|100    | 20 sec            | ~ 1.8 h           |
|10^6   | ~ 55.5 h          | ~ 5.5 h           |
|10^9   | ~ 6.3 years       | ~ 8.3 h           |

