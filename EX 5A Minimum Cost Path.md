# EX 5A Minimum Cost Path
## DATE:

## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.

## Algorithm
Here’s the **algorithm for Minimum Cost Path** in **5 single-line steps**:

1. Initialize a 2D table `tc` of size `R x C` and set `tc[0][0] = cost[0][0]`.
2. Fill the first column with cumulative sums: `tc[i][0] = tc[i-1][0] + cost[i][0]`.
3. Fill the first row with cumulative sums: `tc[0][j] = tc[0][j-1] + cost[0][j]`.
4. For each cell `(i, j)`, compute `tc[i][j] = cost[i][j] + min(tc[i-1][j-1], tc[i-1][j], tc[i][j-1])`.
5. Return `tc[m][n]` as the minimum cost to reach cell `(m, n)`.
  

## Program:
```
/*
A program to implement to find the Minimum Cost Path Problem using a  Naive recursive Approach.

Developed by: haritha shree
Register Number:  212222230046
*/
R = int(input())
C = int(input())
def minCost(cost, m, n):
 
    tc = [[0 for x in range(C)] for x in range(R)]
    tc[0][0] = cost[0][0]
    for i in range(1, m+1):
        tc[i][0] = tc[i-1][0] + cost[i][0]
    for j in range(1, n+1):
        tc[0][j] = tc[0][j-1] + cost[0][j]
    for i in range(1, m+1):
        for j in range(1, n+1):
            tc[i][j] = min(tc[i-1][j-1], tc[i-1][j], tc[i][j-1]) + cost[i][j]
    return tc[m][n]
 
# Driver program to test above functions
cost = [[1, 2, 3],
        [4, 8, 2],
        [1, 5, 3]]
print(minCost(cost, 2, 2))
```

## Output:
![Screenshot 2025-05-16 183331](https://github.com/user-attachments/assets/8c06f594-d400-4cd3-aba1-212d5e2d9000)



## Result:
Thus the above program was executed successfully for finding the minimum cost.
