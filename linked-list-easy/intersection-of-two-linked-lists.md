# Intersection of Two Linked Lists

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def getIntersectionNode(self, headA, headB):
        """
        :type head1, head1: ListNode
        :rtype: ListNode
        """
        curA, curB = headA, headB
        len_a = self.lengthCount(curA)
        len_b = self.lengthCount(curB)

        curA, curB = headA, headB

        if len_a > len_b:
            for _ in xrange(len_a - len_b):
                curA = curA.next
        elif len_a < len_b:
            for _ in xrange(len_b - len_a):
                curB = curB.next


        while curA != curB:
            curA = curA.next
            curB = curB.next

        return curA

    def lengthCount(self,head):
        count = 0;
        while head:
            count = count+1
            head = head.next

        return count
```

