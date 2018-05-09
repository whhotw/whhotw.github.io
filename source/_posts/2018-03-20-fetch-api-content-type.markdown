---
layout: post
title: "Fetch API Content-Type"
date: 2018-03-20 09:38:46 +0800
comments: true
categories: javascript
---
最近用到 js 中的 [fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) 發現 `Content-Type` 會因為參數而改變

例如

```
const options = {
  method,
  headers: {
    Accept: 'application/json',
    'Content-Type': 'application/json', // 指定
  },
  body: params, // 第二張圖
  // body: JSON.stringify(params), // 第一張圖
};
    
return fetch(url, options)
  .then((res) => {
    if (!res.ok) {
      throw new Error('請檢查網路連線');
    }

    return res.json();
  });
```

假如 `params` 沒有用 `JSON.stringify` 的話，實際傳出去的 `Content-Type` 不一定是 `application/json`

我用 wireshark 做的實驗

{% img /assets/Screen%20Shot%202018-03-20%20at%2009.44.19.png 1080 1920 %}

{% img /assets/Screen%20Shot%202018-03-20%20at%2009.44.05.png 1080 1920 %}


