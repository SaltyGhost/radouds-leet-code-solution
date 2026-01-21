# Intuition
Try each element to each other

# Complexity
- Time complexity: O(n^2)

- Space complexity: O(1)


# Code
```javascript []
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
        for(let i=0; i < nums.length; i++){
            let elem_1 = nums[i]
            for (let j=0; j < nums.length; j++){
                if (i!=j){
                    let elem_2 = nums[j]
                    if (elem_2 + elem_1 == target){
                        return [i,j]

                    }
                }
            }
        }
};
```
