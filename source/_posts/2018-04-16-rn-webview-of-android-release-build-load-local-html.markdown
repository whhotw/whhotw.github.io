---
layout: post
title: "RN WebView of android release build load local HTML"
date: 2018-04-16 11:52:04 +0800
comments: true
categories: react-native
---
`RN` 中的 WebView 可以使用 `require()` 讀取靜態的 HTML 檔案。但是安卓的 `release` 階段要用 `file:///android_asset/xxx` 的寫法，否則會無法正常執行

靜態檔案放在 android project 的 assets 底下

{% img /assets/ScreenShot2018-04-16at1157.png 1080 1920 %}

