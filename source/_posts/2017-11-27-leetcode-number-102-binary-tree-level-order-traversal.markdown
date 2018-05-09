---
layout: post
title: "Leetcode #102. Binary Tree Level Order Traversal"
date: 2017-11-27 13:30:41 +0800
comments: true
categories: leetcode
---
分層印出二元樹的元素，自己寫了遞迴的方式，紀錄一下

```
let toArray = (root, arr, level, idx) => {
    if (!root) {
        return null;
    } else {
        if (!arr[level]) {
            arr[level] = [];
        }
        
        arr[level].push(root.val);
    }
    
    toArray(root.left, arr, level + 1, idx * 2);
    toArray(root.right, arr, level + 1, idx * 2 + 1);
};
```