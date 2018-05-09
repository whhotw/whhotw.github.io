---
layout: post
title: "React Native Navigation 顯示 Modal 透明背景"
date: 2018-03-08 19:15:14 +0800
comments: true
categories: react-native
---
不透明的背景

{% img /assets/Simulator%20Screen%20Shot%20-%20iPhone%208%20-%202018-03-08%20at%2019.17.36.png 360 640 %}

透明的背景

{% img /assets/Simulator%20Screen%20Shot%20-%20iPhone%208%20-%202018-03-08%20at%2019.27.42.png 360 640 %}

```
static navigatorStyle = {
	screenBackgroundColor: 'transparent',
	modalPresentationStyle: 'overFullScreen'
}
```