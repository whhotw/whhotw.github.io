---
layout: post
title: "OSX 上解決 port 被使用的問題"
date: 2017-09-07 10:18:55 +0800
comments: true
categories: command
---
在開發的時候會需要開一些服務，來幫助除錯或是測試程式，但有時候會遇到無法正常啟動的問題，這時候可以檢查看看是不是舊服務把 port 佔住，導致新的服務開不起來，可以使用 `lsof(list open files)` 這個指令檢查一下把不要的服務 kill

```
lsof -t -i:${PORT}
kill -9 $(lsof -t -i:${PORT})
```

#####-i 顯示所有端口<br/>-i:${PORT} 顯示指定端口<br/>-t 只印出 PID