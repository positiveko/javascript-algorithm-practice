# reverse number

reverse 함수에 정수인 숫자를 인자로 받습니다. 그 숫자를 뒤집어서 return해주세요.

x: 숫자 return: 뒤집어진 숫자를 반환!

예들 들어, x: 1234 return: 4321

x: -1234 return: -4321

x: 1230 return: 321

## 풀이

```js
const reverse = x => {
  const res = (x+'').split('').reverse().join('');
  return x < 0 ? - parseInt(res) : parseInt(res)
}
```

시간복잡도: O(n)


