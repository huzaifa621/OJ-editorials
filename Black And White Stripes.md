## Problem Name - Black And White Stripes

* * *

## Problem Description:

Given a stripe of checkered paper with cells that are either white or black, the task is to find the minimum number of cells that must be recolored from white to black in order to have a segment of k consecutive black cells on the stripe. If there is already a segment of k consecutive black cells in the given stripe, no recoloring is required, and the answer is 0.

## Hint:

To solve this problem, iterate through the cells in the stripe and keep track of the current segment of black cells. When you encounter a white cell, check if recoloring it can extend the current segment to length k. If not, increment the recoloring count.

## Short Explanation:

In this problem, we need to find the minimum number of cells that need to be recolored from white to black in order to have a segment of k consecutive black cells on the stripe. We iterate through the cells in the stripe and maintain a current segment of consecutive black cells. When we encounter a white cell, we check if recoloring it can extend the current segment to length k. If not, we increment the recoloring count. Finally, we output the count of recolored cells.

## Detailed Explanation:

To solve this problem, we can use the following approach:

1. Read the input values n and k, where n is the length of the stripe and k is the desired length of the consecutive black segment.
2. Read the string representing the stripe.
3. Initialize two variables: `current_segment` to 0 (to keep track of the current consecutive black segment) and `recolor_count` to 0 (to keep track of the number of cells that need to be recolored).
4. Iterate through the cells of the stripe from left to right.
5. For each cell, check if it is black ('B') or white ('W'):
   - If it is black, increment `current_segment`.
   - If it is white, check if recoloring it can extend the current segment to length k. If so, do not increment `recolor_count` or reset `current_segment`. Otherwise, increment `recolor_count` and reset `current_segment` to 1.
6. Continue this process for all cells in the stripe.
7. After the loop, `recolor_count` will contain the minimum number of cells that need to be recolored to achieve a segment of length k.
8. Print the value of `recolor_count` as the answer.

## Pseudo Code:
```plaintext
- int n // length of the stripe
- int k // desired length of consecutive black segment
- string stripe // input stripe
- int current_segment = 0 // current consecutive black segment length
- int recolor_count = 0 // number of cells to recolor
- for i = 0 to n-1
    - if stripe[i] is 'B'
        - increment current_segment by 1
    - else
        - if current_segment < k
            - increment recolor_count by 1
            - reset current_segment to 1
- print recolor_count
```

## Time Complexity:

The time complexity of this approach is O(n), where n is the length of the stripe. We iterate through the stripe once to find the minimum number of recolorings required.

## Space Complexity:

The space complexity is O(1) because we only use a constant amount of extra space to store variables, regardless of the input size.