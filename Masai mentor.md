### Editorial

**Problem Analysis:**

In this problem, each student has a rating, and they want to find the highest possible rating of a mentor they can choose. A student j can be a mentor of student i only if `rating[j] ≤ 2 × rating[i]`. Each student should have the strongest possible mentor according to this constraint.

**Approach:**

To solve this problem, we can sort the students' ratings in ascending order and find the highest possible mentor for each student. For each student, we need to find the first student whose rating is greater than or equal to half of the current student's rating, and assign this student as the mentor.

**Pseudocode:**

```plaintext
Input:
- int T // number of test cases
- for each test case:
    - int n // number of students
    - int[] ratings // ratings of students
    
Output:
- For each student, print the maximum possible rating of their mentor or -1 if there are no possible mentors.

for each test case:
    - Sort ratings in ascending order
    - for i from 0 to n-1:
        - Find the index j where ratings[j] is greater than or equal to half of ratings[i]
        - if j < n:
            - print ratings[j]
        - else:
            - print -1
```

**Time Complexity:**

The time complexity of this approach is O(n log n) for sorting the ratings. For each student, we perform a binary search, which takes O(log n) time. Overall, the time complexity is O(n log n).

**Space Complexity:**

The space complexity is O(n) for storing the ratings.