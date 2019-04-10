---
layout: post
title: "react-native-webrtc crash on running device"
date: 2018-05-24 16:05:35 +0800
comments: true
categories: react-native
---
[react-native-webrtc](https://github.com/oney/react-native-webrtc) 跑在安卓實機的時候一直閃退，找了好久終於找到解法

[參考這個issues](https://github.com/oney/react-native-webrtc/issues/230)

proguard rule 裡面加入

```
-keep class org.webrtc.** { *; }
```