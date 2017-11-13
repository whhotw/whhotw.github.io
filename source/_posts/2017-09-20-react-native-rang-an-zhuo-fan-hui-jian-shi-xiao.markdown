---
layout: post
title: "React Native - 讓安卓返回鍵失效"
date: 2017-09-20 17:28:47 +0800
comments: true
categories: react-native
---
設定 `overrideBackPress=true` 

```
this.props.navigator.showLightBox({
    screen: '',
    passProps: {},
    style: {},
    overrideBackPress: true
});
```