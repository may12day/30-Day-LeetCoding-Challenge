# Solution
```
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        res = {}
        for i in strs:
            b = ''.join(sorted(i))
            if b in res:
                res[b] += [i]
            else:
                res[b] = [i]
        
        return [res[i] for i in res]
```
