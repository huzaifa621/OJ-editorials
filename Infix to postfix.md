# Infix to Postfix - Editorial

**Difficulty**: Medium

## Algorithm - Infix to Postfix Conversion

1. Scan the entire expression from left to right.
2. If the character is an operand, add it to the final postfix expression as it is the same in postfix and infix expression.
3. If the character is an opening bracket, push it onto the stack.
4. If the character is a closing bracket, pop all the elements from the stack until an opening bracket is encountered. If the opening bracket is not encountered and the stack becomes empty, then the given infix expression is invalid. Brackets in postfix expressions are superfluous, so pop out the bracket without adding it to the postfix expression.
5. If the character is an operator:
   - Pop out all the operators from the stack until the stack becomes empty, or the character at the top of the stack has a lower priority than the current character.
6. After scanning the entire expression, pop off all the elements from the stack until it becomes empty and add them to the final postfix expression.
7. Finally, print the postfix expression.

## Priority Order for Operators

- Priority Order: `(^) > (*,/) > (+,-)`
- Operators at the same level have the same priority.
- Brackets free the expression from priorities.

## Pseudo Code
```
string infixToPostfix(string expression)
    stack<char> operatorsStack
    string postfixExpression
    for each character in expression
        if character is operand
            append it to postfixExpression
        else if character is opening bracket
            push character onto operatorsStack
        else if character is closing bracket
            pop and append operators from operatorsStack to postfixExpression until an opening bracket is encountered
        else (character is an operator)
            while operatorsStack is not empty and operator at the top of the stack has higher or equal precedence than current character
                pop and append the operator from operatorsStack to postfixExpression
            push current character onto operatorsStack
    pop and append any remaining operators from operatorsStack to postfixExpression
    return postfixExpression
```

## Time Complexity

- The time complexity of this algorithm is O(n), where n is the length of the input infix expression.

## Space Complexity

- The space complexity is O(n) due to the stack used to store operators.


