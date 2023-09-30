## Problem Name - Maximize Substring

* * *

## Problem Statement:

Manu is given a string S consisting of lowercase English alphabets of size N. His task is to find the lexicographically maximum substring of this string.

## Hint:

To solve this problem, think about iterating through the string and keeping track of the lexicographically maximum substring encountered so far.

## Short Explanation:

In this problem, we are given a string S, and we need to find the lexicographically maximum substring of this string. To do this, we can iterate through the string from left to right while keeping track of the lexicographically maximum substring encountered so far. We start with an empty string as the initial maximum substring and update it whenever we find a character that is greater than or equal to the first character of the current maximum substring. This ensures that we build a lexicographically maximum substring as we move through the string.

## Detailed Explanation:

To solve this problem, we can use the following approach:

1. Read the input value N, which represents the size of the string.
2. Read the input string S.
3. Initialize a variable `max_substring` to an empty string (to store the lexicographically maximum substring).
4. Initialize a variable `current_substring` to the first character of the input string (to start the current substring).
5. Iterate through the characters of the input string from left to right, starting from the second character (index 1).
6. For each character at index i:
   - If the character at index i is greater than or equal to the first character of `current_substring`, append it to `current_substring`.
   - Otherwise, compare `current_substring` with `max_substring`. If `current_substring` is lexicographically greater, update `max_substring` with its value.
   - Reset `current_substring` to the current character.
7. After the loop, compare `current_substring` with `max_substring` one more time to ensure that the last substring is considered.
8. Print the value of `max_substring` as the lexicographically maximum substring.

## Pseudo Code:
```plaintext
- int N // size of the string
- string S // input string
- string max_substring = "" // lexicographically maximum substring
- string current_substring = S[0] // current substring starting from the first character
- for i = 1 to N-1
    - if S[i] >= current_substring[0]
        - append S[i] to current_substring
    - else
        - if current_substring is lexicographically greater than max_substring
            - set max_substring to current_substring
        - set current_substring to S[i]
- if current_substring is lexicographically greater than max_substring
    - set max_substring to current_substring
- print max_substring
```

## Time Complexity:

The time complexity of this approach is O(N), where N is the size of the input string. We iterate through the string once, and the comparisons and concatenations are done in constant time for each character.

## Space Complexity:

The space complexity is O(N) because we store the input string S, `max_substring`, and `current_substring`, each of which can have a maximum length of N.