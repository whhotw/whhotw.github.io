---
layout: post
title: "LeetCode #493. Reverse Pairs"
date: 2018-01-28 10:48:40 +0800
comments: true
categories: leetcode
---
```
for (let i = 0; i < nums.length; i++) {
    for (let j = 0; j < nums.length; j++) {
        if (i < j && nums[i] > 2 * nums[j]) {
            x++;
        }
    }
}
```
>Big O(n<sup>2</sup>)