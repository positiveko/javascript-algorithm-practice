# 자바스크립트로 스택 구현하기

![IMG_5CDCD1440D01-1](https://user-images.githubusercontent.com/69200669/141116513-deda77a4-7a35-46df-888c-dc487b826761.jpeg)

```js
class Stack {
  constructor() {
    this.items = [];
    this.count = 0;
  }

  // Add element to top of stack
  push(element) {
    this.items[this.count] = element;
    this.count += 1;
    return this.count - 1;
  }

  // Return and remove top element in stack
  // Return undefined if stack is empty
  pop() {
    if (this.count == 0) return undefined;
    let deleteItem = this.items[this.count - 1];
    this.count -= 1;
    return deleteItem;
  }

  // Check top element in stack
  peek() {
    return this.items[this.count - 1];
  }

  // Check if stack is empty
  isEmpty() {
    return this.count == 0;
  }

  // Check size of stack
  size() {
    return this.count;
  }

  // Print elements in stack
  print() {
    let str = '';
    for (let i = 0; i < this.count; i++) {
      str += this.items[i] + ' ';
    }
    return str;
  }

  // Clear stack
  clear() {
    this.items = [];
    this.count = 0;
    return this.items;
  }
}

const stack = new Stack();

stack.isEmpty();
stack.push(100);
stack.push(200);
stack.peek();
stack.push(300);

stack.pop();
stack.pop();

stack.clear();

stack.size();
stack.isEmpty();
```

### reference

- [Stack Data Structure | JavaScript](https://www.youtube.com/watch?v=wtynhUwS5hI)
