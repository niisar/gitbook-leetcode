# [Path Sum](https://leetcode.com/problems/path-sum/description/)

``` py
class Solution(object):
    def hasPathSum(self, root, sum):
        """
        :type root: TreeNode
        :type sum: int
        :rtype: bool
        """
        #Edge
        if not root:
            return False

        #Process
        if not root.left and not root.right:
            return sum - root.val == 0
        else:
            sum -= root.val

        #Recursion
        left = self.hasPathSum(root.left, sum)
        right = self.hasPathSum(root.right, sum)

        return left or right
```