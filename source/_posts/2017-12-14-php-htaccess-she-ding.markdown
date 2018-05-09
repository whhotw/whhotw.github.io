---
layout: post
title: ".htaccess 設定"
date: 2017-12-14 03:44:11 +0800
comments: true
categories: php
---
其實用 `PHP` 寫的東西不是很多，再加上一直都不算是網頁端的開發者，所以很多相關的知識其實不太熟悉，哈；目前台灣傳統的資訊公司（新創應該都是 `Node.js` 了），應該還是用 `PHP` 來開發網路應用，一來當然是廣大社群的力量（有問題 google 一下，基本上都能找到解法），很多很棒的第三方套件，再加上建置成本相對便宜的因素。最近民間友人拜託看一個 bug ，就當作工作之餘也摸一些網頁的東西，並且趁這次記錄一下。註：我是 OSX 的環境 

##遇到 http 500 internal server error
確定 apache 的模組有載入 

```
$ vim /etc/apache2/httpd.conf

...
LoadModule rewrite_module libexec/apache2/mod_rewrite.so
...
```

##開啟 .htaccess 功能
類似這樣

```
<Directory "/myweb">
	...
	AllowOverride all
	...
</Directory>
```

## .htaccess 檔案內容
```
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteBase /
    #RewriteCond $1 !^(index\.php|assets|.*\.ipa|images|swf|uploads|js|css|assets|robots\.txt|$)
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule ^(.*)$ index.php?/$1 [L,QSA]
</IfModule>
```