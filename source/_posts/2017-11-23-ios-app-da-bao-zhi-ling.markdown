---
layout: post
title: "iOS App 打包用的指令"
date: 2017-11-23 15:30:49 +0800
comments: true
categories: ios
---
自動打包這件事情，在很多時候可以幫助開發者，節省很多的等待時間。簡單來說就是開始執行你就可以不用管了，之後的產出甚至可以結合自動測試，發布等等。這邊單純分享打包用的指令

###Archive

```
$ xcodebuild -workspace ${PROJECT_NAME}.xcworkspace -scheme ${TARGET_NAME} -sdk iphoneos -configuration archive -archivePath $PWD/build/${TARGET_NAME}.xcarchive
```

###Export *.ipa

```
$ xcodebuild -exportArchive -archivePath $PWD/build/${TARGET_NAME}.xcarchive -exportOptionsPlist BUILD.plist -exportPath $PWD/build
```

###BUILD.plist

```
$ cat BUILD.plist
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
        <key>teamID</key>
        <string>${TEAM_ID}</string>
        <key>method</key>
        <string>${METHOD}</string>
        <key>uploadSymbols</key>
        <true/>
        <key>compileBitcode</key>
        <true/>
</dict>
</plist>
```

>Xcode8.3 以上透過 command-line 輸出 ipa 需要打入 `exportOptionsPlist` 這個鍵值，因此需要多配置一個檔案類似如上

* method: (String) The method of distribution, which can be set as any of the following:
	* app-store
	* enterprise
	* ad-hoc
	* development
* teamID: (String) The development program team identifier.
* uploadSymbols: (Boolean) Option to include symbols in the generated ipa file.
* uploadBitcode: (Boolean) Option to include Bitcode.

###我自己寫的 Shell Script

<script src="https://gist.github.com/whhotw/b1d12e06844cbf08ae7dfa088e306fad.js"></script>
