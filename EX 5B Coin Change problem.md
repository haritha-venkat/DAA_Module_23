# EX 5B Coin Change Problem
## DATE:

## AIM:
To compute the fewest number of coins that we need to make up the amount given.


## Algorithm

1. Initialize `dp` array of size `amount + 1` with `inf`, and set `dp[0] = 0`.
2. For each coin in `coins`, iterate through amounts from `coin` to `amount`.
3. Update `dp[i] = min(dp[i], dp[i - coin] + 1)` for each amount `i`.
4. After filling, check if `dp[amount]` is still `inf` (not possible to form amount).
5. Return `dp[amount]` if reachable, else return `-1`.

## Program:
```
/*
Create a python function to compute the fewest number of coins that we need to make up the amount given.

.
Developed by: haritha shree
Register Number:  212222230046
*/
class Solution(object):
   def coinChange(self, coins, amount):
      ####################      Add your Code Here ###########
       dp = [float('inf')] * (amount + 1)
       dp[0]=0
       for coin in coins:
           for i in range(coin, amount + 1):
               dp[i] = min(dp[i], dp[i - coin] + 1)
       return dp[amount] if dp[amount]!=float('inf') else -1
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))


print(ob1.coinChange(s,amt))
```

## Output:

![Screenshot 2025-05-16 183549](https://github.com/user-attachments/assets/20c130c0-6c7b-4b7b-a8a4-71edca2636f2)


## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
