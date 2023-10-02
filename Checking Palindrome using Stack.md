## Problem Statement:

Given a string, check whether it's a Palindrome or not using stack.


## Hint:

To check if a string is a palindrome using a stack, you can push half of the characters onto the stack and then pop and compare them with the remaining half. This works because a palindrome is the same forwards and backwards.


## Short Explanation:

Given a string, we need to determine whether it's a palindrome. A palindrome is a string that reads the same forwards and backward.

## Detailed Explanation:

To solve this problem, we can use a stack data structure. Here's the step-by-step approach:

1. Initialize an empty stack.
2. Iterate through the characters of the input string from left to right.
3. For each character, push it onto the stack.
4. After pushing half of the characters (rounded down if the length is odd), start popping characters from the stack and comparing them with the remaining characters in the string.
5. If all the characters match, the string is a palindrome, and we print "YES." Otherwise, we print "NO."

## Pseudo Code:

Here's the pseudo code to check if a string is a palindrome using a stack:

```

function isPalindrome(s):
    Initialize an empty stack
    n = length of s
    Iterate through the first n/2 characters of s:
        Push each character onto the stack
    If n is odd, skip the middle character

    Iterate through the remaining characters in s:
        Pop a character from the stack
        If it doesn't match the current character in s:
            Print "NO"
            Return
    Print "YES"

s = Read input for the string
isPalindrome(s)


```


## Time Complexity:

The time complexity of this algorithm is O(N), where N is the length of the input string s. We iterate through half of the string to push characters onto the stack and then compare them with the remaining characters.

## Space Complexity:

The space complexity is O(N/2) in the worst case since we push half of the characters onto the stack. Therefore, it can be simplified to O(N).