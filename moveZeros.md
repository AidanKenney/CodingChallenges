Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Example:

Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
Note:

You must do this in-place without making a copy of the array.
Minimize the total number of operations.

```js
var moveZeroes = function(nums) {
    let i = 0
    let j = i + 1
    while (j < nums.length) {
        if (nums[i] === 0 && nums[j] !== 0) {
            // swap
            let temp = nums[j]
            nums[j] = nums[i]
            nums[i] = temp
            i++
            j++
        } else if (nums[i] === 0 && nums[j] === 0) {
            // let j move ahead to find next number
            j++
        } else {
            i++
            j++
        }
    } 
    return nums
};
```
