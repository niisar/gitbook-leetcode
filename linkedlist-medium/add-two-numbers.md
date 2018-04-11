# Add Two Numbers

``` py
# You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.
# You may assume the two numbers do not contain any leading zero, except the number 0 itself.
# Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
# Output: 7 -> 0 -> 8

class Solution(object):
    def addTwoNumbers(self, n1, n2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        ret = ListNode(0)
        temp = ret
        carry = 0
        while n1 or n2 or carry:
            result = carry
            if n1:
                result += n1.val
                n1 = n1.next
            if n2:
                result += n2.val
                n2 = n2.next
            newNode = ListNode(result % 10)
            carry = result / 10
            temp.next = newNode
            temp = temp.next
        return ret.next
```