# Just Find Minimum - Editorial

---

## Problem Description:

The user is given a number, N, denoting the number of stack operations to perform. There are three types of operations:
1. `PUSH V`: Push the integer `V` onto the stack.
2. `POP`: Pop the top element from the stack. Print "EMPTY" if the stack is empty.
3. `MIN`: Print the minimum value currently in the stack.

---

## Hint:

Consider using an auxiliary data structure alongside the main stack to keep track of the minimum value at any given point.

---

## Short Explanation:

While a stack can help us with the `PUSH` and `POP` operations, we need an auxiliary data structure to efficiently retrieve the minimum element. One option is to use another stack to keep track of the minimum element seen so far. As elements are added to the main stack, we can update this auxiliary stack to reflect the current minimum.

---

## Detailed Explanation:

Whenever a `PUSH` operation is encountered:
1. Push the value onto the main stack.
2. Compare the value with the top of the minimum stack (if it exists). If the new value is smaller, or the minimum stack is empty, push this new value onto the minimum stack.

For the `POP` operation:
1. Pop the top value from the main stack.
2. If this value matches the top of the minimum stack, pop from the minimum stack as well.

For the `MIN` operation:
1. Simply print the top value of the minimum stack. If the minimum stack is empty, print "EMPTY".

---

## Pseudo Code:

```plaintext
- int N // number of operations
- stack<int> mainStack
- stack<int> minStack

- for (int i = 0; i < N; i++)
    - read operation
    
    - if operation is "PUSH V"
        - push V onto mainStack
        - if minStack is empty or V <= top of minStack
            - push V onto minStack

    - else if operation is "POP"
        - if mainStack is not empty
            - if top of mainStack == top of minStack
                - pop from minStack
            - pop from mainStack
        - else
            - print "EMPTY"

    - else if operation is "MIN"
        - if minStack is not empty
            - print top of minStack
        - else
            - print "EMPTY"
```

---

## Time Complexity:

All operations (`PUSH`, `POP`, `MIN`) are O(1) because we always deal with the top of the stack(s), so for N operations, the time complexity is O(N).

---

## Space Complexity:

In the worst case, the space complexity is O(N) because we could have all elements pushed into both the main stack and the min stack.

---