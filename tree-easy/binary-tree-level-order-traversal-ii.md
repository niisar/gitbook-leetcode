# Binary Tree Level Order Traversal II

``` py
# in
    3
   / \
  9  20
    /  \
   15   7
   
# out
[
  [15,7],
  [9,20],
  [3]
]

class Solution(object):
    def levelOrderBottom(self, root):
        """
        :type root: TreeNode
        :rtype: List[List[int]]
        """
        self.res = []

        def dfs(root, level):
            if not root:
                return

            if len(self.res) == level:
                self.res.append([])
            self.res[level].append(root.val)

            left = dfs(root.left, level + 1)
            right = dfs(root.right, level + 1)

        dfs(root, 0)
        return self.res[::-1]
```