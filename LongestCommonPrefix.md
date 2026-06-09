# Intuition
Check special case first
Then get the shortest string
And go check index per index

# Complexity
- Time complexity:
O(n+nˆ2)



# Code
```golang []
func longestCommonPrefix(strs []string) string {
    if len(strs) == 1 {
        return strs[0]
    }
    
    var minLength int = len(strs[0])
    if minLength == 0 {
        return ""
    }
    
    var indexOfMin int = 0
    for i:=0; i < len(strs); i++ {
        if len(strs[i]) == 0 {
            return ""
        }
        if len(strs[i]) < minLength {
            minLength = len(strs[i])
            indexOfMin = i
        }
    }
    
    var test string = ""
    fmt.Println("string:", indexOfMin)
    for k := 0; k < minLength ; k ++ {
        if k < minLength{
            test = strs[indexOfMin][:k+1]
        }
        for j:=0; j < len(strs); j++ {
            if strs[j][k] != test[k] {
                return test[:k]
            }
        }
    }
    return test
}
```
