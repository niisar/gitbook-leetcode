# Swap Nodes in Pairs

``` py
# Given a linked list, swap every two adjacent nodes and return its head.
# For example,
# Given 1->2->3->4, you should return the list as 2->1->4->3.

class Solution(object):
    def swapPairs(self, head):
        if not head:
            return head

        guard = p0 = ListNode(0)
        guard.next = head

        while p0.next and p0.next.next:
            p1 = p0.next
            p2 = p0.next.next 

            p0.next = p2
            p1.next = p2.next
            p2.next = p1

            p0 = p0.next.next

        return guard.next
```