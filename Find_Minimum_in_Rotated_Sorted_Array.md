# Find Minimum in Rotated Sorted Array


[문제](https://leetcode.com/explore/learn/card/binary-search/126/template-ii/949/)


```js
/**
 * @param {number[]} nums
 * @return {number}
 */
const findMin = function(nums) {
  let left = 0;
  let right = nums.length - 1;
  
  while(left < right) {
    const mid = Math.floor((left + right) / 2);
    
    if (nums[mid] > nums[right]) {
      left = mid + 1;
    } else {
      right = mid;
    }
  }
  
  return nums[left]
};
```