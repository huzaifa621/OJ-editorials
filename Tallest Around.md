# Tallest Around - Editorial

**Difficulty**: Easy
**Prerequisite**: Array, Sliding Window

## Problem Statement

The problem asks us to find the tallest person in each interval of K people within a queue. We are given the length of the queue L, the integer K, and the heights of the people in the queue. We need to find the tallest person in each interval of K people.

## Hint

Use a sliding window approach to efficiently find the tallest person in each interval.

## Short Explanation

To solve this problem, we can use a sliding window approach. Initialize two pointers, left and right, to represent the current interval of K people. Iterate through the queue while moving the right pointer. Keep track of the maximum height within the current interval. When the size of the interval becomes equal to K, output the maximum height and move the left pointer to create a new interval.

## Detailed Explanation

1. Initialize two pointers, left and right, to 0. These pointers represent the current interval of K people.

2. Initialize a variable, max_height, to 0. This variable will keep track of the maximum height within the current interval.

3. Iterate through the queue using the right pointer (from 0 to L-1).

   a. Update max_height with the maximum of max_height and the height of the person at the right pointer.

   b. Check if the size of the current interval (right - left + 1) is equal to K:

      - Output max_height as the tallest person in the interval.

      - Move the left pointer to create a new interval (left++).

4. Continue this process until the right pointer reaches the end of the queue.

5. Output the tallest person in each interval as space-separated integers.

## Pseudo Code
```plaintext
int t // number of test cases
for each test case:
    int L // length of the queue
    int K // interval size
    array A[L] // queue of heights
    int left = 0 // left pointer
    int max_height = 0 // maximum height in the current interval
    for right from 0 to L-1:
        max_height = max(max_height, A[right])
        if (right - left + 1 == K):
            print max_height as integer, followed by a space
            left++ // move left pointer to create a new interval
```
## Time Complexity
The time complexity of this approach is O(L) for each test case, where L is the length of the queue. We iterate through the queue once.

## Space Complexity
The space complexity is O(1) for each test case. We use a constant amount of extra space for variables.
