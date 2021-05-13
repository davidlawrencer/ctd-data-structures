```js

// Arrays

// Make an array of length 6
const arr = [0,1,2,3,4,5];

// Look up element by Index
arr[0]; // 0, the first element
arr[1]; // 1, the second element

// Keeps track of length
arr.length // 6
// Last element is at index 5
arr[arr.length - 1] // 5
arr[6] // undefined

// Sparse array doesn't fill in all values
arr[9] = 100
arr.length // 10
arr[7] // undefined
arr // [0, 1, 2, 3, 4, 5, <3 empty items>, 100]

// Adding to beginning will move everything else over
arr.unshift(-1)
arr[1] // 2
arr  // [ -1, 0, 1, 2, 3, 4, 5, <3 empty items>, 100 ]

// Two new classes: Node, and LinkedList
// Nodes will hold 1 piece of information ("Data" or value)
// LinkedLists will add, remove, and look through nodes for our information

class Node {
  constructor(value, next = null) {
    this.value = value // Any type
    this.next = next // Another Node
  }
}

let node1 = new Node(3)
node1.value // 3
node1.next // null
let node2 = new Node(2)
node2.value // 2
node2.next // null

node1.next = node2
// (3) -> (2)

let node3 = new Node(10, node1)
// (10) -> (3) -> (2)
console.log(node3.next.next.value) // 2

let node4 = new Node(10, node3)
// (10) -> (10) -> (3) -> (2)
node4.next.next.next.value

let node5 = new Node(4, node3)
// (4) -> (10) -> (3) -> (2)
// (10) -> (10) -> (3) -> (2) still exists
// we need a way to track WHERE we should be looking


class LinkedList {
  // our goal is to only reference one node at a time, and then use that node to do everything else
  // That node is called the "Head" of the list
  constructor(head = null) {
    this.head = head;
  }

  get lastValue() {
    let currentHead = this.head;
    // make sure head isn't null
    if (currentHead === null) {
      return;
    }

    // look through the nodes contained in here
    // the end of the list is the node whose `next` is null
    while (currentHead.next !== null) {
      currentHead = currentHead.next
      
      // example flow:
      // HEAD(a) -> (b) -> (c) -> (d)
      // first, currentHead is `a`
      // inside the first iteration, set currentHead to `b`
      // (b) -> (c) -> (d)
      // `b` has a next, so we set currentHead to `c`
      // (c) -> (d)
      // `c` has next, etc...
      // once the currentHead is pointing to `d`, this loop wont run again, so we're at the end
    }
    
    return currentHead.value;
  }

  addToBeginning(value) {
    let node = new Node(value)
    // HEAD(b) -> (c) -> (d), I want to add f
    node.next = this.head
    // (f) -> HEAD(b) -> (c) -> (d)
    this.head = node
    // HEAD(f) -> (b) -> (c) -> (d)
  }

  sumElements() {
    let sum = 0
    // make sure there is a head node
    if (this.head === null) {
      return sum
    }

    let currentHead = this.head
    while (currentHead.next !== null) {
      sum = sum + currentHead.value
      currentHead = currentHead.next
    }
    return sum
  }
}

let list1 = new LinkedList(node5)
console.log(list1.lastValue)
list1.addToBeginning(3)
list1.addToBeginning(6)
console.log(list1.sumElements())


```
