# Solution
```
# """
# This is BinaryMatrix's API interface.
# You should not implement it, or speculate about its implementation
# """
#class BinaryMatrix(object):
#    def get(self, x: int, y: int) -> int:
#    def dimensions(self) -> list[]:

class Solution:
    def leftMostColumnWithOne(self, binaryMatrix: 'BinaryMatrix') -> int:
        if not binaryMatrix:
            return -1
        rows,cols = binaryMatrix.dimensions()
        result = -1
        i,j = 0,cols-1
        
        while i<rows and j>=0:
            if binaryMatrix.get(i,j)==1:
                result = j
                j -= 1
                
            else:
                i += 1
        
        return result

```
