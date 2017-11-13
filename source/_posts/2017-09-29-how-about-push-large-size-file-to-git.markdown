---
layout: post
title: "How about push large size file to Git"
date: 2017-09-29 10:36:15 +0800
comments: true
categories: git
---
想要上傳超過 100MB 的檔案到 Git 被 rejected 的解法

###安裝
`brew install git-lfs`

###操作
```
cd ${project}
git lfs install
git lfs track "*.ext" => 依副檔名
git add file.ext
git commit -m "something..."
git push origin master
```

關鍵是 `track` 某個檔案或是資料夾，可以利用 `git lfs ls-files` 查看哪些檔案被追蹤

```
$ git lfs ls-files
74015d7b01 * src/ios/xxx
```