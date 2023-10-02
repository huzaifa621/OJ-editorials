# Longest Balanced Sub-array - Editorial

---

## Problem Description:

Chintu is presented with an array of positive and negative integers. Positive integers represent opening brackets of a specific type, while their negative counterparts represent the closing brackets of the same type. The objective is to find the length of the longest sub-array that is balanced in terms of these brackets. 

A matching pair of brackets is considered balanced if the set of brackets it encloses are matched. For instance, [3, 4, -4, -3] is balanced, but [3, 4, -3, -4] is not.

---

## Hint:

Think of how a stack can be used to track the opening and closing of brackets. Whenever a bracket is opened, you can push its type to the stack, and when a bracket is closed, you can pop from the stack and check for a match.

---

## Short Explanation:

For this task, use a stack to track the opening brackets. As you iterate through the array, push the opening brackets onto the stack. When encountering a closing bracket, pop the last item from the stack and check if they form a balanced pair. By keeping track of these operations and the array indices, you can identify balanced sub-arrays and determine their lengths.

---

## Detailed Explanation:

We begin by initializing an empty stack. As we iterate over the array, whenever we encounter a positive number (opening bracket), we push it onto the stack. On encountering a negative number (closing bracket), we check the top of the stack. If the top item on the stack is the positive counterpart of the current negative number, we pop the item from the stack, signifying that we have found a balanced pair.

However, if at any point the stack is empty (when we encounter a closing bracket) or the top item doesn't match the current bracket, we reset our current length counter and continue with the process.

By monitoring the indices where we start and end these operations, we can calculate the lengths of balanced sub-arrays. The maximum length found during this process is our desired answer.

---

## Pseudo Code:

```plaintext
- int N // number of brackets
- array brackets[N] // array of brackets
- stack<int> st // to track opening brackets
- int maxLength = 0
- int currentLength = 0

- for (int i = 0; i < N; i++)
    - if brackets[i] > 0 // opening bracket
        - push brackets[i] onto st
        - increment currentLength
    - else if !st.empty() and st.top() == -brackets[i] // matching closing bracket
        - pop from st
        - increment currentLength
        - if st.empty()
            - maxLength = max(maxLength, currentLength)
    - else // unmatched closing bracket
        - clear st
        - currentLength = 0

- print maxLength
```

---

## Time Complexity:

The time complexity of this approach is O(N), where N is the number of brackets. Each bracket is processed once, either being pushed onto the stack or matched with an opening bracket.

---

## Space Complexity:

The space complexity is O(N) in the worst case. This happens when all the brackets are opening brackets, and the stack grows to accommodate all of them.

---