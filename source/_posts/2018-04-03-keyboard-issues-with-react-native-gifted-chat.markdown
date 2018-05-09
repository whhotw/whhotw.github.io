---
layout: post
title: "Keyboard issues with react-native-gifted-chat"
date: 2018-04-03 14:13:35 +0800
comments: true
categories: react-native
---
使用 `react-native-gifted-chat` 假如有同時使用 `react-native-keyboard-manager` 在設定的時候記得 `setEnable(false)`

```
if (Platform.OS === 'ios') {
  if (__DEV__) {
    KeyboardManager.setEnableDebugging(true);
  }

  KeyboardManager.setEnable(false); // do not using it's
  KeyboardManager.setKeyboardDistanceFromTextField(10);
  KeyboardManager.setPreventShowingBottomBlankSpace(true);
  KeyboardManager.setEnableAutoToolbar(true);
  KeyboardManager.setToolbarManageBehaviour(0);
  KeyboardManager.setShouldToolbarUsesTextFieldTintColor(false);
  KeyboardManager.setToolbarPreviousNextButtonEnable(true);
  KeyboardManager.setShouldShowTextFieldPlaceholder(true);
  KeyboardManager.setOverrideKeyboardAppearance(false);
  KeyboardManager.setShouldResignOnTouchOutside(false);
  KeyboardManager.resignFirstResponder();
}
```