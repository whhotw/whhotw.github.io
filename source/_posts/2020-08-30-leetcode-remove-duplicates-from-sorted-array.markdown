---
layout: post
title: "LeetCode #26 Remove Duplicates from Sorted Array"
date: 2020-08-30 22:17:07 +0800
comments: true
categories: leetcode
---
```
var removeDuplicates = function(nums) {
    let previous = nums[0]
    let i = 1;
    while (i <= nums.length) {
        if (nums[i] === previous) {
            nums.splice(i, 1)
            continue
        } else {
            previous = nums[i]
        }
        i++
    }
    return nums.length
};
```