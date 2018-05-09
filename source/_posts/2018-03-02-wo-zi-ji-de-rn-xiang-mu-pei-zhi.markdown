---
layout: post
title: "我自己的 RN 項目配置"
date: 2018-03-02 01:34:59 +0800
comments: true
categories: react-native
---
記錄一下，建立一個新的 RN 項目時的步驟，每次都會忘記，再加上改版時不時就跑出一推問題，麻煩！這只是我個人有用到一些套件與建立步驟

#CLI

```
yarn init ${PROJECT_NAME} --version 0.51.0
yarn add redux-thunk redux-logger redux react-redux react-native-navigation react-native-vector-icons react-native-i18n react-native-elements prop-types
yarn add babel-eslint eslint eslint-config-airbnb eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react babel-core@6.0.0 --dev
```

#package.json

```
{
  "name": "${PROJECT_NAME}",
  "version": "0.0.1",
  "private": true,
  "scripts": {
    "start": "node node_modules/react-native/local-cli/cli.js start",
    "test": "jest"
  },
  "dependencies": {
    "prop-types": "^15.6.1",
    "react": "16.0.0",
    "react-native": "0.51.0",
    "react-native-elements": "^0.19.0",
    "react-native-i18n": "^2.0.12",
    "react-native-navigation": "^1.1.393",
    "react-native-vector-icons": "^4.5.0",
    "react-redux": "^5.0.7",
    "redux": "^3.7.2",
    "redux-logger": "^3.0.6",
    "redux-thunk": "^2.2.0"
  },
  "devDependencies": {
    "babel-core": "6.0.0",
    "babel-eslint": "^8.2.2",
    "babel-jest": "22.4.1",
    "babel-preset-react-native": "4.0.0",
    "eslint": "^4.18.1",
    "eslint-config-airbnb": "^16.1.0",
    "eslint-plugin-import": "^2.9.0",
    "eslint-plugin-jsx-a11y": "^6.0.3",
    "eslint-plugin-react": "^7.7.0",
    "jest": "22.4.2",
    "react-test-renderer": "16.0.0"
  },
  "jest": {
    "preset": "react-native"
  },
  "rnpm": {
    "assets": [
      "./src/fonts"
    ]
  }
}
```

#Directory tree

```
▶ tree -La 1
.
├── .babelrc
├── .buckconfig
├── .eslintrc
├── .flowconfig
├── .gitattributes
├── .gitignore
├── .watchmanconfig
├── __tests__
├── android
├── app.json
├── index.js
├── ios
├── node_modules
├── package.json
├── src
└── yarn.lock
```

#Directory of src tree

```
▶ tree -L 1
.
├── actions
├── components
├── config
├── fonts
├── helpers
├── i18n
├── reducers
└── screens
```

#.eslintrc

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