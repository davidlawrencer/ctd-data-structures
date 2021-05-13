# Stacks

## Implementations

- [Javascript](./js-implementation.md)
- [Ruby](./ruby-implementation.md)

## What are they?

Stacks are abstract data types that allow you to interact with only one item at a time. The order that items are added is also the order in which they'll be removed; thus, we say that stacks are Last-In, First-Out (LIFO) data structures. Stacks are an easy way to organize our data using a data structure whose basic operations are all O(1).

## Why use them?

Stacks can be incredibly helpful for figuring out order and nesting. 

- If we're debugging our applications and we want to find out all of the operations that occurred before an issue presented, we can check the "Call Stack" to see what order our functions were called in. The most recent function be at the top of the stack, and then we could dig down from there to see the functions that were called before it.
- If we want to parse a raw string to see if it has valid punctuation (every quote should close, every paren should have a closing paren), we could track the opening punctuation marks and make sure the corresponding closing mark comes next.

## Practice

1. Create a function `reverseString`, which takes in a string and then uses a stack to reverse the order of the characters in the input.
2. Create a function `validPunctuation` which takes in a string and uses a stack to see if every `"`, `(`, `{`, and `[` mark has a closing mark. Use a stack here because order matters! Ex: `"([])"` is valid, but `"([)]"` is not, even though both strings contain the same 6 characters.
3. Sort an input stack using other stacks. HINT: Use three stacks, as if you are implementing the [Tower of Hanoi](https://en.wikipedia.org/wiki/Tower_of_Hanoi) problem.

