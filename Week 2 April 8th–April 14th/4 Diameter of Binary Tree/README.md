# Solution
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def diameterOfBinaryTree(self, root: TreeNode) -> int:
        
        def height(root):
            nonlocal diameter
            if not root:
                return 0
            
            left = height(root.left)
            right = height(root.right)
            diameter = max(diameter, left + right)
            return max(left, right) + 1
        
        diameter = 0
        height(root)
        return diameter
```
