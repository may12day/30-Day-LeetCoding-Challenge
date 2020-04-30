# Solution
```
# Method 1

# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:       
    def isValidSequence(self,root, arr):
        n = len(arr)
        def dfs(i, node):
            if not node or i == n or arr[i] != node.val:
                return False
            if i == n - 1 and node.left is None and node.right is None:
                return True
            return dfs(i+1, node.left) or dfs(i+1, node.right)
        return dfs(0, root)

# Method 2 (BFS)

# class Solution:
#     def isValidSequence(self, root: TreeNode, arr: List[int]) -> bool:   
#             if not root or root.val != arr[0]: return False
#             queue = [root]
#             for val in arr[1:]:
#                 new_queue = []
#                 for node in queue:
#                     if node.left  and node.left.val  == val: new_queue.append( node.left )
#                     if node.right and node.right.val == val: new_queue.append( node.right )
#                 if not new_queue: return False
#                 queue = new_queue
#             res = queue[0]
#             return res.left is None and res.right is None
           
```
