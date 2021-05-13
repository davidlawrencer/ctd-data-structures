```js

// QUEUE

// Add -> "Enqueue"
// Remove -> "Dequeue"
// Look at the next thing -> "Front"
// "isEmpty"

// Two implementations
// 1st: Easy one using an Array

class Queue {

  constructor() {
    this.list = [];
  }

  enqueue(value) {
    // add to the end
    this.list.push(value)
    // O(1)
  }

  dequeue() {
    // shows us what's in front
    // it removes that item from the front
    // "takes that item out of line"
    return this.list.shift()

    // When removing first, we have to move all the other items over one spot to the left
    // O(n)
  }

  get front() {
    // edge case: nothing in queue. what do we do? up to you :) as-is, this returns undefined
    return this.list[0];
    // O(1)
  }

  // easy... wipe off your brow, good job.
  get isEmpty() {
    return this.list.length === 0;
    // O(1)
  }

}

let queue = new Queue()
for (i = 0; i < 5; i ++ ) {
  queue.enqueue(i)
}

console.log(queue.front) // 0, because 0 gets added first
console.log(queue.isEmpty) // false

for (i = 0; i < 3; i ++) {
  queue.dequeue()
}

console.log(queue.front) // 3, because 3 "moved up 3 spaces in line"

class Animal {
  constructor(genus, name) {
    this.genus = genus;
    this.name = name;
  }
}

const dog = new Animal("canus", "spot")
const cat = new Animal("feline", "minnos")
const frog = new Animal("frogus", "jumpy")

const vetSchedule = [dog, frog, cat]

let vetQueue = new Queue()

for (i = 0; i < vetSchedule.length; i++ ) {
  vetQueue.enqueue(vetSchedule[i])
}

//now our vet knows what animals they're seeing, and in what order

vetQueue.dequeue // A dog


// Dequeueing with our Queue is slow. We want our data structures to be fast!
// Let's make it better using a LinkedList


// Why would we choose something harder?
// Because we can make it work faster/more efficiently

class Node {
  constructor(value, next) {
    this.value = value
    this.next = next
  }
}

class LinkedList {
  constructor() {
    // front -> where we'll dequeue from
    this.head = null
    // back -> where we'll enqueue to
    this.tail = null
  }

  /* 
    HEAD(2) -> (3) -> TAIL(4)
    enqueue(6)
    HEAD(2) -> (3) -> (4) -> TAIL(6)
    dequeue()
    HEAD(3) -> (4) -> TAIL(6)
  */
}

class LLQueue {
  constructor() {
    this.list = new LinkedList()
  }

  enqueue(value) {
    // Overall strategy: I want to reassign tail to be a node with the `value` coming in here
    const node = new Node(value)
    
    // edge cases:
    // What if tail doesnt exist? what is head doesn't exist
    // -> these both mean there's an empty list
    
    if (this.list.tail === null) {
      // for an empty list, that node is both head and tail
      this.list.tail = node
      this.list.head = node
    } else {
      let tail = this.list.tail
    // first, we make sure that the current tail now points to the new node
    // make sure there's a connection
      tail.next = node
    // situation 1: HEAD(2) -> (3) -> TAIL(4) -> (6)
    // situation 2: HEADTAIL(2)
    // then reassign
      this.list.tail = node
    // situation 1: HEAD(2) -> (3) -> (4) -> TAIL(6)
    // situation 2: HEAD(2) -> TAIL(6)
    
    }
  }

  dequeue() {
    // remove from the front
    // We'll always change HEAD in this function
    // We'll need to watch out for tail in certain edge cases

    // what if there are no node/values/items?
    if (this.list.head === null) {
      // situation 1: nothing to dequeue, because no head node
      // solution: do nothing.
      return;
    } 
    
    // what if there is one item?
    // before dequeue, tail points to the same node as head
    if (this.list.head === this.list.tail) {
      // we need to go from one item to zero items
      // situation 2: HEADTAIL(2)
      // dequeue -> remove the first item
      // head and tail now don't point to any node

      let value = this.list.head.value
      this.list.head = null
      this.list.tail = null
      return value
      // O(1), because it doesnt take longer as the list grows
    }
    
    // if we start from 2+ items in the queue
    // situation 3: HEAD(2) -> (3) -> (4) -> TAIL(6)

    let head = this.list.head
    // head = node(3)
    this.list.head = head.next
    // situation 3: HEAD(3) -> (4) -> TAIL(6)
    // the node (2) "falls off"
    return head.value
    // O(1), because it doesnt take longer as the list grows
    
    // "garbage collection" -> how does the software clear memory to get rid of items that are no longer in use?
    // how does this get cleaned up in JS v. in Ruby
    // similar to ActiveStorage in Rails?
    
  }

  get front() {
    //edge case: empty queue
    if (this.list.head === null) {
      return
    }
    return this.list.head.value
  }

  get isEmpty() {
    return this.list.head === null
  }
}
```
