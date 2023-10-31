**Editorial: Rooms and Letters**

**Problem Analysis:**

In this problem, we are given information about dormitories in Masai University. Each dormitory has a specific number of rooms, and there are letters with room numbers that need to be delivered. If a letter has only a room number, we have to determine the dormitory number and the room number within that dormitory where the letter should be delivered.

**Approach:**

To solve this problem, we can use the prefix sum technique to determine which dormitory the given room number belongs to. We first calculate the cumulative sum of rooms in the dormitories and store it in a separate array. For each letter's room number, we find the corresponding dormitory by performing a binary search on the prefix sum array.

**Pseudocode:**

```plaintext
Input: int n, m, int[] rooms, int[] letters

Function find_dormitory(rooms, letters):
    dormitory_sum = calculate_prefix_sum(rooms)  # Calculate cumulative sum of rooms in dormitories
    for letter in letters:
        dormitory = binary_search(dormitory_sum, letter)  # Find dormitory using binary search
        room_in_dormitory = letter - dormitory_sum[dormitory - 1]  # Calculate room number within dormitory
        print dormitory, room_in_dormitory

Function calculate_prefix_sum(rooms):
    prefix_sum = [0]  # Initialize prefix sum array with 0
    for i in range(len(rooms)):
        prefix_sum.append(prefix_sum[-1] + rooms[i])  # Calculate cumulative sum
    return prefix_sum

Function binary_search(arr, target):
    left, right = 1, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] >= target and arr[mid - 1] < target:
            return mid  # Found the dormitory
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1

n, m = read number of dormitories and number of letters
rooms = read rooms present in all dormitories
letters = read room numbers written on the letters
find_dormitory(rooms, letters)  # Find and print dormitories and room numbers
```

**Time Complexity:**

The time complexity of this approach is `O(n * log(n) + m * log(n))`, where `n` is the number of dormitories, `m` is the number of letters, and `log(n)` is the complexity of binary search. The prefix sum calculation takes `O(n)` time, and binary search for each letter takes `O(m * log(n))` time.

**Space Complexity:**

The space complexity is `O(n)` for storing the prefix sum array.
