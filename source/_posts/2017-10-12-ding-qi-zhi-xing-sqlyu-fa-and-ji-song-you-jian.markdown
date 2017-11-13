---
layout: post
title: "定期執行SQL語法"
date: 2017-10-12 15:08:30 +0800
comments: true
categories: sql
---
###設定 mysql event schedule
```
CREATE EVENT `<table_name>`.`<event_name>`
ON SCHEDULE EVERY 1 YEAR
ON COMPLETION PRESERVE
ENABLE
DO
insert into field('b') values(now())
```
`DO` 後面就是接一般的 `SQL` 語法新增，刪除，修改等

###顯示 event schedule
`mysql> show processlist;`