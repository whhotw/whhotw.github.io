---
layout: post
title: "JavaScript 中 this 的種種"
date: 2018-01-09 09:56:40 +0800
comments: true
categories: javascript
---
JavaScript 中的 this 是一個很容易搞混的東東。

具名函數搭配 bind 的寫法

```
function wth() {
	console.log(this);
}

let o = {
	name: 1
};

wth(); // window

let wthBind = wth.bind(o);

wthBind(); // object o
```

使用箭頭函數

```
let wth = () => {
	console.log(this);
};

let o = {
	name: 1
};

wth(); // window

let wthBind = wth.bind(o);

wthBind(); // window
```
為什麼執行結果不同呢？是因為透過箭頭函數 this 對象會在宣告時就綁定，因此就算之後用 bind 也不會有變化