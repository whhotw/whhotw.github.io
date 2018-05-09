---
layout: post
title: "LeetCode #717. 1-bit and 2-bit Characters"
date: 2018-01-31 10:38:51 +0800
comments: true
categories: leetcode
---
```
const len = bits.length - 1;
let i = 0;
while (i < len) {
    if (bits[i] === 0) {
        i++;
    } else if (bits[i] === 1) {
        if (i + 1 === len) {
            return false;
        }
        
        i += 2;
    }
}
    
return true;
```