# Min Stack

``` py
class MinStack(object):

    def __init__(self):
        self.stack = []
        self.minstack = []

    def push(self, x):
        self.stack.append(x)
        if self.minstack:
            x = min(self.minstack[-1], x)
        self.minstack.append(x)

    def pop(self):
        self.minstack.pop()
        self.stack.pop()

    def top(self):
        return self.stack[-1]

    def getMin(self):
        return self.minstack[-1]
```