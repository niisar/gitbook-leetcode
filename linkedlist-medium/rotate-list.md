# Rotate List

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def rotateRight(self, head, k):
        """
        :type head: ListNode
        :type k: int
        :rtype: ListNode
        """
        #Edge
        if not head or not head.next:
            return head

        cur, count = head, 0

        while cur:
            count = count+1
            cur = cur.next

        mod = k % count

        #Edge 2
        if k == 0 or mod == 0:
            return head

        slow = fast = head

        for _ in range(mod):
            fast = fast.next

        while fast.next:
            slow = slow.next
            fast = fast.next

        newHead = slow.next
        fast.next = head
        slow.next = None

        return newHead
```

