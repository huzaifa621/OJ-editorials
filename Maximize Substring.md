## Problem Name - Maximize Substring

* * *

## Problem Statement:

Manu is given a string S consisting of lowercase English alphabets of size N. His task is to find the lexicographically maximum substring of this string.

## Hint:

To solve this problem efficiently, you can iterate through the string while keeping track of the lexicographically maximum character and its instances.

## Short Explanation:

In this problem, you can find the lexicographically maximum substring by iterating through the string while keeping track of the maximum character and its instances. The provided code snippet demonstrates this approach.

## Detailed Explanation:

1. Initialize an empty list `instances` to store the indices where the maximum character occurs in the string.
2. Initialize `maxi` to the first character of the input string `s` (s[0]) as the initial maximum character.
3. Iterate through each character `char` in the string `s`.
4. In each iteration, update `maxi` to be the maximum of `char` and the current `maxi`. This ensures that `maxi` always contains the lexicographically maximum character encountered so far.
5. After completing the loop, you have the lexicographically maximum character stored in `maxi`.
6. Iterate through the indices of the string `s` from 0 to N-1.
7. For each index `i`, check if `s[i]` is equal to `maxi`. If it is, append `i` to the `instances` list. This identifies all instances where the maximum character occurs in the string.
8. Now, you have a list of indices `instances` where the maximum character occurs.
9. Iterate through each index `idx` in the `instances` list.
10. For each `idx`, update `maxi` by finding the maximum lexicographically substring starting from `s[idx]` onwards. You can do this by taking the maximum of the current `maxi` and the substring `s[idx:]`.
11. After completing the loop, `maxi` contains the lexicographically maximum substring.
12. Print `maxi` as the answer.

## Pseudo Code:

```plaintext
- string s // input string
- list instances = [] // to store indices where maximum character occurs
- char maxi = s[0] // initial maximum character

- // Find the maximum character
- for char in s:
    - set maxi to maximum of char and maxi

- // Find indices where maximum character occurs
- for i in range(N):
    - if s[i] is equal to maxi:
        - append i to instances

- // Find the lexicographically maximum substring
- for idx in instances:
    - set maxi to maximum of s[idx:] and maxi

- print maxi
```

## Time Complexity:

The time complexity of this approach is O(N), where N is the size of the input string. We iterate through the string once to find the maximum character, and then we iterate through the instances to find the lexicographically maximum substring.

## Space Complexity:

The space complexity is O(1) because we only use a constant amount of extra space to store variables, regardless of the input size.