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
Given an array nums of n integers where n > 1,  return an array output such that output[i] is equal 

to the product of all the elements of nums except nums[i].


Example:

```
Input:  [1,2,3,4]
Output: [24,12,8,6]
```
Note: Please solve it without division and in O(n).


Follow up:

Could you solve it with constant space complexity? 

(The output array does not count as extra space for the purpose of space complexity analysis.)
```python
class Solution:
    def productExceptSelf(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        n = len(nums)
        res = [None]*n
        res[0] = 1
        for i in range(1,n):
            res[i] = res[i-1] * nums[i-1]
        
        right = 1
        for i in range(n-1,-1,-1):
            res[i] *= right
            right *= nums[i]
        return res;
        
```
这个题并不难，开始我尝试了一下算所有数字的product然后再遍历整个数组，输出product/当前数字。 后来发现这样做一旦遇到0 基本属于GG
因为所有数字的成乘积就变成了0 处理起来很麻烦 需要很多判断，因为整个数组可能在多个位置出现0。

这个解法的精髓就在于，把本位置以及以前的数字成积算出来放在res[]这个list 里，第二遍遍历的时候从后往前用同样的方法，只不过再乘之前算好
的res 中的数值


---

Feel free to comment on below: