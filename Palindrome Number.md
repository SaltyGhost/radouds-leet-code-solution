# Intuition
The thing is in symetry

# Code
```javascript []
/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
    let x_str = x.toString()
    for(let i=0; i < x_str.length/2; i++){
        if (x_str[i] != x_str[x_str.length-(1+i)]){
            return false;
        }
    }
    return true;
};
```
