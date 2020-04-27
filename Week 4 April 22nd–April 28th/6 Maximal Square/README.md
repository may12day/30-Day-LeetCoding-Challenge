# Solution
```
class Solution:
    def maximalSquare(self, matrix: List[List[str]]) -> int:
        rows = len(matrix)
        if not matrix or not rows:
            return 0
        cols = len(matrix[0])
        height = 0
        ans = [[0]*(cols+1) for i in range(rows+1)]
        
        for i in range(1,rows+1):
            for j in range(1,cols+1):
                if matrix[i-1][j-1]=='1':
                    ans[i][j] = 1 + min(ans[i-1][j], ans[i][j-1], ans[i-1][j-1])
                    height = max(height, ans[i][j])
                    
        return height**2
                
```
