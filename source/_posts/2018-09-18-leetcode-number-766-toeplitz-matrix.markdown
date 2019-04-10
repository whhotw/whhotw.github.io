---
layout: post
title: "LeetCode #766 Toeplitz Matrix"
date: 2018-09-18 18:58:19 +0800
comments: true
categories: leetcode
---
```
var isToeplitzMatrix = function(matrix) {
    let a = true;
    for (let i = 0; i < matrix.length; i++) {
        let j = 0;
        while (j + 1 < matrix[i].length && i + 1 < matrix.length) {
            console.log(i + 1, j + 1);
            if (matrix[i][j] !== matrix[i + 1][j + 1]) {
                a = false;
            }
            
            j++;
        }
    }
    
    return a;
};
```