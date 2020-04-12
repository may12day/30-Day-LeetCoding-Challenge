# Solution
```
import heapq
class Solution:
    def lastStoneWeight(self, stones: List[int]) -> int:
        pq = [-x for x in stones]
        heapq.heapify(pq)
        for i in range(len(stones) - 1):
            heapq.heappush(pq, heapq.heappop(pq) - heapq.heappop(pq))
        return -pq[0]
```
