# Solution
```
class Solution:
    def checkValidString(self, s: str) -> bool:
        
        #Solution 1
         
        cmin = cmax = 0
        for i in s:
            if i == '(':
                cmax += 1
                cmin += 1
            if i == ')':
                cmax -= 1
                if cmin > 0:
                    cmin -= 1
            if i == '*':
                cmax += 1
                if cmin > 0:
                    cmin -= 1
            if cmax < 0:
                return False
        return cmin == 0


        #Solution 2

        #if len(s)==0 or s=='*':return True
        #if len(s)==1:return False
        
        #leftBalance = 0
        # from left
        #for i in s:
            #if i==')':#leftBalance-=1
            #else: #leftBalance+=1
            
            #if leftBalance<0:#return False #If number of ) brackets is more than the sum of ( and *, string is unbalanced
        
        #if leftBalance==0:return True
        
        #rightBalance = 0
        # from right
        #for i in reversed(s):
            #if i=='(':#rightBalance-=1
            #else: #rightBalance+=1
            
            #if rightBalance<0:#return False#If number of ( brackets is more than the sum of ) and *, string is unbalanced
        
        #return True
        
        
```
