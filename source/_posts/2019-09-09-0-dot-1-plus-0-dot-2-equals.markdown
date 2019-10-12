---
layout: post
title: "0.1 + 0.2 = ?"
date: 2019-09-09 23:14:37 +0800
comments: true
categories: javascript
---
```
var a = 0.1 + 0.2;
if (a === 0.3) {
	// never into, why?
}
```

這段程式碼有很高的機率會是 `false` 甚至可以說一定會是 `false`，為什麼呢？市面上常見的程式語言，理論上都會遇到這個陷阱，尤其是像 `js` 這類的動態語言。當然！這也不是什麼困難問題，隨便 google 一下就知道怎麼解了，這邊我就簡單記錄一下，順帶一提，根本原因是系統對於浮點數的儲存原理，有興趣請自行上網搜尋。

##解法

###[Number.EPSILON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/EPSILON)

利用相減後的差額是否小於 `Number.EPSILON` 來判定是否成立

```
if (Math.abs(a - 0.3) < Number.EPSILON) {
	// if true, a = 0.3
}
```

###[Number.prototype.toPrecision()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toPrecision)

[參考這篇](https://github.com/camsong/blog/issues/9)