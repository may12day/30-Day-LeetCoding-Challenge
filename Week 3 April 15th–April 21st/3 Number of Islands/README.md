# Solution
```
class Solution:
    def numIslands(self, grid):
        if not grid:
            return 0

        islands = 0
        for i in range(len(grid)):
            for j in range(len(grid[i])):
                if grid[i][j] == '1':
                    islands += 1
                    self.dfs(grid, i, j)
        return islands

    def dfs(self, grid, i, j):
        if i<0 or j<0 or i>=len(grid) or j>=len(grid[0]) or grid[i][j] != '1':
            return
        
        grid[i][j] = '0'
        self.dfs(grid, i+1, j)
        self.dfs(grid, i-1, j)
        self.dfs(grid, i, j+1)
        self.dfs(grid, i, j-1)
        
        
```
