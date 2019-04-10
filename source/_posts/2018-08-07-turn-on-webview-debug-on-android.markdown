---
layout: post
title: "Turn on WebView Debug on Android"
date: 2018-08-07 17:51:02 +0800
comments: true
categories: android
---
[官方文件](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/webviews)

在 activity 起來的時候 enable

```
@Override
 	public void onCreate() {
 	super.onCreate();
	SoLoader.init(this, /* native exopackage */ false);
	WebView.setWebContentsDebuggingEnabled(true);
}
```