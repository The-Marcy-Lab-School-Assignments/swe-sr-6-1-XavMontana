# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Arrays, Linked Lists and Doubly Linked Lists all allow programmers to organize data in a sequence. So, how would you choose to use one over the other?

In your response, make sure to compare the time complexities for insertion, removal, and random access (grabbing a particular known element by index/position) for each data structure as well as memory usage and ease of traversal.

### Response 1

```
We should choose arrays when we need fast random access and a predictable number of elements, linked lists when frequent insertion/deletion occurs at the beginning of the list but no random access, and doubly linked lists when we need frequent insertion/deletion at both the beginning and end of the list.


Arrays have the fastest time using indexes but are difficult to modify dynamically. A singly linked list has linear traversal required to find an element and can only traverse forward. Doubly linked lists are similar to singly linked lists but can traverse both forward and backward effectively.


In a singly linked list, each node stores a pointer to the next node, leading to extra memory usage, same for doubly linked list, but doubly stores pointers to both previous and next node, which leads to memory usage being double. Arrays use a contiguous block of memory, leading to effective catching.

```

## Prompt 2

Imagine you are developing a web browser's "back" button functionality. When a user clicks "back," the browser should navigate to the previously visited webpage.

Would you use a stack or a queue to implement this functionality?

In your response, explain what a Stack/Queue is and why it would be best for this use case. Make sure that your response includes the terms LIFO or FIFO.

### Response 2

Mario response
A stack is the best use for the "back" button because it follows the Last In First Out path. Each visited page is pushed onto the stack, and when the user clicks "back", the last page visited is popped off, returning them to the previous page. This mirrors expected browser behavior, making stacks the best choice for web navigation history.


## Prompt 3

What is an Abstract Data Type and why are they worth learning about?

### Response 3

```
Abstract Data Types(ADT) define a class of objects and the operations that can be performed on them, along with their expected behavior(semantics), but without specifying implementation details. ADT is worth learning because they provide a conceptual framework for organizing and manipulating data effectively, single or specific implementations.
```

## Prompt 4

A few classic problems involving a stack are the `isBalanced` and `isPalindrome` functions. Choose one of these functions and provide a solution to it along with a brief lesson explaining how it works.

### Response 4

Mario Response

```javascript
function isBalanced(s) {
  let stack = [];
  const pairs = { d: "b", q: "p" }; // These are the  matching pairs

  for (let char of s) {
    if (Object.values(pairs).includes(char)) {
      stack.push(char);
    } else if (Object.keys(pairs).includes(char)) {
      if (!stack.length || stack.pop() !== pairs[char]) {
        return false; // if  a pair  is wrong or extra chars
      }
    }
  }
  return stack.length === 0; // if a stack is balanced it ends up empty
}
```

This function follows Last In First Out using a stack. It pushes the b and the p characters onto the stack and pops them when encountering d or q characters (their opposites/pair), ensuring they match. If there’s a mismatch or extra characters, it returns false. An empty stack at the end means the string is balanced.
