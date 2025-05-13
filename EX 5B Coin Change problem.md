# EX 5B Coin Change Problem
## DATE:
## AIM:
To compute the fewest number of coins that we need to make up the amount given.


## Algorithm
1. If amount is 0, answer is 0; if coins are too big, answer is -1.
2. Make a list dp to remember the fewest coins needed for each amount.
3. Set 1 coin for amounts equal to the coin values.
4. For bigger amounts, check if using a coin gives fewer coins, and update.
5. At the end, return the answer from dp[amount]   

## Program:
```
Developed by: VINISH RAJ R
Register Number: 212223230243

class Solution(object):
    def coinChange(self, coins, amount):
        if amount == 0 :
            return 0
        if min(coins) > amount:
            return -1
        dp = [-1 for i in range(0, amount + 1)]
        for i in coins:
            if i > len(dp) - 1:
                continue
            dp[i] = 1
            for j in range(i + 1, amount + 1):
                if dp[j - i] == -1:
                    continue
                elif dp[j] == -1:
                    dp[j] = dp[j - i] + 1
                else:
                    dp[j] = min(dp[j], dp[j - i] + 1)
        return dp[amount]
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))
print(ob1.coinChange(s,amt))
```

## Output:
![image](https://github.com/user-attachments/assets/395499e4-9ba3-484d-aaab-1b4dee65953d)



## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
