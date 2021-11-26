# Search for a Range

[문제](https://leetcode.com/explore/learn/card/binary-search/135/template-iii/944/)


```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
const searchRange = function(nums, target) {
  if (nums.length === 1) {
    return nums[0] === target ? [0,0]: [-1,-1]
  }
  if (nums.length < 1) return [-1, -1];
  
  let left = 0;
  let right = nums.length - 1;
  
  
  while(left <= right) {
    const mid = Math.floor((left + right) / 2);
    
    if (nums[mid] === target) {
      let sidx = mid;
      let lidx = mid;
      
      while(sidx > 0 && target === nums[sidx - 1]) {
        sidx -= 1;
      }
      while(lidx < nums.length - 1 && target === nums[lidx + 1]) {
        lidx += 1;
      }
      
      return [sidx, lidx];
    }
    
    if (target < nums[mid]) {
      right = mid - 1;
    } else {
      left = mid + 1;
    }
  }
  
  return [-1, -1];
};



```