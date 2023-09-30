# Sum of Next Smaller - Editorial

**Difficulty**: Easy
**Prerequisite**: Stack, Array Traversal

## Problem Statement

Given an array of integers, you need to find the sum of the nearest smaller values to the right of each element. If there is no smaller value to the right, consider it as zero.

## Hint

This problem can be effectively solved using a stack. Try to traverse the array from right to left and utilize a stack to keep track of the nearest smaller elements.

## Short Explanation

To solve this problem, we traverse the array from right to left. We use a stack to keep track of the nearest smaller elements for each element. If an element is smaller than the top element of the stack, we pop elements from the stack until we find a smaller or equal element or the stack becomes empty. We sum these popped elements and store the result for the corresponding element. If the stack is empty, we consider the sum as 0. We repeat this process for all elements and output the sums.

## Detailed Explanation

1. Start by traversing the array from right to left.
2. Initialize an empty stack to keep track of the nearest smaller elements.
3. For each element in the array:
   - Pop elements from the stack until the stack is not empty and the top element is greater than the current element. For each popped element, add it to the sum for the corresponding position in the result array.
   - Push the current element onto the stack.
4. If the stack is not empty after the traversal, it means there were no smaller elements to the right for those elements. We consider their sum as 0.
5. Output the sums for each element.

## Pseudo Code

```plaintext
int[] findSumOfNextSmaller(int[] arr, int n) 
  int[] result // Initialize an array to store the sums
  Stack stack // Initialize a stack to keep track of smaller elements
  for i from n-1 to 0, decrementing
    while stack is not empty and stack.top > arr[i]
      sum += stack.pop() // Pop and add elements to sum until a smaller or equal element is found
    result[i] = sum // Store the sum for the current position
    stack.push(arr[i]) // Push the current element onto the stack
  for i from 0 to n-1
    if result[i] is not set
      result[i] = 0 // Set sum as 0 for elements with no smaller values to the right
  return result
```
## Time Complexity
The time complexity of this approach is O(n) for each test case, where n is the size of the input array. This is because we traverse the array once and perform stack operations.

## Space Complexity
The space complexity is O(n) for each test case, where n is the size of the input array. This is due to the space used by the stack and the result array.
