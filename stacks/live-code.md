```js
// Big-O Growth rates


// O(1) ->  "Constant time" 
// every time we do this, it will need to do 1, or some constant amount of computations

const print1 = (n) => {
   console.log(n)
}

// print1(1) // prints once
// print1([1,2,3,4]) // prints once -> the size of our input does not affect how much our function must do

// O(n) -> "Linear time"
// for any array/collection, if we print each item, that means we're performing `n` prints

const printN = (n) => {
   console.log(n)
   for (i = 0; i < n.length; i++) {
     console.log(n[i])
   }
}

printN([1]) // only runs 1 time, because the array has 1 element. NOT O(1), however.
printN([1,2,3,5,76,12]) // run more than 1 time -> for the size of our array, we perform that many operations in an O(n)

const newArray = new Array(10_000).fill(1)
print1(newArray) // Prints 1 time
printN(newArray) // this grew at a rate of n -> linear, as our input gets bigger, it'll take 1 * n amount of time to perform that function


// O(n^2) -> "Quadratic Time"
// if 1 thing comes in -> 1 execution
// if 2 things comes in -> 4 executions
// if 20 things comes in -> 400 executions

const printNSquared = (n) => {
   // one for-loop is O(n)
   for (i = 0; i < n.length; i++) {
     // nested for loop is O(n^2)
     // nested math -> n * n
     for (j = 0; j < n.length; j++) {
       console.log(n[j], n[i])
       // if we nested another loop, that's O(n * n * n) -> O(n^3). Whoa!
     }
   }
}

// Figuring out the Big-O rate

// to look at every value
// grab first array, look through item in there
// grab second array
// n = matrix.length
// n^2 = matrix.length * matrix.length

const squareMatrix = [[1,2,3],
                      [4,5,6],
                      [7,8,9]]


// this matrix is NOT square, so we're not only looking at `n` items each time we look through the elements
// n = matrix.length
// m = innerArray.length
// n * m = matrix.length * innerArray.length
// We still say this is quadratic, because both `n` and `m` grow linearly, which means that when combined, they grow quadratically
const matrix = [[1,2,3],
                [4,5,6],
                [7,8,9],
                [10,11,12]]


printNSquared([1,2,3,4,5,6,7,8,9])

const printNTwice = (n) => {
   for (i = 0; i < n.length; i ++ ) {
     console.log("our num first time is " + n[i])
   }

   for (i = 0; i < n.length; i ++ ) {
     console.log("our num second time is " + n[i])
   }
   // we drop the lowest complexity
   // O(n + n) = O(2 * n) = O(n)

}

printNTwice([1,2,3,4,5,6])

// "amortized time" - theoretically how long would this take for any sized input?

// JS Benchmarking -> actual measuring of the length of time to execute a function

console.time()

// ...
// do some stuff
// ...

console.timeEnd()





// Let's make a stack! Since this is abstract, we'll base our implementation on an Array.
// To get our stack working nicely, we'll need to find ONE location in the Array to add, remove, and look at.

class Stack {
  constructor() {
    this.list = []
  }

  // when we push onto an Array, we are adding to the end of the array
  push(n) {
    // O(1) -> one change, just adds to the end of the array
    this.list.push(n)
  }

  // for our other functions we write, let's make sure we're just looking at the end of the array called `list`

  // this is removing an item from the stack (aka the list)
  pop() {
    // O(1) -> one change, removes from the array
    // removes from end of the array and returns it to whoever is using the stack
    return this.list.pop()
  }

  get top() {
    // O(1) -> one operation (look up item at top)

    // let's see what is on "top" of the array
    // we don't remove anything when we look at `top`, whereas in `pop` we both remove and return to `top` of the stack
    return this.list[this.list.length - 1]
  }

  // isEmpty
  get isEmpty() {
    // O(1) -> we only do one thing (check for equivalence on length)

    // we want to tell someone whether or not (Boolean value) the stack has anything in it
    return this.list.length === 0
  }
}

const stack = new Stack()
stack.push(1)
stack.push(2)
stack.push(3)

// when i pop, i want to see three first
console.log(stack.list)
console.log(stack.top)
console.log(stack.pop()) // 3!
console.log(stack.list)
console.log(stack.pop())
console.log(stack.list)
console.log(stack.pop())
console.log(stack.pop())

// Nothing left!

console.log(stack.top)
console.log(stack.isEmpty)
console.log(stack.pop())
console.log(stack.pop())
console.log(stack.pop())
console.log(stack.isEmpty)



// Big-O Wrap-up
// We want our DS to work as quickly as possible!

const arr = new Array()
for (i = 0; i < 5, i++ ) {
  // adding each is O(1)
  arr.push(i)
}

arr // has 5 items

// adding to the front means we have to move n items before add in our new item
arr.unshift(-1) //O(n)

// if we knew we needed to remove from the front of a list many times, we would probably choose a LL over an array
const linkedList = new LL()
//remove first -> O(1)
// if we know where `head` is, we can just change 1 item when adding/removing from the front of a list

```
