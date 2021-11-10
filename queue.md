# 자바스크립트로 큐 구현하기

![IMG_DC00C90D5746-1](https://user-images.githubusercontent.com/69200669/141120961-c842526e-1c81-4f88-b0e5-14d24608342f.jpeg)

```js
function Queue() {
  this.store = [];
  this.enqueue = enqueue;
  this.dequeue = dequeue;
  this.front = front;
  this.rear = rear;
  this.empty = empty;
}

function enqueue(item) {
  this.store.push(item);
}

function dequeue() {
  return this.store.shift();
}

function front() {
  return this.store[0];
}

function rear() {
  return this.store[this.store.length - 1]
}

function empty() {
  return this.length === 0 ? true : false;
}

const queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
queue.enqueue(3);
queue.dequeue();
queue.front(); // 2
queue.enqueue(4);
queue.rear(); // 4
queue.empty(); // false
```

```js
class Queue {
  constructor() {
    this.store = [];
  }
  
  enqueue(item) {
    this.store.push(item);
  }
  
  dequeue() {
    this.store.shift();
  }
  
  empty() {
    return this.store.length === 0 ? true : false;
  }
  
  front() {
    return this.store[0];
  }
  
  rear() {
    return this.store[this.store.length - 1];
  }
}

const queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
queue.enqueue(3);
queue.dequeue();
queue.front(); // 2
queue.enqueue(4);
queue.rear(); // 4
queue.empty(); // false
```