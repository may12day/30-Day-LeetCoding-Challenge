# Solution
```
class Solution:
    def search(self, nums, target):
        if not nums:
            return -1
        return self.binarySearch(nums, target, 0, len(nums)-1)

    def binarySearch(self, nums, target, start, end):
        if end < start:
            return -1
        mid = (start+end)//2
        if nums[mid] == target:
            return mid
        if nums[start] <= target < nums[mid]: 
            return self.binarySearch(nums, target, start, mid-1)
        elif nums[mid] < target <= nums[end]: 
            return self.binarySearch(nums, target, mid+1, end)
        elif nums[mid] > nums[end]: 
            return self.binarySearch(nums, target, mid+1, end)
        else: 
            return self.binarySearch(nums, target, start, mid-1)
```
