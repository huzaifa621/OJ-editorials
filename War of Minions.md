## Problem Statement:

Minions are of 26 types, from 'a' to 'z'. If two Minions of same type finds themselves besides each other, they will kill each other.

You are given a string of Minions. You need to find the final surviving string of Minions, after all the killings. i.e Further No Minion will kill other Minion.

If no Minion survived a after all the fighting, print "-1".


## Hint:

Think of a way to simulate the Minions' fights and eliminate adjacent pairs of the same type.


## Short Explanation:

Given a string of Minions, we need to simulate their fights. When two Minions of the same type are adjacent, they will eliminate each other. We must find the final surviving string of Minions or return -1 if no Minion survives.

## Detailed Explanation:

To solve this problem, we can use a stack data structure. We iterate through the input string of Minions character by character. For each character, we check if the stack is empty or if the top character on the stack is the same as the current character. If they are the same, we pop the character from the stack (eliminating the pair), and if they are different, we push the current character onto the stack.

After processing the entire string, the stack will contain the surviving Minions. We convert the stack back to a string, and that is the final answer. If the stack is empty, it means no Minion survived, so we return -1.

## Pseudo Code:

function findSurvivingMinions(N, S):
    Initialize an empty stack
    Iterate through each character in S:
        If the stack is not empty and the top character is the same as the current character:
            Pop the top character from the stack
        Else:
            Push the current character onto the stack
    If the stack is empty:
        Return -1
    Else:
        Convert the stack to a string and return it as the surviving Minions

N = Read input for N
S = Read input for S
result = findSurvivingMinions(N, S)
Print result



## Time Complexity:

The time complexity of this algorithm is O(N), where N is the length of the input string S. We iterate through the string once, and each character is pushed and popped from the stack at most once.

## Space Complexity:

The space complexity of this algorithm is O(N) as well. In the worst case, the stack may contain all the characters of the input string.