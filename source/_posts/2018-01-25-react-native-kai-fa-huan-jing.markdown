---
layout: post
title: "React-Native 開發環境"
date: 2018-01-25 10:58:08 +0800
comments: true
categories: react-native
---
[React-Native Getting Started](https://facebook.github.io/react-native/docs/getting-started.html)

###Homebrew
[安裝](https://brew.sh) OSX 的套件管理包

```
▶ brew -v
Homebrew 1.4.3
Homebrew/homebrew-core (git revision a76c8; last commit 2018-01-11)
```

###Node

```
brew install node
▶ node -v
v8.9.4
```

###Watchman
追蹤檔案的變化

```
brew inatall watchman
▶ watchman -v
4.9.0
```

###Command-Line
指令工具用於創建專案，初始化，更新，打包服務等任務

```
npm install react-native-cli
▶ react-native -v
react-native-cli: 2.0.1
```

###Flow、Yarn
檢查 `JavaScript` 語法錯誤與更高效能的第三方套件管理工具，可取代 `npm`

```
brew install flow
npm install -g yarn 
▶ yarn -v
1.3.2
```