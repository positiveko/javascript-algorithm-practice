# Find Smallest Letter Greater Than Target


[문제](https://leetcode.com/explore/learn/card/binary-search/137/conclusion/977/)


```js
const nextGreatestLetter = function(letters, target) {
  let [left, right] = [0, letters.length - 1];
  
  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (letters[mid] > target) {
      right = mid - 1;
    } else {
      left = mid + 1; 
    }
  }
  return letters[left % letters.length];
};
```