# Solution
```
class Solution:
    def stringShift(self, s: str, shift) -> str:
        sh = 0
        for i in shift:
            if i[0] == 0:
                sh += i[1]
            else:
                sh -= i[1]
        sh %= len(s)  
        return s[sh:] + s[:sh]
```
