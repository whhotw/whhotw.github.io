---
layout: post
title: "Disable font sacle on React-Native"
date: 2020-04-23 02:38:39 +0800
comments: true
categories: react-native
---
必須在 `class` 裡面

```
export default class App extends Component {
  constructor() {
    super();
    Text.defaultProps.allowFontScaling = false;
    TextInput.defaultProps.allowFontScaling = false;
  }
}
```
