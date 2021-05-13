```js

// Stack using array as underlying data collector - we'll manipulate the element at the last index, since it supports O(1) operations
class ArrayStack {
  constructor() {
    this.list = []
  }

  push(n) {
    this.list.push(n)
  }

  pop() {
    return this.list.pop()
  }

  get top() {
    return this.list[this.list.length - 1]
  }

  get isEmpty() {
    return this.list.length === 0
  }
}

// Stack using LinkedList as underlying data collector - we'll manipulate HEAD, since it supports O(1) operations
class LLStack {
  constructor() {
    this.list = new LinkedList()
  }

  push(n) {
    this.list.addToFront(n)
  }

  pop() {
    return this.list.removeFromFront()
  }

  get top() {
    return this.list.head
  }

  get isEmpty() {
    return this.list.isEmpty
  }
}


```
