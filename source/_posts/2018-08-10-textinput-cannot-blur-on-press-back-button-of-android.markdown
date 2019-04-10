---
layout: post
title: "TextInput cannot blur on press back button of Android"
date: 2018-08-10 15:23:19 +0800
comments: true
categories: react-native
---
先說一下我是在 RN 0.51，搞不好新版本不會有這問題...

在 Android 平台上遇到的一個小小問題，需求是這樣的，畫面上有 4 個輸入框，我不希望使用者可以手動點擊要輸入的框框是哪一個，因此我鎖住 touch event (用一個 View 遮住)，然後透過 event 來取得 focus。

在 iOS 沒問題，行為都是我預期的那樣，使用者可以透過我準備的按鈕把鍵盤彈起，但在 Android 的時候，假如使用者按 Back Button 把鍵盤收起來（或是系統的行為。如：收到簡訊），就無法在彈起了...

這是為什麼呢？

就我實驗的結果發現，假如使用者不是自己按下鍵盤上的[完成](https://cdn.wccftech.com/wp-content/uploads/2016/12/Google-Gboard-Keyboard-app.jpg)，讓鍵盤收起。`TextInput` 事實上並不會 `call blur()` 

什麼意思呢？

>簡單的說即是焦點並沒有消失，導致下次就算 `call focus()` 也並不會有 `state` 的改變

為了解決這問題，我的方法是監聽鍵盤被收起的時候，手動 `blur()`

```
class AAA {
  componentDidMount() {
  	this.keyboardDidHideListener = Keyboard.addListener('keyboardDidHide', this.keyboardDidHide);
  }

  componentWillUnmount() {
    this.keyboardDidHideListener.remove();
  }
  
  keyboardDidHide = () => {
  	this.input.blur();
  };
}
```