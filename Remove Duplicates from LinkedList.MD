Problem Analysis:

The problem involves processing a sorted linked list and removing duplicates from it. The input is given in the form of a linked list, and the task is to modify the list in-place, ensuring that no duplicates exist.

Approach:

Since the linked list is sorted, duplicate nodes will always be adjacent to each other. We can iterate through the list, comparing each node with its next node. If the current node's value is equal to the next node's value, it means there is a duplicate. In this case, we skip the next node by changing the next pointer of the current node to point to the node after the next node.

''''
Input: ListNode head // head of the linked list

current = head // start from the head of the linked list
    
    Inside while Loop:
        if current.value == current.next.value:
            // there is a duplicate, skip the next node
            current.next = current.next.next
        else:
            // move to the next node
            current = current.next


''''

Time Complexity:

The time complexity of this approach is O(N), where N is the number of nodes in the linked list. We iterate through the list once, and in each iteration, we either move to the next node or skip a node.

Space Complexity:

The space complexity is O(1) because we use a constant amount of extra space regardless of the size of the input.