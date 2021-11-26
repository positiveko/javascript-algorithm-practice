# Guess Number Higher or Lower


[문제](https://leetcode.com/explore/learn/card/binary-search/125/template-i/951/)


```js
/** 
 * Forward declaration of guess API.
 * @param {number} num   your guess
 * @return 	            -1 if num is lower than the guess number
 *			             1 if num is higher than the guess number
 *                       otherwise return 0
 * var guess = function(num) {}
 */

/**
 * @param {number} n
 * @return {number}
 */
const guessNumber = function(n) {
    let left = 1;
    let right = n;

    while (left < right) {
        const mid = Math.floor((left + right) / 2);
        const temp = guess(mid);
        if(temp === 0) return mid;
        if(temp === -1) right = mid - 1;
        else left = mid + 1;
    }
    return left;
};
```