### Level : Easy

## Given the head of a singly linked list, return the middle node of the linked list.

## If there are two middle nodes, return the second middle node.

 

Example 1:


Input: head = [1,2,3,4,5]
Output: [3,4,5]
Explanation: The middle node of the list is node 3.
Example 2:


Input: head = [1,2,3,4,5,6]
Output: [4,5,6]
Explanation: Since the list has two middle nodes with values 3 and 4, we return the second one.
 

Constraints:

The number of nodes in the list is in the range [1, 100].
1 <= Node.val <= 100

## Solution:

## Brute Force:
```Python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: ListNode | None) -> ListNode | None:
        count = 0
        temp1,temp = head,head
        while temp.next is not None:
            count += 1
            temp = temp.next
        count += 1
        val = (count // 2) + 1
        i = 1
        while i < val:
            temp1 = temp1.next
            i += 1
        return temp1
```
## TC = O(N+N/2)

## Optimal : Hare and tortoise

```Python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: ListNode | None) -> ListNode | None:
        temp1,temp2 = head,head
        while temp2 is not None and temp2.next is not None:
            temp1 = temp1.next
            temp2 = temp2.next.next
        return temp1    
```

## TC = O(N/2)
