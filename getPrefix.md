# get Prefix

strs은 단어가 담긴 배열입니다. 공통된 시작 단어(prefix)를 반환해주세요.

예를 들어 strs = ['start', 'stair', 'step'] return은 'st'

strs = ['start', 'wework', 'today'] return은 ''


## 풀이

```js
const getPrefix = strs => {
  if(strs.length === 0) return '';
  strs.sort();
  for (let i = 0; i < strs[0].length; i++) {
    if(strs[0] === strs[strs.length - 1]) return strs[0];
    if(strs[0][i] !== strs[strs.length - 1][i]) return strs[0].slice(0, i)
  }
}
```