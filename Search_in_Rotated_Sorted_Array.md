# Search in Rotated Sorted Array


[문제](https://leetcode.com/explore/learn/card/binary-search/125/template-i/952/)


```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
const search = function(nums, target) {
  if (nums.length === 1) return nums[0] === target ? 0 : -1;
  
  let left = 0;
  let right = nums.length - 1;
  
  let pp = 0;
  
  while(left < right) {
    let mid = Math.floor((left + right) / 2);
    
    if (nums[mid] > nums[right]) {
      left = mid + 1;
    } else {
      right = mid;
    }
  } 
  
  pp = left;
  left = 0;
  right = nums.length - 1;
  
  if (nums[pp] <= target && target <= nums[right]){
    left = pp;
  } else {
    right = pp - 1;
  }

  while(left <= right) {
    let mid = Math.floor((left + right) / 2);
    if(nums[mid] === target){
      return mid;
    }
    if(nums[mid] < target){
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return -1;
};
```