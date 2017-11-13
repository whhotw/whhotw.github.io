---
layout: post
title: "CLI 方式啟動 Android 模擬器"
date: 2017-11-02 17:18:48 +0800
comments: true
categories: android
---
[android-emulator-commandline](https://developer.android.com/studio/run/emulator-commandline.html)

[avdmanager-commandline](https://developer.android.com/studio/command-line/avdmanager.html)

List avd

```
./avdmanager list avd
Available Android Virtual Devices:
    Name: Pixel_API_25
  Device: pixel (Google)
    Path: /Users/whh/.android/avd/Pixel_API_25.avd
  Target: Google APIs (Google Inc.)
          Based on: Android 7.1.1 (Nougat) Tag/ABI: google_apis/x86_64
    Skin: pixel
  Sdcard: 100M
```

Run android emulator

```
cd ${ANDROID_HOME}/tools
emulator @${YOUR_AVD_NAME}
```

List of devices attached

```
adb devices
List of devices attached
emulator-5554	device
```