---
layout: post
title: "經典面試題-翻轉二元樹"
date: 2020-04-28 02:47:51 +0800
comments: true
categories: leetcode
---
```
var invertTree = function(root) {
    if (root == null) return root;
    const tmp = root.left;
    root.left = invertTree(root.right);
    root.right = invertTree(tmp);
    return root;
};
```