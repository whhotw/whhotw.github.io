---
layout: post
title: "set git submodule don't use https"
date: 2019-07-06 20:47:55 +0800
comments: true
categories: git
---
In `.gitmodules` file. Set repository url need use git@github.com:$NAME.git if is https:// will meet SSH authentication failed.

```
[submodule "$NAME"]
  path = $PATH
  url = git@github.com:genesis-healthcare/$NAME.git
  branch = master
```
