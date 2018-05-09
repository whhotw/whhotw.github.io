---
layout: post
title: "在 OSX 環境下安裝 PHP mcrypt 套件"
date: 2017-12-14 11:09:46 +0800
comments: true
categories: php
---
指令

```
$ brew install mcrypt
$ brew tap homebrew/homebrew-php
$ brew install php56-mcrypt --without-homebrew-php
```
> php.ini 加入 extension, 重啟 apache

網路上找到的解決辦法

<script src="https://gist.github.com/idleberg/24479f34dc5007e50d47.js"></script>