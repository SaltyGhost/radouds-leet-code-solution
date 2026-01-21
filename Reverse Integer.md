# Intuition
String reverse approach then check constraint


# Code
```python3 []
class Solution:
    def reverse(self, x: int) -> int:
        if x.bit_length() >= 32:
            return 0

        sign = -1 if x<0 else 1
        abs_x = abs(x)
        ans= int(str(abs_x)[::-1]) * sign
        
        if ans.bit_length() <= 31 :
            return ans
        else:
            return 0
        
```
