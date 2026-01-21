# Intuition
I need a dictionnary for matching values then for 1 letter case a easy block
but for other cases i need to check the thing from left to right and distingish the 4 and 9 case numbers


# Code
```javascript []
/**
 * @param {string} s
 * @return {number}
 */
var romanToInt = function(s) {
    let value = 0
    let values = {"I":1,"V":5,"X":10,"L":50,"C":100, "D":500,"M":1000}
    if (s.length == 1){
        return values[s]
    }
    for(let i=0;i<s.length;i++){
        let letter = s[i]
        let letter_value = values[s[i]]
        if(i+1 < s.length){
            let next_letter_value = values[s[i+1]]
            if(next_letter_value > letter_value){
                value -= letter_value
            }else{
                value+=letter_value
            }
        }else{
            value+=letter_value
        }
    }
    return value

};
```
