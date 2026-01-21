# Intuition
We need to use the alphabet index, and the letter position for the value of the letter, the column number is the sum of the letters values


# Code
```python3 []
class Solution:
    def titleToNumber(self, columnTitle: str) -> int:
        alphabet="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
        l = len(columnTitle)
        v = 0
        for i in range(0,l):
            letter = columnTitle[l-i-1]
            power = i
            for j in range(0,26):
                if letter == alphabet[j]:
                    v+= (j+1) * (26**power)
        return v

        
```
