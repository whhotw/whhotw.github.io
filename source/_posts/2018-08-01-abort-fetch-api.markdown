---
layout: post
title: "Abort Fetch API"
date: 2018-08-01 21:46:22 +0800
comments: true
categories: javascript
---
在 [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) 中並沒有原生提供中斷請求的方法。但假設遇到並行事件時，需要取消前一個請求可以怎麼做呢？這時候就可以實作 `Promise` 的物件來解決

```
const promise = new Promise(function (resolve, reject) {
  const f = fetch(url, options).then((res) => {
    if (!res.ok) {
      reject(new Error('something wrong'));
    } else {
      // resolve(res.json());
      resolve('it's work');
    }
  });

  f.abort = function () {
    reject(new Error('abort error'));
  };

  return f;
});
    
promise.then((res) => {
	console.log(res); // it's work
}).catch(e => {
	console.error(e); // something wrong or abort error
});

// call this before resolve
promise.abort();
```