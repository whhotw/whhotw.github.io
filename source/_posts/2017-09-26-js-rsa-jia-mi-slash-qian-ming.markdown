---
layout: post
title: "JS RSA 加密/簽名"
date: 2017-09-26 11:14:39 +0800
comments: true
categories: JavaScript
---
大致上的流程就是伺服端生成公私鑰對後，將公鑰儲存在前端。登入時利用公鑰將敏感資料加密傳送給後端。通常我會習慣轉成 base64 後才傳給後端

先安裝 `jsrsasign` 

```
import rs from 'jsrsasign';

let pub = rs.KEYUTIL.getKey(file);
let cipher = rs.KJUR.crypto.Cipher.encrypt(this.state.passwd, pub, 'RSA');
return rs.hextob64(cipher);
```
getKey() 裡面放要使用的鑰匙資訊，像我是透過 `pem` 所以會從檔案中把資訊取出來。 可以使用 `react-native-fs` 存取檔案系統

一開始以為可以透過類似讀圖片的方式 `require('url')` 得到憑證檔案，因為自己的想法是，假如要先手動把一些自定義的檔案放入個別的系統，真的很麻煩。經過了一個下午的努力與 google 的結果，似乎除了圖片目前還沒有自動連結實體檔案的方法，下次有時間研究一下 `rnpm link` 是怎麼做的！雖然是針對套件不過應該可以自己寫個 script 解決我這個問題