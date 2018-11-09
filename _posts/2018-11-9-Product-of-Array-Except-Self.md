---
layout: post
title:  "LC238. Product of Array Except Self"
date:   2018-11-09
desc: "Given an array nums of n integers where n > 1,  return an array output such that output[i] is equal to the product of all the elements of nums except nums[i]."
keywords: "Array"
categories: [Python]
tags: [Array]
icon: icon-python
---

```python
class Solution:
    def productExceptSelf(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        sumAll = sum(nums)
        result = []
        for i in nums:
            result.append(sum-i)
        return result
        
```

---

Feel free to comment on below: