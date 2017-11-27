---
layout: post
title: "Leetcode #357. Count Numbers with Unique Digits"
date: 2017-11-16 14:44:14 +0800
comments: true
categories: leetcode
---
*Given a non-negative integer n, count all numbers with unique digits, x, where 0 ≤ x < 10n.
Example:
Given n = 2, return 91. (The answer should be the total numbers in the range of 0 ≤ x < 100, excluding [11,22,33,44,55,66,77,88,99])*

起初用暴力解但效率只能到達 n=6, 以上就會 time limit exceeded

**我自己想的解法**

```
var countNumbersWithUniqueDigits = function(n) {
    console.log(Math.pow(10, n));
    let maxNum = Math.pow(10, n);
    let count = 0;
    for (let i = 10; i < maxNum; i++) {
        let arr = i.toString().split('');
        let set = new Set(arr);
        if (arr.length !== set.size) {
            count++;
        }
    }
    
    return maxNum - count;
};
```

**參考解答後優化的解法**

```
var countNumbersWithUniqueDigits = function(n) {
    if (n === 0) {
        return 1;
    } else {
        let v = 9;
        for (let i = 1; i < n; i++) {
            v *= (11 - i - 1);
        }
        
        return countNumbersWithUniqueDigits(n - 1) + v;
    }
};
```

主要是運用動態規劃的方式

```
f(1)=f(0)+9
f(2)=f(1)+9*9
f(3)=f(2)+9*9*8
...
f(9)=f(8)+9*8*7*6*5*4*3*2
f(10)=f(9)+9*8*7*6*5*4*3*2*1
```