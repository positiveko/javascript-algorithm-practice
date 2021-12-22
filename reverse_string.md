# Reverse String


[문제](https://leetcode.com/explore/learn/card/recursion-i/250/principle-of-recursion/1440/)


```js
/**
 * @param {character[]} s
 * @return {void} Do not return anything, modify s in-place instead.
 */
const reverseString = function(s) {
  if (s.length === 0) return;
  
  const temp = s[0];
  s.shift();
  reverseString(s);
  s.push(temp);
};
```