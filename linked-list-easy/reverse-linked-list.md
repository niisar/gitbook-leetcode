# Reverse Linked List

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def reverseList(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        cur = head
        prev = None
        while cur:
            next = cur.next #2,3,4,5    3,4,5   4,5     5
            cur.next = prev 
            prev = cur      #1          2,1     3,2,1   4,3,2,1
            cur = next      #2,3,4,5    3,4,5   4,5     5
        head = prev
        return head
```

