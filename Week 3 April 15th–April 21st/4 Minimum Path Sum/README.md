# Solution
```
class Solution:
    def minPathSum(self, g):
        m = len(g)
        n = len(g[0])
        if m < 1:
            return 0

        for i in range(0, m):
            for j in range(0, n):
                if i == 0 and j == 0:
                    continue
                if i == 0 and j > 0:
                    g[i][j] += g[i][j - 1]
                elif j == 0 and i > 0:
                    g[i][j] += g[i - 1][j]
                else:
                    g[i][j] += min(g[i - 1][j], g[i][j - 1])
        return g[-1][-1]
        
        
```
