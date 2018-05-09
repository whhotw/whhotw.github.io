---
layout: post
title: "React Native - Setting onMessage on a WebView overrides existing values of window.postMessage"
date: 2017-09-13 15:56:07 +0800
comments: true
categories: react-native
---
最近在玩 React Native 遇到的一個問題。假如想讓 WebView 與 React Native 溝通的話可以用 `onMessage` 這個介面，但是假如原本的網頁內容你不確定怎麼寫的，可能會遇到 `Setting onMessage on a WebView overrides existing values of window.postMessage`
這樣的錯誤訊息，搜尋了一下解法，紀錄一下

```
const patchPostMessageFunction = () => {
  const originalPostMessage = window.postMessage;

  const patchedPostMessage = (message, targetOrigin, transfer) => {
    originalPostMessage(message, targetOrigin, transfer);
  };

  patchedPostMessage.toString = () => String(Object.hasOwnProperty).replace('hasOwnProperty', 'postMessage');

  window.postMessage = patchedPostMessage;
};

const patchPostMessageJsCode = `(${String(patchPostMessageFunction)})();`;
```