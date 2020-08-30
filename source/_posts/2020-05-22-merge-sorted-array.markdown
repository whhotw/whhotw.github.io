---
layout: post
title: "Leetcode #88 Merge Sorted Array"
date: 2020-05-22 02:45:22 +0800
comments: true
categories: leetcode
---
曾經面試時被問到過。

```
var merge = function(nums1, m, nums2, n) {
    while(m + n > 0) {
        if (n <= 0) {
            break;
        }
        nums1[m + n - 1] = (nums1[m - 1] >= nums2[n - 1]) ? nums1[--m] : nums2[--n];
    }
};
```