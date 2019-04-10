---
layout: post
title: "LeetCode #23 Merge k Sorted Lists"
date: 2018-10-04 11:49:46 +0800
comments: true
categories: leetcode
---
240ms 差強人意

```
var mergeKLists = function(lists) {
    lists = lists.filter(list => list);
    
    if (lists.length === 0) {
        return null;
    }
    
    const list = new ListNode();
    let next = list;
    
    while (lists.length > 0) {
        let min = 0;
        
        for (let i = 0; i < lists.length; i++) {
            if (lists[i] && lists[i].val < lists[min].val) {
                min = i;
            }
        }
        
        next.val = lists[min].val;
        lists[min] = lists[min].next;
        
        if (!lists[min]) {
            lists.splice(min, 1);
        }
        
        if (lists.length > 0) {
            next.next = new ListNode();
            next = next.next;
        }
    }
    
    return list;
};
```