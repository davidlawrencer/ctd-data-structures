```js

class ArrayQueue {

  constructor() {
    this.list = [];
  }

  enqueue(value) {
    this.list.push(value)
  }

  dequeue() {
    return this.list.shift()
  }

  get front() {
    return this.list[0];
  }

  get isEmpty() {
    return this.list.length === 0;
  }

}

class LLQueue {
  constructor() {
    this.list = new LinkedList()
  }

  enqueue(value) {
    if (this.list.tail === null) {
      this.list.tail = node
      this.list.head = node
    } else {
      let tail = this.list.tail
      tail.next = node
      this.list.tail = node
    }
  }

  dequeue() {
    if (this.list.head === null) {
      return;
    } 
    
    if (this.list.head === this.list.tail) {
      let value = this.list.head.value
      this.list.head = null
      this.list.tail = null
      return value
    }

    let head = this.list.head
    this.list.head = head.next
    return head.value    
  }

  get front() {
    if (this.list.head === null) {
      return
    }
    return this.list.head.value
  }

  get isEmpty() {
    return this.list.head === null
  }
}

// Helper classes

class Node {
  constructor(value, next) {
    this.value = value
    this.next = next
  }
}

class LinkedList {
  constructor() {
    this.head = null
    this.tail = null
  }
}


```
