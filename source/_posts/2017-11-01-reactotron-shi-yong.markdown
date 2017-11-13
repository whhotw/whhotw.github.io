---
layout: post
title: "Reactotron 使用"
date: 2017-11-01 16:27:58 +0800
comments: true
categories: react
---
###[Reactotron](https://github.com/infinitered/reactotron)

開發 React 應用的時候，可以試試這個工具。可以觀察網路連線的資訊還可以印出自定義的日誌

import 下面這行到你要用的地方
`import Reactotron from 'reactotron-react-js'`

預設有三種等級可以選擇

```
Reactotron.log('log')
Reactotron.warn('warn')
Reactotron.error('error')
```

也可以印出物件

```
Reactotron.display({
  name: 'ORANGE',
  preview: 'Who?',
  value: 'Orange you glad you don\'t know me in real life?',
  important: true
})
```
