# Valid_Perfect_Square


[문제](https://leetcode.com/explore/learn/card/binary-search/137/conclusion/978/)


```js
/**
 * @param {number} num
 * @return {boolean}
 */
const isPerfectSquare = function(num) {
  if (num === 1) return true;
  let left = 1;
  let right = Math.floor(num / 2);
  
  while(left <= right) {
    const mid = Math.floor((left + right) / 2);
    const square = mid * mid;
    if (square === num) return true;
    
    if (square > num) {
      right = mid - 1;
    } else {
      left = mid + 1;
    }
  }
  
  return false;
};
```