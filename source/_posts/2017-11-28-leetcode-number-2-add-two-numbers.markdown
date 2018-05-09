---
layout: post
title: "LeetCode #2. Add Two Numbers"
date: 2017-11-28 17:31:11 +0800
comments: true
categories: leetcode
---
*You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.*

*You may assume the two numbers do not contain any leading zero, except the number 0 itself.*

*Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8*

>相加兩個 linked lists

兩個 list 不一定會是等長，因此當沒有下一個節點的時候會新增一個假的節點，在下一回合檢查的時候 `if (!l1.next && !l2.next)` 為真即最後回合。

PS. 處理進位問題不是很漂亮應該有更好的寫法！

```
var addTwoNumbers = function(l1, l2) {
    if (l1 && l2) { 
        let val = l1.val + l2.val;
        let l = new ListNode(val % 10);
        
        if (!l1.next && !l2.next) {
            l.next = (val > 9 ? new ListNode(1) : null);
            return l;
        }
        
        if (!l1.next) {
            l1.next = new ListNode(0);
        }
        
        if (!l2.next) {
            l2.next = new ListNode(0);
        }
        
        if (val > 9) {
            if (l1.next) {
                l1.next.val++;    
            } else {
                l1.next = new ListNode(1);
            }
        }
        
        l.next = addTwoNumbers(l1.next, l2.next);    
        return l;
    } else {
        return null;
    }
};
```