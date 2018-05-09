---
layout: post
title: "認識 JWT"
date: 2018-02-13 13:19:20 +0800
comments: true
categories: 
---
#流程圖

![](https://stormpath.com/wp-content/uploads/2016/05/Cookie-v-Token-Diagram-v1-3-1024x536.png)

左邊是傳統的 `cookie-session` 的流程，右邊是使用 `token` 的流程，乍看是很類似的。也因為運作的慨念很類似，所以兩者之間的轉換幾乎沒什麼困難。

#[JWT](https://jwt.io)

因為我都是在寫 APP 比較多，因此選擇用 `token` 的機制去解決身份驗證的問題，在實作上會快很多，重點是 `lib` 人家都寫好了，呵呵

##What is JSON Web Token?
>JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA.

>Let's explain some concepts of this definition further.

>Compact: Because of their smaller size, JWTs can be sent through a URL, POST parameter, or inside an HTTP header. Additionally, the smaller size means transmission is fast.

>Self-contained: The payload contains all the required information about the user, avoiding the need to query the database more than once.

被定義在[RFC7519](https://tools.ietf.org/html/rfc7519)，可使傳輸過程變得安全並有輕量與自我驗證的優勢

##When should you use JSON Web Tokens?
>Here are some scenarios where JSON Web Tokens are useful:

>Authentication: This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.

>Information Exchange: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.

取自官網上的資訊，主要的目的就是身份驗證與資料交換

##What is the JSON Web Token structure?

三個部分

* Header
* Payload
* Signature

###Header

```
{
  "alg": "HS256",
  "typ": "JWT"
}
```

###Payload

```
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```

>[Notice that the claim names are only three characters](https://tools.ietf.org/html/rfc7519#section-4.1)

###Signature

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

#參考資料

* [JWT](https://jwt.io/introduction/)
* [Refresh Token](https://auth0.com/blog/refresh-tokens-what-are-they-and-when-to-use-them/)
* [HTTP Authorization](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization)
* [Cookie vs Token](https://auth0.com/blog/cookies-vs-tokens-definitive-guide/)