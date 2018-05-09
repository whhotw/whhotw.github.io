---
layout: post
title: "Testing iOS Notification with APNs"
date: 2018-01-17 16:24:21 +0800
comments: true
categories: ios
---
設定步驟可以[參考蘋果的官方](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)或是[這篇](https://medium.com/@ankushaggarwal/generate-apns-certificate-for-ios-push-notifications-85e4a917d522)

此篇主要是介紹我自己用的測試工具，Github 上可以抓到[原檔](https://github.com/pubnub/pubnub-support/blob/master/kb/code/push_debug.py)

```
// for production
python push_debug.py aps.pem ${device_token}

// for sandbox
python push_debug.py aps.pem ${device_token} -s
```

###產出PEM檔
從 keychain 導出 p12 檔後需要轉成 pem 

![](https://files.readme.io/bMyAXe1tRjac9USLX1z0_34.jpg)

```
openssl pkcs12 -in aps.p12 -out aps.pem -nodes -clcerts
```