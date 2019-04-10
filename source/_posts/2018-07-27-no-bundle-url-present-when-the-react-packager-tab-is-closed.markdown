---
layout: post
title: "No bundle url present: when the React Packager tab is closed"
date: 2018-07-27 18:17:11 +0800
comments: true
categories: react-native
---
當 Info.plist 中設定成下圖時，可能會無法在 DEBUG 模式下正常執行

{% img /assets/Screen-Shot-2018-07-27.png 1080 1920 %}

解決辦法

```
remove "Allow Arbitrary Loads in Web Content"
```
