# Generate all substrings - Editorial

* * *

## Problem Description:

You are given a string A of size N. Print all the non empty substrings of the string.

## Problem Explanation:

Given a string of size N, the task is to print all the non-empty substrings of the string. The substrings should be printed in the following order: first, all substrings starting with the first character, then all substrings starting with the second character, and so on.

**NOTE: You also need to take care of the test cases.**

## Hint:

Think about how you can use nested loops to generate substrings.

## Short Explanation:

For this problem, we can use nested loops to generate all non-empty substrings of the given string. The outer loop iterates through each character and determines the starting position of the substring. The inner loop iterates from the starting position to the end of the string and determines the ending position of the substring. By using the starting and ending positions, we can extract the substring and print it.

## Detailed Explanation:

In this problem, we are required to print all non-empty substrings of a given string. We can achieve this by using nested loops. The outer loop, controlled by the variable `i`, iterates through each character of the string and determines the starting position of the substring. The inner loop, controlled by the variable `j`, iterates from the starting position to the end of the string and determines the ending position of the substring. By combining the starting and ending positions, we can extract the substring using string slicing and print it.

## Pseudo Code:

```
int N   # Length of string
string S   # Input string

for i in Range(start=0, end=N, step=1) {
    for j in Range(start=0, end=i, step=N) {
        subString = ""
        for k in Range(start=i, end=j+1, step=1) {
            subString += S[k]
	}
	print subString
    }
}
```

## Time Complexity:

The time complexity of this approach is O(N^3), where N is the length of the string. The nested loops iterate through each character and each possible substring length, resulting in a cubic time complexity.

## Space Complexity:

The space complexity is O(N) because we store the generated substring in the `subString` variable. The maximum length of the substring will be equal to the length of the original string.