```
/**
 * @param {number[]} nums
 * @return {number}
 */
// https://leetcode-cn.com/problems/first-missing-positive/submissions/

var firstMissingPositive = function(nums) {
    let len = nums.length;
    if(!len) return 1;
    let max =  Math.max.apply(null,nums);
    if(max <=0 ) return 1
    let arr = [];
    
    for(let i = 0;i < len; i++){
       if(nums[i] > 0){
           arr[nums[i]] = nums[i]
       }   
    }
   
    if(arr.length == 0 || arr[1] == 0) return 1;
    let j = 1;
    for(;j < arr.length; j++){ 
        if(!arr[j]) {
            return j;
            break;
        };
    }
    return j ;
};

```