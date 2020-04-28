# Solution
```
# Method 1

from collections import OrderedDict
class FirstUnique:

    def __init__(self, nums: List[int]):
        self.d = OrderedDict()
        self.s = set()
        for i in nums:
            self.add(i)

    def showFirstUnique(self) -> int:
        if len(self.d)==0:
            return -1
        else:
            for i in self.d:
                return i

    def add(self, value: int) -> None:
        if value not in self.s:
            self.s.add(value)
            self.d[value]=None
        else:
            self.d.pop(value,None)


# Method 2

class DDL:
#     def __init__(self, val):
#         self.val = val
#         self.next = None
#         self.prev = None

# class FirstUnique:

#     def __init__(self, nums: List[int]):
#         self.m = {}
#         self.head = DDL('#')
#         self.cur = self.head
#         for n in nums:
#             self.add(n)
                    
        

#     def showFirstUnique(self) -> int:
#         return self.head.next.val if self.head.next else -1

#     def add(self, value: int) -> None:
#         if value not in self.m:
#             node = DDL(value)
#             self.cur.next = node
#             node.prev = self.cur
#             self.cur = self.cur.next
#             self.m[value] = node
#         else:
#             node = self.m[value]
#             if node == self.cur:
#                 self.cur = self.cur.prev
#             if node.next:
#                 node.next.prev = node.prev
#             if node.prev:
#                 node.prev.next = node.next
#             node.next = None
#             node.prev = None

# Your FirstUnique object will be instantiated and called as such:
# obj = FirstUnique(nums)
# param_1 = obj.showFirstUnique()
# obj.add(value)
                
```
