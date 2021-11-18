# K번째 수

[문제](https://programmers.co.kr/learn/courses/30/lessons/42748)

```js
function solution(array, commands) {
  const result = [];
  
  commands.forEach(([first, last, nth])=>{
    result.push(array.slice(first - 1, last).sort((a, b) => a - b)[nth - 1])
  })
  
  return result;
}
```