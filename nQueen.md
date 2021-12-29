# N-Queen


[문제](https://programmers.co.kr/learn/courses/30/lessons/12952?language=javascript)


```js
function solution(n) {
  let res = 0;
  const chess = Array.from(Array(n), () => Array(n).fill(0));
  
  const dfs = (chess, qIdx) => {
    if (qIdx === n) {
      return res++;
    }
    
    for (let i = 0; i < n; i++) {
      if (chess[qIdx][i] === 0) {
        chess[qIdx][i] = qIdx + 1;
        
        let ld = i - 1;
        let rd = i + 1;
        for(let j = qIdx + 1; j < n; j++) {
          if(ld >= 0 && chess[j][ld] === 0) {
            chess[j][ld] = qIdx + 1;
          }
          if(rd < n && chess[j][rd] === 0) {
            chess[j][rd] =  qIdx + 1;
          }
          if(chess[j][i] === 0) {
            chess[j][i] = qIdx + 1;
          }
          ld--;
          rd++;
        }
        
        dfs(chess, qIdx + 1)
        
        chess[qIdx][i] = 0;
        ld = i - 1;
        rd = i + 1;
        for(let j = qIdx + 1; j < n; j++) {
          if(ld >= 0 && chess[j][ld] === qIdx + 1) {
            chess[j][ld] = 0;
          }
          if(rd < n && chess[j][rd] === qIdx + 1) {
            chess[j][rd] =  0;
          }
          if(chess[j][i] === qIdx + 1) {
            chess[j][i] = 0;
          }
          ld--;
          rd++;
        }
        
      }
    }
  }
  
  dfs(chess, 0)
  return res;
}

```