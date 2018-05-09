---
layout: post
title: "Jenkins 中 Poll SCM 與 Build periodically 差異"
date: 2018-02-27 11:00:34 +0800
comments: true
categories: jenkins
---
#Poll SCM

固定時間執行（假如代碼有改變）

*/5 * * * * （每 5 分鐘檢查一次）
 
#Build periodically

固定時間執行（不管代碼是否改變）

0 2 * * * （每天 AM 2:00 執行一次）