---
layout: post
title: "stack vs. heap"
date: 2018-01-12 10:58:29 +0800
comments: true
categories: 
---
最近複習了一下`stack`跟`heap`的觀念。我主要是參考這部[影片](https://www.youtube.com/watch?v=_8-ht2AKyH4)

![image](https://i.ytimg.com/vi/_8-ht2AKyH4/maxresdefault.jpg)
>影片中我覺得很重要的一張圖

###Global

全域變數或是靜態變數

###Stack

可預期生命週期的變數或是函式，例如：區域變數，函式變數

```
int f() {
	int a;
	a = ff();
	return a;
}

int ff() {
	return 10;
}
```

編譯器會知道變數的生命週期，像是上面的片段。程式會在`stack`放入變數`a`接著等待函式`ff`的返回，當`ff`返回時會從`stack`中釋放變數`a`，因此程式可以自我管理記憶體空間不需要開發者介入

###Heap

動態配置的空間，例如：指標

```
int f() {
	int *a;
	a = (int*)malloc(sizeof(int)); // 配置記憶體
	*a = 10;
	free(a); //釋放記憶體
}
```

編譯器並不會知道何時要釋放變數`a`，因此開發者必須自行執行函式`free`將記憶體釋放。配置跟釋放有`malloc` `free`跟`new` `delete`
