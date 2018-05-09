---
layout: post
title: "commit 空資料夾到 git"
date: 2018-01-05 01:29:37 +0800
comments: true
categories: git
---
有些時候想要在 git 上 commit 一個空資料夾時，可以透過 .gitignore 的設定來做到。

###專案結構

```
$ tree -La 1
.
├── .git
├── .gitignore
├── README.md
├── application
├── assets
├── index.php
├── system
└── vendor
```
>假如你有一個空的資料夾，你是沒有辦法 commit 這個檔案到 git 上的，因此可以建立一個 .gitignore 在這個空的資料夾裡

###新的專案結構

```
$ tree -La 1
.
├── .git
├── .gitignore
├── README.md
├── application
├── assets
├── index.php
├── system
├── test
│   └── .gitignore
└── vendor
```

>如此一來將可以 commit

另外你假如想要保留一個 temp 資料夾在 git 上，你可以順便利用這個 .gitignore 

```
$ vim test/.gitignore
*
!.gitignore
```

###使用 [.gitkeep](http://www.ryanwright.me/cookbook/git/gitkeep)

也可以達到一樣的效果