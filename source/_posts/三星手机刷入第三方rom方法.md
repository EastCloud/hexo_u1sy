---
title: 三星手机刷入第三方rom方法
date: 2021-02-05 07:25:00
categories: 玩机
cate_eng: playphone
urlname: samsung-mobile-phone-swipe-into-the-third-party-rom
tags:
---
<!--markdown-->#首先
此文原发布于[WeRoot玩机站][1]，现因网站调整，故迁移至本站。

#此处以国行版三星s8举例：
#前提条件：
首先确定你的机器是高通版并且已经解锁bl
##固件下载：
链接: https://pan.baidu.com/s/1uMqjgyAxMlYlOmmzN_0kTg 提取码: sr84?
#刷入教程
###1.首先下载图中所需要的文件
![1.png](https://i.loli.net/2020/08/04/sTKulheFt1GoxL8.png)
###2.然后依次安装驱动，解压odin3
![2.png](https://i.loli.net/2020/08/04/ObtjoWguxr9f3Qw.png)
###3.将手机进入downloading模式
关机状态下，同时按住**音量下键**+**bixby键**+**电源键**，即可进入（即如图中所示）
![3.jpg](https://i.loli.net/2020/08/04/o2zJvMkqfbwHlP3.jpg)
###4.进入twrp
首先解压odin3.zip，然后双击文件夹里的odin3，再继续按照有图中的方法，如果上面步骤1/2/3完成的话，那么图中第一个红圈将会出现**COM数字**，然后到**options**里面把**自动重启** **取消勾选**，散后点第三个红圈位置，选择刚刚下载的资源目录里的twrp，然后点击**start**
![4.png](https://i.loli.net/2020/08/04/yc2VukAsLXpKow4.png)
###5.格式化data
手机进入twrp之后，先滑动允许修改system
![5.jpg](https://i.loli.net/2020/08/04/3UVhHkqKWPrs9wv.jpg)
然后点击主页面上的**清除**，然后点击**格式化data**，然后输入**yes**进行确定。此时，等待手机格式化完成后，点击主页面上的**重启**-**Recovey**
![6.jpg](https://i.loli.net/2020/08/04/4GWRZ2jAXMieQOu.jpg)
现在点击主页上的挂载，勾选**data**
![7.jpg](https://i.loli.net/2020/08/04/q41BSeE32o5zAsn.jpg)
###6.传输刷机包
此时电脑**这台电脑**将会出现你的手机，
![8..png](https://i.loli.net/2020/08/04/hRqIEAvJ1crfL8x.png)
现在你要做的事情就是把刷机包复制进去。
![10.png](https://i.loli.net/2020/08/04/jMAhrmvpbdV35an.png)
复制完成后你的根目录将会如下图所示
![9.png](https://i.loli.net/2020/08/04/mLixq84FdZpw39N.png)
###7.开始刷机
此时刷机包已经都存在于手机之上，所以我们只需点击**安装**，并选择要安装的刷机包
![11.jpg](https://i.loli.net/2020/08/04/NKgqBDJ5PE4YZx7.jpg)


? [1]: https://www.weroot.top/post-14.html