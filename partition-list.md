# Partition List

``` py
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def partition(self, head, x):
        """
        :type head: ListNode
        :type x: int
        :rtype: ListNode
        """
        small, large = ListNode(0), ListNode(0)
        cur1, cur2 = small, large
        while head:
            if head.val < x:
                cur1.next = head
                cur1 = cur1.next
            else:
                cur2.next = head
                cur2 = cur2.next
            
            head = head.next
            
        cur2.next = None
        cur1.next = large.next
        
        return small.next
```