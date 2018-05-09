---
layout: post
title: "LeetCode #581. Shortest Unsorted Continuous Subarray"
date: 2018-01-29 18:45:26 +0800
comments: true
categories: leetcode
---
```
let n = nums.map((val) => val);
nums.sort();
    
let l = 0;
let r = n.length;
    
while (l <= r) {
    if (n[l] === nums[l]) {
        l++;
    } else if (n[r] === nums[r]) {
        r--;
    } else {
        break;
    }
}
    
return l > r ? 0 : r - l + 1;
```