# 자바스크립트로 스택 구현하기

![IMG_5CDCD1440D01-1](https://user-images.githubusercontent.com/69200669/141116513-deda77a4-7a35-46df-888c-dc487b826761.jpeg)

```js
function Stack() {
  this.store = [];
  this.top = 0;
  this.push = push;
  this.pop = pop;
  this.peek = peek;
  this.clear = clear;
  this.length = length;
}

function push(item) {
  this.store[this.top++] = item;
}

function pop() {
  return this.store[--this.top];
}

function peek() {
  return this.store[this.top - 1];
}

function length() {
  return this.top;
}

function clear() {
  this.top = 0;
}

const stack = new Stack();
stack.push(1);
stack.push(2);
stack.push(3);
stack.length(); // 3
stack.pop();
stack.peek(); // 2
```

```js
class Stack {
  constructor() {
    this.store = [];
    this.top = 0;
  }

  push(item) {
    this.store[this.top++] = item;
  }
  pop() {
    return this.store[--this.top];
  }
  peek() {
    return this.store[this.top - 1];
  }
  length() {
    return this.top;
  }
}

const stack = new Stack();
stack.push(1);
stack.push(2);
stack.push(3);
stack.length(); // 3
stack.pop();
stack.peek(); // 2
```
