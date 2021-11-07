# Get Length of String

String 형인 str 인자에서 중복되지 않은 알파벳으로 이루어진 제일 긴 단어의 길이를 반환해주세요.

str: 텍스트 return: 중복되지 않은 알파벳 길이 (숫자 반환)

예를 들어, str = "abcabcabc" return 은 3 => 'abc' 가 제일 길기 때문

str = "aaaaa" return 은 1 => 'a' 가 제일 길기 때문

str = "sttrg" return 은 3 => 'trg' 가 제일 길기 때문

## 풀이

```js
const getLengthOfStr = str => {
  if(!str) return 0;
  for (let i = 1; i < str.length; i++) {
    for (let j = 0; j < i; j++) {
      let temp = str.slice(j, str.length - i + j + 1);
      let filtered = [...new Set(temp)]
       if(filtered.length === temp.length) return temp.length;
    }
  }
  return 1;
}
```
