---
layout: post
title: "First React Native App"
date: 2017-09-06 14:49:07 +0800
comments: true
categories: React-Native
---
#快速建立一個 React-Native App
###Install create-react-native-app
```
npm install -g create-react-native-app
```

###Create React Native App
```
create-react-native-app ${ProjectName}
cd ${ProjectName}
npm run ios(or android)
```

#建立一個 React-Native App
###Install react-native-cli
```
npm install -g react-native-cli
```

###Init & Run Project
```
react-native init ${ProjectName}
cd ${ProjectName}
react-native run-ios(or -anroid)
```
>remind: stop apache

#常用的第三方套件
###Install & Import react-native-vector-icons
```
npm install --save react-native-vector-icons
npm install -g rnpm
rnpm link

import Icon from 'react-native-vector-icons/Ionicons';
```
>react-native-i18n: 多語系<br/>
>react-native-keychain: 帳密處理<br/>
>react-native-navigation: 導覽列佈局<br/>
>react-native-vector-icons: 圖資源<br/>