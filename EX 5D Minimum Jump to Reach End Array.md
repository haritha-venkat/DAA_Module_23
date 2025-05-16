# EX 5D Minimum Jump to Reach End Array
## DATE:

## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.


## Algorithm

1. Initialize a `jumps[]` array with `0` at start and `inf` for other positions.
2. If array length is 0 or first element is 0, return `inf` (can't proceed).
3. For each index `i` from 1 to `n-1`, set `jumps[i] = inf` initially.
4. For each `j < i`, check if `i <= j + arr[j]` and update `jumps[i]`.
5. Return `jumps[n-1]` as the minimum jumps to reach the end.
   

## Program:
```
/*
To implement the program to finding the minimum number of jumps needed to reach end of the array.


Developed by: haritha shree
Register Number:  212222230046
*/
def minJumps(arr, n):
    ##########  Add your code here ##############
    jumps = [0 for i in range(n)]
 
    if (n == 0) or (arr[0] == 0):
        return float('inf')
 
    jumps[0] = 0
    for i in range(1, n):
        jumps[i] = float('inf')
        for j in range(i):
            if (i <= j + arr[j]) and (jumps[j] != float('inf')):
                jumps[i] = min(jumps[i], jumps[j] + 1)
                break
    return jumps[n-1]
arr = []
n = int(input()) #len(arr)
for i in range(n):
    arr.append(int(input()))
print('Minimum number of jumps to reach','end is', minJumps(arr,n))
 
```

## Output:

![Screenshot 2025-05-16 183920](https://github.com/user-attachments/assets/72b1b11a-75bf-4b95-ac12-ed3bb522ee50)


## Result:
Thus the program was executed successfully for finding the minimum number of jumps to reach end.
