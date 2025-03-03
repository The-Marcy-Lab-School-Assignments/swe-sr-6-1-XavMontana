# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Arrays, Linked Lists and Doubly Linked Lists all allow programmers to organize data in a sequence. So, how would you choose to use one over the other?

In your response, make sure to compare the time complexities for insertion, removal, and random access (grabbing a particular known element by index/position) for each data structure as well as memory usage and ease of traversal.

### Response 1

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
