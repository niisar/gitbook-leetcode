# Valid Parentheses

``` py
# ****************
# Descrption:
# 20. Valid Parentheses
# Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.
# The brackets must close in the correct order, "()" and "()[]{}" are all valid but "(]" and "([)]" are not.
# ****************

class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        stack = []

        for char in s:
            if char == '(' or char == '[' or char == '{':
                stack.append(char)
            if char == ')':
                if not stack or stack.pop() != '(':
                    return False
            if char == ']':
                if not stack or stack.pop() != '[':
                    return False
            if char == '}':
                if not stack or stack.pop() != '{':
                    return False
        # Edge for
        # "[" or "{" or "("
        if stack:
            return False
        return True
```