# Solution
```
class Solution:
    def canJump(self, nums):
        max_reach = 0
        n = len(nums)
        for i, x in enumerate(nums):
            if i > max_reach: 
                return False
            if max_reach >= n - 1: 
                return True
            
            max_reach = max(max_reach, i + x)
            
            
           
```
