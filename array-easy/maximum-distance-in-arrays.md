## Problem
Given `m` arrays, and each array is sorted in ascending order. Now you can pick up two integers from two different arrays (each array picks one) and calculate the distance. We define the distance between two integers `a` and `b` to be their absolute difference `|a-b|`. Your task is to find the maximum distance.

## Solution
``` py
class Solution(object):
    def maxDistance(self, nums):
        """
        :type arrays: List[List[int]]
        :rtype: int
        """
        low = float('inf')
        high = float('-inf')
        res = 0
        for num in nums:
            # We can use num[0] && num[-1] only because these lists are sorted
            res = max(res, max(high - num[0], num[-1] - low))
            low = min(low, min(num))
            high = max(high, max(num))
        return res
```