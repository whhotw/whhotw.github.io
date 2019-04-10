---
layout: post
title: "Number() vs parseInt()"
date: 2018-05-09 17:58:06 +0800
comments: true
categories: javascript
---
```
parseInt('123', 10) // 123
parseInt('123abc', 10) // 123
parseInt(undefined, 10) // NaN
parseInt(null, 10) // NaN
parseInt('', 10) // NaN
Number('123') // 123
Number('123abc', 10) // NaN
Number(undefined) // NaN
Number(null) // 0
Number('') // 0
```

數字轉字串

```
String(123) // "123"
`123` // "123"

let a = 123;
a.toString() // "123"
```