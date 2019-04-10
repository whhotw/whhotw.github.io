---
layout: post
title: "Install RVM"
date: 2018-10-18 01:34:36 +0800
comments: true
categories: 
---
原本想說用 `brew` 安裝 `ruby` 結果沒想到版本相依的問題，這麼難搞，用了好幾天，實在沒辦法！最後還是用決定 [RVM](https://rvm.io) 了

```
\curl -sSL https://get.rvm.io | bash -s stable
rvm install x.x.x (e.g. 2.5.1)
```

#Usage

```
rvm list
=> ruby-2.3.7 [ x86_64 ]
   ruby-2.4.4 [ x86_64 ]
 * ruby-2.5.1 [ x86_64 ]

# => - current
# =* - current && default
#  * - default

rvm use x.x.x
Using $HOME/.rvm/gems/ruby-x.x.x
```

#RubyGems Environment

```
gem env
RubyGems Environment:
  - RUBYGEMS VERSION: 2.7.7
  - RUBY VERSION: 2.3.7 (2018-03-28 patchlevel 456) [x86_64-darwin17]
  - INSTALLATION DIRECTORY: $HOME/.rvm/gems/ruby-2.3.7
  ...
```