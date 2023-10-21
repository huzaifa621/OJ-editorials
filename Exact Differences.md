### Editorial

**Problem Analysis:**

Given an array of integers, the task is to count the number of pairs of indices (i, j) such that i < j and \(a_j - a_i = j - i\). In other words, the problem requires finding pairs of indices where the difference between the values at those indices is equal to the difference between the indices themselves.

**Approach:**

- ### Brute force: 
Use Nested loop where the outer loop will run from 0 to n and the inner loop will run from 1 to n. Inside the 
iteration compare the pairs with the if condition of a[j]-a[i] = j-i

- ### Optimized approach:
a[j] - a[i] = j - i
a[i] - i = a[j] - j
To solve this problem efficiently, we can use a hashmap (dictionary in Python) to store the differences \(a_j - a_i\) and their corresponding frequencies. While iterating through the array, for each index i, we calculate the difference \(a_j - a_i\) and check if this difference exists in the hashmap. If it does, we add the frequency of that difference to the total count. After that, we update the hashmap with the current difference by incrementing its frequency.

**Pseudocode:**

``` 
for each test case:
    - initialize an empty hashmap freq_map
    - initialize a variable count to 0
    - iterate through the array using index i:
        - calculate the difference diff = array[i] - i
        - if diff exists in freq_map:
            - add the frequency of diff to count
        - increment the frequency of diff in freq_map
    - print count
```

**Time Complexity:**

The time complexity of this approach is O(N), where N is the number of integers in the array. We iterate through the array once, and each hashmap operation (insertion and lookup) takes constant time on average.

**Space Complexity:**

The space complexity is O(N) because we use a hashmap to store the differences and their frequencies. In the worst case, where all differences are unique, the hashmap will contain N key-value pairs.

**Sample Output 1:**

```
1
3
3
10
```

In this example, the first test case has one pair (3,5), the second test case has three pairs (1,2), (2,3), and (1,3), the third test case has three pairs (1,3), (1,4), and (3,4), and the fourth test case has ten pairs (1,6), (2,6), (3,6), (4,6), (1,5), (2,5), (3,5), (1,4), (2,4), and (3,4).