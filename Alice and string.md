## Problem Statement:

Alice has a binary string of length N, and she wants to maximize its beauty. The beauty of the string is defined as the length of the longest substring consisting of equal letters (0s or 1s) within the string. Alice is allowed to change at most K characters in the string. The task is to find the maximum beauty Alice can achieve.

## Hint:

To solve this problem, think about how you can efficiently iterate through the string while keeping track of the number of changes made. Use a sliding window approach to find the maximum beauty.

## Short Explanation:

The problem can be solved using a sliding window approach. Initialize counters for the maximum beauty, the left end of the window, and counts of 0s and 1s within the window. Iterate through the string using the right pointer, and for each character, check if it can be part of the window while keeping track of the counts of 0s and 1s. If the minimum count of 0s and 1s in the window is greater than K, shrink the window from the left end. Update the maximum beauty when needed. Finally, output the maximum beauty.

## Detailed Explanation:

In this problem, we are tasked with finding the maximum beauty of a binary string while allowing Alice to change at most K characters. To achieve this, we can use a sliding window approach. Here's how it works:

Initialize variables for the maximum beauty, the left end of the window, and counts of 0s and 1s within the window.
Iterate through the string using the right pointer.
For each character, check if it can be part of the window while keeping track of the counts of 0s and 1s.
If the minimum count of 0s and 1s in the window is greater than K, shrink the window from the left end to ensure we don't exceed the allowed number of changes.
Update the maximum beauty when needed by comparing the current window's length with the previous maximum beauty.
Finally, output the maximum beauty.

## Pseudo Code:

int N // length of the string
int K // maximum allowed changes
string s // input binary string
int maxBeauty = 0 // maximum beauty
int left = 0 // left end of the window
int zeroCount = 0 // count of 0s within the window
int oneCount = 0 // count of 1s within the window
for (int right = 0; right < N; right++)
if (s[right] == '0')
increment zeroCount by 1
else
increment oneCount by 1
while (minimum(zeroCount, oneCount) > K)
if (s[left] == '0')
decrement zeroCount by 1
else
decrement oneCount by 1
increment left by 1
maxBeauty = maximum(maxBeauty, zeroCount + oneCount)
print maxBeauty


## Time Complexity:

The time complexity of this approach is O(N), where N is the length of the string. We iterate through each character of the string, making it efficient for large inputs.

## Space Complexity:

The space complexity is O(1) because we use a constant amount of extra space to store counters and indices.

This code efficiently solves the problem within the given constraints.