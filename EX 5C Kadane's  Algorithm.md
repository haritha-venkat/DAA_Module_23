# EX 5C Kadane's Algorithm
## DATE:

## AIM:
To write a python program to find the maximum contiguous subarray.


## Algorithm

1. Initialize `max_so_far = a[0]` and `max_ending_here = 0`.
2. Loop through each element of the array.
3. Add current element to `max_ending_here`.
4. Update `max_so_far` if `max_ending_here` is greater.
5. If `max_ending_here` becomes negative, reset it to 0.


## Program:
```
/*
To implement the program to find the maximum contiguous subarray.


Developed by: haritha shree
Register Number:  212222230046
*/
def maxSubArraySum(a, size):
    max_so_far = a[0]
    max_ending_here = 0
 
    for i in range(0, size):
        max_ending_here = max_ending_here + a[i]
        if (max_so_far < max_ending_here):
            max_so_far = max_ending_here
 
        if max_ending_here < 0:
            max_ending_here = 0
    return max_so_far

n = int(input())
a = []
for i in range(n):
    a.append(int(input()))
print("Maximum contiguous sum is", maxSubArraySum(a, n))

```

## Output:

![Screenshot 2025-05-16 183742](https://github.com/user-attachments/assets/e5429f30-ed80-459a-beaf-1c5de1985a23)


## Result:
Thus the program was executed successfully for finding the maximum contiguous sum of subarray..
