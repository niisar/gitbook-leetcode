# Same Tree

```python
class Solution(object):
    def isSameTree(self, p, q):
        #Edge
        if not p or not q:
            return p == q
        else:
            return p.val == q.val and self.isSameTree(p.left, q.left) and self.isSameTree(p.right, q.right)
```

