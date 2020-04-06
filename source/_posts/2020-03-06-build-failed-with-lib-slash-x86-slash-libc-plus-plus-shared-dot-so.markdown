---
layout: post
title: "Build Failed with lib/x86/libc++_shared.so"
date: 2020-03-06 00:53:46 +0800
comments: true
categories: android
---
Add codes in `build.gradle` as below

```
packagingOptions {
    pickFirst 'lib/x86/libc++_shared.so'
    pickFirst 'lib/x86_64/libc++_shared.so'
    pickFirst 'lib/arm64-v8a/libc++_shared.so'
    pickFirst 'lib/armeabi-v7a/libc++_shared.so'
}
```