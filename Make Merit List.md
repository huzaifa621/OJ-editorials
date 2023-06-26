# Make Merit List - Editorial

* * *

## Problem Description:

From a college, a group of students applied for 8 positions in the Indian army. Each student will be chosen based on the following criteria:

- Every student has the following 4 details Name, Height, Weight and IQ in the same order.

- IQ is the first priority to choose a particular student , if a student has IQ of 115 and other student has 110 ,print first the name of student having greater IQ .

- If any two students IQ is same then print the student name having greater height if the heights are also same then print the student name having lesser weight.

- If all of these details(height,weight,IQ) are same then first print the lexicographically smaller name.

You have to prepare top 8 students  merit list bases on the above criteria.

Note : You cannot use built-in sort function. Using that can lead to disqualification. Write your own sorting algorithm.

## Problem Explanation:

We have a group of students who have applied for eight positions in the Indian Army. Each student is characterized by their name, height, weight, and IQ, in that order. The selection criteria prioritize IQ, followed by height, weight, and lexicographically smaller names in case of ties. Our task is to create a merit list that ranks the students according to these criteria.



## Short Explanation:

Using a custom sorting algorithm, we will evaluate each student based on their IQ, height, weight, and name. By following the specified order of priorities, we will generate a merit list that ensures fairness and accuracy in selecting the most deserving candidates for the Indian Army.

## Detailed Explanation:
To create a merit list based on the given criteria, we will employ a custom sorting algorithm. We will compare the IQs of each student first and arrange them in descending order. If two or more students have the same IQ, we will consider their height, giving preference to the one with greater height. If the heights are also equal, we will consider their weights, favoring the student with lesser weight. Lastly, if all the details (height, weight, IQ) are the same, we will compare the names lexicographically and arrange them in ascending order.

The custom sorting algorithm can be implemented as follows:

- Read the input containing the number of students, N.
- Create an array or a data structure to store the student information (name, height, weight, IQ).
- Iterate over the input N times and populate the array with the student details.
- Implement a custom sorting algorithm that compares the students based on the given criteria.
- Compare the IQs of two students. If IQ1 > IQ2, student1 is considered greater.
- If IQ1 = IQ2, compare the heights. If height1 > height2, student1 is considered greater.
- If height1 = height2, compare the weights. If weight1 < weight2, student1 is considered greater.
- If height1 = height2 and weight1 = weight2, compare the names lexicographically. If name1 < name2, student1 is - considered greater.
- Perform the sorting algorithm on the array of student information, placing the most deserving candidates at the top.
- Print the names of the top eight students, which represent the merit list.


## Pseudo Code:

```
def compare_students(student1, student2):
    if student1[3] > student2[3]:  # Compare IQs
        return -1  # student1 is considered greater
    elif student1[3] < student2[3]:
        return 1  # student2 is considered greater
    else:
        if student1[1] > student2[1]:  # Compare heights
            return -1
        elif student1[1] < student2[1]:
            return 1
        else:
            if student1[2] < student2[2]:  # Compare weights
                return -1
            elif student1[2] > student2[2]:
                return 1
            else:
                if student1[0] < student2[0]:  # Compare names lexicographically
                    return -1
                elif student1[0] > student2[0]:
                    return 1
                else:
                    return 0  # Names are the same

# Read the number of students, N
N = int(input())

# Create an empty list to store student information
students = []

# Iterate over the input N times and populate the list with student details
for _ in range(N):
    name, height, weight, iq = input().split()
    height = int(height)
    weight = int(weight)
    iq = int(iq)
    students.append([name, height, weight, iq])

# Sort the list of students based on the custom sorting algorithm
students.sort(key=functools.cmp_to_key(compare_students))

```

## Time Complexity:

- Reading the number of students and populating the list: O(N)
- Sorting the list using the custom sorting algorithm: O(N log N)
- Printing the names of the top eight students: O(1) (since we are only printing a fixed number of names)
- Therefore, the overall time complexity of the code is O(N log N) due to the sorting operation.

## Space Complexity:

- Variables for name, height, weight, and IQ: O(1) (since they are individual values)
- List to store student information: O(N) (as it scales linearly with the number of students)
- Custom comparison function: O(1) (as it does not consume additional space proportional to the input size)
- Hence, the space complexity of the code is O(N), where N is the number of students.