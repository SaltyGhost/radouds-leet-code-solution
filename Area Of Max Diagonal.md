# Intuition
Get the rectangles having the longest diagonal first using Pythagore theorem then get the one with the max area


# Complexity
- Time complexity: O(2n)


# Code
```python3 []
class Solution:
    def areaOfMaxDiagonal(self, dimensions: List[List[int]]) -> int:
        max_diag_square = 0
        max_diag_dims = []
    
        for dim in dimensions:
            diag = (dim[0]**2) + (dim[1]**2)
            if diag > max_diag_square:
                max_diag_square = diag
                max_diag_dims = [dim]
            elif diag == max_diag_square:
                max_diag_dims.append(dim)
        
        return max(map(lambda x: x[0]*x[1], max_diag_dims))

```
