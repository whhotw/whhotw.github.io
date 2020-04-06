---
layout: post
title: "A Network Error from Axios"
date: 2020-03-26 02:22:20 +0800
comments: true
categories: react-native
---
最近合作的專案中，在與後端合作時，遇到一個奇怪的現象，一開始以為是 `bug` 看了 `Axios` 原始碼後才知道，根本是我們的後端亂寫！哈，紀錄一下我的發現，以及我如何解決。

首先是呼叫 API 時，總是會發生錯誤，像我有寫 `Interceptor` 

```
ApiService.interceptors.response.use(
  function(response) {
    // Do something before request is sent
    return response;
  },
  function(error) {
    // Do something with request error
    return error;
  }
);
```
就會一直跑入 function (error) ，但是神奇的地方在於，並不是每一隻 API 都會有問題，因此我就想說查看看 `Axios` 在收到回應後的處理是如何。

正常情況下，收到回應後，會做一些檢查，其中一項是 `Content-Type` ，之後我又比較了正常與不正常的 API 回傳的差異，我發現，在不正常的回傳封包中的標頭竟然沒有帶入 `Content-Type` ，後來問了原因，只是因為後端認為沒有回傳的 `body` 所以不帶。

最後我們把 `Content-Type` 帶入 `body` 維持空值一切就正常了！查了一下，HTTP1.1 的定義，也並沒有把 `Content-Type` 設為必要資訊，所以我想這應該就是 `Axios` 自行決定的吧！