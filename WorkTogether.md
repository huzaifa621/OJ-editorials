Problem Analysis:

Sachin and Ankush are playing a game together with a total of n levels. Sachin can pass p levels, and Ankush can pass q levels. They have specific levels they can pass, and they want to work together optimally to pass the entire game.

The task is to determine whether, by working together optimally, they can pass all the levels.

Approach:
Bruteforce: Use Nested loop if all the levels from 1-n are present in the levels that Sachin & Ankush can pass.

Optimized: To solve this problem, we can consider the union of the levels that Sachin and Ankush can pass. If the union contains all n levels, then they can work together optimally and pass the entire game. Otherwise, there are some levels left unpassed, and they cannot win the game together.

Pseudocode:

1. Create an empty dictionary "passed_levels" to store the levels as keys.
2. Iterate through sachin_levels:
    - Add each level to the "passed_levels" dictionary as a key with value 1.
3. Iterate through ankush_levels:
    - Add each level to the "passed_levels" dictionary as a key with value 1.
4. If the size of the keys in "passed_levels" is equal to n, print Winner.
5. Else, print Loser.

Time Complexity:

The time complexity of this approach is O(p + q), where p and q are the number of levels Sachin and Ankush can pass, respectively. We iterate through their levels to create the dictionary.

Space Complexity:

The space complexity is O(p + q) because we use a dictionary to store the levels that Sachin and Ankush can pass.

This approach utilizes a dictionary where the keys represent the levels that Sachin and Ankush can pass. By checking the size of the dictionary, we can determine if they can pass all levels together.
