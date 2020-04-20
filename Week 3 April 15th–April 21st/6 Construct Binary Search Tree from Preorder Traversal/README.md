# Solution
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def bstFromPreorder(self, preorder: List[int]) -> TreeNode:
        root = TreeNode(preorder[0])
        stack = [root]
        for value in preorder[1:]:
            if value < stack[-1].val:
                stack[-1].left = TreeNode(value)
                stack.append(stack[-1].left)
            else:
                while stack and stack[-1].val < value:
                    last = stack.pop()
                last.right = TreeNode(value)
                stack.append(last.right)
        return root
    
    # i = 0
    # def bstFromPreorder(self, A, bound=float('inf')):
    #     if self.i == len(A) or A[self.i] > bound:
    #         return None
    #     root = TreeNode(A[self.i])
    #     self.i += 1
    #     root.left = self.bstFromPreorder(A, root.val)
    #     root.right = self.bstFromPreorder(A, bound)
    #     return root
```
