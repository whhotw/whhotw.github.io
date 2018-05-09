---
layout: post
title: "Sublime setup eslint for RN"
date: 2018-02-08 00:25:20 +0800
comments: true
categories: 
---
我是使用 Sublime 3 的版本

#Install Sublime Package
```
SublimeLinter // 先裝
SublimeLinter-eslint
```

#Manual
or add on package.json

```
yarn add eslint --dev
yarn add eslint-config-airbnb --dev
yarn add eslint-plugin-import --dev
yarn add eslint-plugin-react --dev
yarn add eslint-plugin-jsx-a11y --dev
yarn add babel-eslint --dev
```

#Create .eslintrc
located on project root

```
{
  "parser": "babel-eslint",
  "extends": "airbnb",
  "rules": {
    "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"] }],
    "react/prop-types": [1],
    "no-unused-vars": [1],
    "no-use-before-define": [1, { "functions": true, "classes": true }],
  },
  "globals": {
    "fetch": true,
    "__DEV__": true,
  }
}
```
> 可以自訂規則寫在 `rules` 0 代表關閉、1 代表警告、2代表錯誤 

上述步驟做完，重開 Sublime 即可看到效果