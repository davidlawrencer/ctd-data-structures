# Stacks

## Implementations

- [Javascript](./js-implementation.md)
- [Ruby](./ruby-implementation.md)

## What are they?

Linked Lists are lists of ordered elements, very similar to what you might see in an array. The chief difference from an array is that a Linked List's elements (called "Nodes") must know about the item after them to maintain order after an add or delete action. In contrast, arrays will have to adjust the size of the entire data structure in order to maintain order after an add or delete action.

## Why use them?

Linked lists have a few advantages over arrays:

- Adding to the beginning of the list takes O(1).
- Items can be added or removed from the middle of the list without re-allocating memory for the list (VERY important for lower-level programming).
- There is no need to define an initial size.

## Practice

#### Basic

1. Add a function `removeElement(:value)`, which will delete any nodes that have that input value.
2. Add a function `removeDuplicates`, which will remove any duplicate values from the list.
3. Add a function `sort`, which will sort the list by its values from low to high (you can assume the linked list only has numbers).

#### Stretch

1. Add a function `middle`, which finds the middle value of a linked list. Try to do this in one traversal of the list using the [fast and slow pointer/tortoise and hair](https://emre.me/coding-patterns/fast-slow-pointers/) approach.
2. Add a function `hasCycle`, which determines whether or not there is a cycle in the list (and returns a Bool). A cycle occurs when the `next` value of a Node points back to a previous `Node`, which prevents traversal from beginning to end of the list. Ex:
![image](https://user-images.githubusercontent.com/50370157/118125564-296ef980-b3c5-11eb-8f02-55d7cce28b31.png)

3. Thus far we've worked with a particularly basic kind of Linked List called a "Singly-Linked List". Another kind is a "Doubly-Linked List" (DLL). 

Each Node in a DLL has a `next` pointer AND another pointer called `previous`, which points to the Node before it in the list (the Head node's `previous` is null). The DLL will keep track of the beginning (`HEAD`) node, and it will also track the end (`TAIL`) node.

Implement a new Node class for the DLL, and the DLL itself. After you've created it, make sure to add functions allowing you to:
- Add a value to the beginning of the list.
- Add a value to the end of the list.
- Look up the first and last values in the list.
