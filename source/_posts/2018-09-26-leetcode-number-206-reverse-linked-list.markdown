---
layout: post
title: "LeetCode #206 Reverse Linked List"
date: 2018-09-26 16:01:35 +0800
comments: true
categories: leetcode
---
面試經典題

```
var reverseList = function(head) {
    let prev = null;
    let curr = head;
    let next = null;
    while (curr) {
        next = curr.next;
        curr.next = prev;
        prev = curr;
        curr = next;
    } 
    
    return prev;
};
```