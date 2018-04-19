# Palindrome Linked List

```python
# Given a singly linked list, determine if it is a palindrome.
# Time: O(n)
# Space: O(1)

class Solution(object):
    def isPalindrome(self, head):
        """
        :type head: ListNode
        :rtype: bool
        """
        slow = fast = head

        while fast and fast.next:
            fast = fast.next.next
            slow = slow.next

        prev = None

        #Reverse here
        while slow:
            nxt = slow.next
            slow.next = prev
            prev = slow
            slow = nxt

        tail = prev

        while head and tail:
            if head.val != tail.val:
                return False
            head = head.next
            tail = tail.next
        return True
```

