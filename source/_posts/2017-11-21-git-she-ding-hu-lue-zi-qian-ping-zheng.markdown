---
layout: post
title: "git 設定忽略自簽憑證"
date: 2017-11-21 17:07:54 +0800
comments: true
categories: git
---
公司的 git server 為了安全性有掛上自簽憑證，但是 git `http.sslVerify` 預設 `true` 因此會無法上傳 code，這時候可以手動修改 `http.sslVerify` 這個值

```
git config --global http.sslVerify false
```

想要安全一些的話就設定自簽憑證路徑

```
git config --system http.sslCAPath /path/to/cacerts
```

以上兩種都可行