```js

// Node class: holds our data, and has a reference to the next node. That's it!

class Node {
  constructor(value, next = null) {
    this.value = value // Any type
    this.next = next // Another Node
  }
}

// Linked List class: knows where the HEAD node is, and uses that position to add, remove, and look through values in the chain of nodes.
// When a user interfaces with the Linked List class, they should not have to know about Nodes. They are looking for the values that these nodes contain!

class LinkedList {
  
  // constructor just needs to know where head is. That's it!
  constructor(head = null) {
    this.head = head;
  }
  
  // some sample LL functions. You could make tons of them!
  
  addToFront(value) {
    let node = new Node(value)
    node.next = this.head
    this.head = node
  }
  
  printAllValues() {
    if (this.head === null) {
      return;
    }

    let currentHead = this.head
    while (currentHead !== null) {
      console.log(currentHead.value)
    }
  }
  
  get isEmpty() {
    return this.head === null;
  }
  
}


```
