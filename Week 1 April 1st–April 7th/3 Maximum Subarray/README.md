# Solution
```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        current = maxx = nums[0]
        for i in nums[1:]:
            current = max(i, current + i)
            maxx = max(maxx, current)

        return maxx
```
