---
layout: post
title: "JavaScript Singleton"
date: 2017-09-12 09:52:10 +0800
comments: true
categories: 
---
```
static instance = null;
static createInstance() {
	return new Class();
}

static getInstance() {
	if (!Class.instance) {
		Class.instance = Class.createInstance();
	}

	return Class.instance;
}
```