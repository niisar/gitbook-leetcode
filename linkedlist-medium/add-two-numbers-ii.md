# Add Two Numbers II

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        n1 = self.list_to_stack(l1)
        n2 = self.list_to_stack(l2)
        stack = self.add_helper(n1,n2)
        result = self.stack_to_list(stack)
        return result 

    def list_to_stack(self, node):
        stack = []
        while node:
            stack.append(node.val)
            node = node.next
        return stack

    def stack_to_list(self, stack):
        head = ListNode(0)
        cur = head
        while stack:
            cur.next = ListNode(stack.pop())
            cur = cur.next
        return head.next

    def add_helper(self, s1, s2):
        res = []
        carry = 0
        while s1 or s2 or carry:
            num1 = s1.pop() if s1 else 0
            num2 = s2.pop() if s2 else 0
            total = num1 + num2 + carry
            res.append(total % 10)
            carry = total/10
        return res
```

