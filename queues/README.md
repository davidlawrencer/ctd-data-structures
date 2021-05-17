# Queues


## Implementations

- [Javascript](./js-implementation.md)
- [Ruby](./ruby-implementation.md)

## What are they?

Queues are collections of elements that are kept in order. Similarly to stacks and linked lists, this data structure is linear, meaning that its elements form a sequeunce. The order is maintained by adding to one end ("enqueuing" from the back) and removing from the other end ("dequeuing" from the front). This data structure is classified as Last In, First Out (LIFO).

## Why use them?

The abstract data structure Queue is used for the same reason banks have people line up in order. When there are multiple tasks to be completed, or data to be processed, they cannot all be completed at the same time. By enqueuing tasks at the back, we can ensure that we are completing the oldest items first. A standard queue will thus sort its items from oldest to newest, but it can also be expanded to serve tasks by additional criteria like priority.

## Practice

#### Basic

1. Add a function `sumAll`, which will return the sum of all values in a queue of numbers.
2. Add a function `reverse`, which will reverse the items in your queue. It might be helpful to use a stack to do this (think about how a sequence of items would be added to a stack).
3. Add a function `find(:index)`, which will return the value at a specific place in the sequence. Assume that your queue is 0-indexed.

#### Stretch

1. Implement a queue using two stacks. Note that you will have to make a performance tradeoff; will your `enqueue` or your `dequeue` run in linear time?

2. Implement a [Priority Queue](https://www.geeksforgeeks.org/priority-queue-set-1-introduction/), which attaches a "priority" to each element when `enqueue`ing, and makes sure to `dequeue` the element with the highest priority.

3. Use a queue to solve the [change-making](https://www.geeksforgeeks.org/check-if-x-can-give-change-to-every-person-in-the-queue/) problem.
