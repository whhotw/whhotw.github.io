---
layout: post
title: "Ignore self signed cert on React Native App"
date: 2017-10-05 11:06:00 +0800
comments: true
categories: React-Native
---
{% img /assets/Simulator%20Screen%20Shot%20Oct%205%2C%202017%2C%2011.19.10%20AM.png 360 640 %}

RN 裡面是不接受自簽憑證的，但是往往在開發環境中，有些時候還是會用到自簽憑證，這時候就會變得很麻煩，因為寫程式的時候等於不能跑在測試環境，這時候就可以新增 `NSURLRequest` 的 category 讓網路連線可以通過 `https` 的錯誤

```
+ (BOOL)allowsAnyHTTPSCertificateForHost:(NSString *)host {
  return YES;
}
```