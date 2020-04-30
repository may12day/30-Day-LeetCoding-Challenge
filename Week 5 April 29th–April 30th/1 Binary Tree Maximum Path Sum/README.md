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
    def maxPathSum(self, root: TreeNode) -> int:
        totalsum = -math.inf
        
        def dfs(node):
            if not node:
                return 0
            lsum = dfs(node.left)
            rsum = dfs(node.right)
                
            diam_sum = max(lsum + rsum + node.val, node.val, lsum+node.val, rsum+node.val)
            
            nonlocal totalsum
            totalsum = max(totalsum, diam_sum)
            
            return max(lsum + node.val, rsum+node.val, node.val)
        
        dfs(root)
        return totalsum

# Method 2(BFS)

# class Solution:
#     def maxPathSum(self, root: TreeNode) -> int:
#         max_path, max_sum = {None: 0}, -float("inf")
#         stack = [(root, False)]
#         while stack:
#             node, visited = stack.pop()
#             if node:
#                 if not visited:
#                     stack.append((node, True))
#                     stack.append((node.right, False))
#                     stack.append((node.left, False))
#                 else:
#                     left, right = max(0, max_path[node.left]), max(0, max_path[node.right])
#                     max_sum = max(max_sum, node.val+left+right)
#                     max_path[node] = max(node.val+left, node.val+right)
#         return max_sum
           
```
