# Find K Closest Elements


[문제](https://leetcode.com/explore/learn/card/binary-search/135/template-iii/945/)


```js
/**
 * @param {number[]} arr
 * @param {number} k
 * @param {number} x
 * @return {number[]}
 */
const findClosestElements = function(arr, k, x) {
  let left = 0;
  let right = arr.length - k;
  
  while(left < right) {
    const mid = Math.floor((left + right) / 2);
    
    if (x - arr[mid] > arr[mid + k] - x) {
      left = mid + 1;
    } else {
      right = mid;
    }
  }
  
  return arr.slice(left, left + k);
};

```