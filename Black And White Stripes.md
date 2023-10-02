## Problem Name - Black And White Stripes

* * *

## Problem Statement:

You are given a stripe of checkered paper with cells that are either white or black. The task is to find the minimum number of cells that must be recolored from white to black in order to have a segment of k consecutive black cells on the stripe. If there is already a segment of k consecutive black cells in the given stripe, no recoloring is required, and the answer is 0.

## Hint:

To solve this problem efficiently, you can use a sliding window approach to keep track of the current segment of black cells.

## Short Explanation:

In this problem, you can use a sliding window approach to efficiently find the minimum number of cells that need to be recolored. The provided code snippet demonstrates this approach.

## Detailed Explanation:

1. Initialize `mini` to positive infinity (float('inf')) to keep track of the minimum number of recolorings required. Initialize `s` to 0 to keep track of the number of black cells in the current segment.
2. Loop from 0 to K-1 (inclusive) to count the number of black cells in the initial segment of size K. If `string[i]` is 'B', increment `s` by 1.
3. Update `mini` as the minimum of `K - s` and the current `mini`. This represents the minimum recolorings needed for the initial segment.
4. Initialize `start` to 0 and `end` to K to set up the initial window.
5. Enter a while loop that runs as long as `end` is less than N (the length of the stripe).
6. Within the loop, check if `string[start]` is 'B'. If it is, decrement `s` by 1 to account for the cell leaving the window.
7. Check if `string[end]` is 'B'. If it is, increment `s` by 1 to account for the cell entering the window.
8. Update `mini` as the minimum of `K - s` and the current `mini`. This represents the minimum recolorings needed for the current window.
9. Increment `start` by 1 to slide the window to the right.
10. Increment `end` by 1 to extend the window to the right.
11. Continue the loop until `end` reaches the end of the stripe.
12. After the loop, `mini` contains the minimum number of cells that need to be recolored. Print `mini` as the answer.

## Pseudo Code:

```plaintext
- int N // length of the stripe
- int K // desired length of consecutive black segment
- string string // input stripe
- int mini = infinity // to store minimum recolorings
- int s = 0 // number of black cells in the current segment

- for i in range(0, K, 1):
    - if string[i] is 'B':
        - increment s by 1

- set mini to minimum of (K - s) and mini

- int start = 0 // left end of the window
- int end = K // right end of the window

- while end < N:
    - if string[start] is 'B':
        - decrement s by 1
    - if string[end] is 'B':
        - increment s by 1
    - set mini to minimum of (K - s) and mini
    - increment start by 1
    - increment end by 1

- print mini
```

## Time Complexity:

The time complexity of this approach is O(N), where N is the length of the stripe. We iterate through the stripe once, and the comparisons and updates are done in constant time for each window.

## Space Complexity:

The space complexity is O(1) because we only use a constant amount of extra space to store variables, regardless of the input size.