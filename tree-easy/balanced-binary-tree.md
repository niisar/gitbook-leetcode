# Balanced Binary Tree

## Question

Given a binary tree, determine if it is height-balanced.

> A binary tree in which the depth of the two sub trees of _every_ node never differ by more than 1.

The Tree below will return **True**.

![](../.gitbook/assets/1.png)

Tree below will return **False**.

![](../.gitbook/assets/2.png)

## Solution \(Recursive\)

{% tabs %}
{% tab title="Python" %}
{% code-tabs %}
{% code-tabs-item title="Recursively Balance the Binary Tree" %}
```python
class Solution(object):
        def isBalanced(self, root):
            def check(root):
                if root is None:
                    return 0
                left  = check(root.left)
                right = check(root.right)
                if left == -1 or right == -1 or abs(left - right) > 1:
                    return -1
                return 1 + max(left, right)

            return check(root) != -1
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="Javascript" %}
todo
{% endtab %}

{% tab title="CSharp" %}
todo
{% endtab %}
{% endtabs %}

## Solution \( Iterative\)

{% tabs %}
{% tab title="Python" %}
{% code-tabs %}
{% code-tabs-item title="Iteratively Balance the Binary Tree" %}
```python
class Solution(object):
    def isBalanced(self, root):
        stack, node, last, depths = [], root, None, {}
        while stack or node:
            if node:
                stack.append(node)
                node = node.left
            else:
                node = stack[-1]
                if not node.right or last == node.right:
                    node = stack.pop()
                    left = depths.get(node.left, 0)
                    right = depths.get(node.right, 0)
                    if abs(left - right) > 1: return False
                    depths[node] = 1 + max(left, right)
                    last = node
                    node = None
                else:
                    node = node.right
        return True


```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="Javascript" %}
todo
{% endtab %}

{% tab title="CSharp" %}
todo
{% endtab %}
{% endtabs %}

## Code Flow

Read on [Google Doc](https://docs.google.com/document/d/1ciAyYImc5Q-TI3eTRBtYL6--DPFBW7LqH6ugc5y9NWs/edit?usp=sharing)

