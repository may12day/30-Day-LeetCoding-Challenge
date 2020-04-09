# Solution
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        res=0
        for i in range(len(prices)-1):
            p = prices[i+1]-prices[i]
            if p > 0:
                res += p
        return res
```
