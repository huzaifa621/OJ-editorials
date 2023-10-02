# Find Id of Brackets - Editorial

**Difficulty**: Medium
**Prerequisite**: Stack Data Structure

## Problem Statement

The problem asks us to assign an ID to each opening and closing bracket in a given string of parentheses. The string may not necessarily be balanced. We need to assign 1-based IDs to the brackets.

## Hint

Consider using a stack data structure to keep track of the opening brackets and assign IDs as you encounter closing brackets.

## Short Explanation

To solve this problem, we can use a stack data structure. Initialize an empty stack to keep track of opening brackets' positions and an array to store the IDs of the brackets. Iterate through the string character by character. For each opening bracket, push its position onto the stack. When encountering a closing bracket, pop the top element from the stack and assign IDs to both the opening and closing brackets. Finally, output the IDs.

## Detailed Explanation

1. Initialize an empty stack to keep track of opening brackets' positions and an array to store the IDs of the brackets.

2. Iterate through the given string character by character:

   a. If the current character is an opening bracket (i.e., '('), push its position onto the stack.

   b. If the current character is a closing bracket (i.e., ')'), pop the top element from the stack. This element represents the opening bracket that matches the current closing bracket. Assign an ID (1-based) to both the opening and closing brackets using their positions. Store these IDs in the array.

3. After processing the entire string, we will have assigned IDs to all the brackets. Print these IDs as space-separated integers.

## Pseudo Code

```plaintext
int T // number of test cases
for each test case:
    int N // length of the string
    string s // input string
    stack<int> openingBrackets // stack to store opening brackets' positions
    array<int> bracketIDs(N, 0) // array to store bracket IDs
    int currentID = 1 // initialize the current ID
    for i from 0 to N-1:
        if s[i] is '(':
            push i onto openingBrackets // push the position of the opening bracket
        else:
            int openingIndex = openingBrackets.top() // get the position of the matching opening bracket
            openingBrackets.pop() // remove the matching opening bracket position from the stack
            bracketIDs[openingIndex] = currentID // assign ID to opening bracket
            bracketIDs[i] = currentID // assign ID to closing bracket
            currentID++ // increment the current ID
    print bracketIDs as space-separated integers
```
## Time Complexity
The time complexity of this approach is O(N) for each test case, where N is the length of the string. We iterate through the string once, and the stack operations are also constant time.

## Space Complexity
The space complexity is O(N) for each test case. We use a stack to store opening brackets' positions and an array to store bracket IDs, both of which can have a maximum size of N.
