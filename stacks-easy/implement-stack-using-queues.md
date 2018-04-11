# Implement Stack using Queues

``` py
class MyStack(object):

    def __init__(self):
        self.queue = []

    def push(self, x):
        self.queue.append(x)

    def pop(self):
        if self.queue:
            for _ in xrange(len(self.queue) - 1):
              self.queue.append(self.queue.pop(0))
            return self.queue.pop(0)
        else: return []

    def top(self):
        temp = 0
        for _ in xrange(len(self.queue)):
            temp = self.queue.pop(0)
            self.queue.append(temp)
        return temp

    def empty(self):
        return False if self.queue else True

# Your MyStack object will be instantiated and called as such:
# obj = MyStack()
# obj.push(x)
# param_2 = obj.pop()
# param_3 = obj.top()
# param_4 = obj.empty()
```