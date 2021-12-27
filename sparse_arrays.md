# Sparse Arrays


[문제](https://www.hackerrank.com/challenges/sparse-arrays/problem?isFullScreen=true)


```js

function matchingStrings(strings, queries) {
  const res = [];
  
  for (let i = 0; i < queries.length; i++) {
    let count = 0;
    for (let j = 0; j < strings.length; j++) {
      if (queries[i] === strings[j]) count += 1;
    }
    
    res.push(count)
  }
  
  return res
}
```