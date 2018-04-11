# Merge Two Sorted Lists

``` py
class Solution:
    def mergeTwoLists(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        #edge
        if not l1 and not l2:
            return None
        
        node = guard_node = ListNode(0)
        
        while l1 and l2:
            if l1.val <= l2.val:
                node.next = l1;
                l1 = l1.next
            else:
                node.next = l2
                l2 = l2.next
            node = node.next
            
        if l1 or l2:
            node.next = l1 or l2
        
        return guard_node.next
```