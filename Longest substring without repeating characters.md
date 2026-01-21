# Intuition
To get all eligible substring, then get the one with greatest length

# Approach
Solve the easiest cases (0,1,2 characters) then handle the harder ones

# Complexity
- Time complexity: O(n^2)

# Code
```python3 []
class Solution:
    def get_new_wip(self, wip, s):
        new_start = 0
        for i in range(0,len(wip)):
            if wip[i] == s:
                new_start = i+1
                break
        return wip[new_start: len(wip)]+s

    def lengthOfLongestSubstring(self, s: str) -> int:
        if len(s) <=1:
            return len(s)
        if (len(s) == 2):
            if (s[0]!=s[1]):
                return 2
            else:
                return 1
        
        max_len = 0
        wip = s[0]
        for i in range(1,len(s)):
            if s[i] in wip:
                if s[i] == wip[-1]:
                    wip = s[i]
                else:
                    wip = self.get_new_wip(wip,s[i]) if len(wip)>1 else s[i]
            else:
                wip+=s[i]
            if max_len < len(wip):
                max_len = len(wip)
           
        return max_len
        
```
