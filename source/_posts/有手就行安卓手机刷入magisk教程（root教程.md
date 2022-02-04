---
title: 有手就行安卓手机刷入magisk教程（root教程
date: 2021-06-18 09:01:00
categories: 玩机
cate_eng: playphone
urlname: android-mobile-phone-brush-into-magick-tutorial-root-tutorial
tags:
---
<!--markdown--># 注意
>**刷机有风险,搞机须谨慎**
>**刷机有风险,搞机须谨慎**
>**刷机有风险,搞机须谨慎**

# 准备工作
您需要
1，给手机解除bl锁定
> BL:Android 系统虽然也是基于 Linux 系统的,但是由于 Android 属于嵌入式设备,并没有像 PC 那样的 BIOS 程序。 取而代之的是 Bootloader —— 系统启动加载器。
（如果您不知如何解锁的话，请百度）

2，一个手机
3，不怕失败的脑子

# 下面开始教程（第一种方法）
1，首先给您的手机刷入第三方recovery（常用[twrp][1]）
>百度查找您的机型刷入方式
①A-only分区机型在fastboot模式输入fastboot flash recovery xxx.img
②AB分区机型要在fastboot模式输入fastboot boot xxx.img

2，下载[magsik.zip][2]
前往[github][2]下载最新版magisk.zip

3，在twrp里刷入
twrp点击安装，选择zip包，选择magisk.zip，滑动刷入，重启手机

4，ok，成功了！
这样，你的手机就成功刷入了magisk了
请享受搞机带来的乐趣吧

# 第二种方法
首先你需要有当前系统的boot
>提取boot方法：
①解压刷机包得到
②通过qpst提取boot

然后安装magisk manager
在里面点击修补boot
选择您的boot文件
然后刷入修补后的boot文件
>刷入方式：
①twrp内刷入镜像到boot分区
②fastboot模式下输入fastboot flash boot xxx.img

**ok**
这样，你的手机就成功刷入了magisk了
请享受搞机带来的乐趣吧


  [1]: http://twrp.me
  [2]: https://github.com/topjohnwu/Magisk/releases