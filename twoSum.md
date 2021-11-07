# twoSum

`twoSum`함수에 숫자배열과 '특정 수'를 인자로 넘기면,
더해서 '특정 수'가 나오는 index를 배열에 담아 return해 주세요.

```
nums: 숫자 배열
target: 두 수를 더해서 나올 수 있는 합계
return: 두 수의 index를 가진 숫자 배열

example)

```
nums = [4, 9, 11, 14]
target = 13 

nums[0] + nums[1] = 4 + 9 = 13
return [0, 1].
```

# 가정
target으로 보내는 합계의 조합은 배열 전체 중에 2개 밖에 없다고 가정하겠습니다.

# 풀이

```js
const twoSum = (nums, target) => {
  for (let i = 0; i < nums.length - 1; i++) {
    for (let j = i + 1; j < nums.length; j++) {
        if(nums[i] + nums[j] === target) {
        return [i, j];
      }
    }
  }
}****
```

시간복잡도: O(n^2)

