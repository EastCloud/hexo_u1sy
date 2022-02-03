---
title: 无需Root权限使用icebox（冰箱）
date: 2021-02-03 12:24:00
categories: 玩机
urlname: use-icebox-without-root
tags:
---
<!--markdown-->Icebox（冰箱）是一款功能强大的冻结app的应用。但是在没有root的手机上该怎么用呢？下面一起看看吧。

#第一种方法（推荐）
使用冰箱激活器，这种方法请看这里**[使用一键激活器冰箱 Ice Box][1]**

#第二张方法（备用）
电脑安装adb工具，手机打开usb调试后连接电脑，cmd里面手动输入adb命令：

```shell
adb shell sh /sdcard/Android/data/com.catchingnow.icebox/files/start.sh
```
#ok，现在打开冰箱app即已激活
更多内容请查看[icebox文档][2]


? [1]: https://iceboxdoc.catchingnow.com/%E4%B8%80%E9%94%AE%E6%BF%80%E6%B4%BB%E5%B7%A5%E5%85%B7
? [2]: https://iceboxdoc.catchingnow.com