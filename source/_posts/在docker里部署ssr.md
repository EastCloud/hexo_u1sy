---
title: 在docker里部署ssr
date: 2021-08-23 13:48:00
categories: 网站
cate_eng: web
urlname: deploy-ssr-in-docker
tags:
---
<!--markdown--># 前言
众所周知docker的轻量性，诸多好评，做到随用随删除
碰巧我最近在用停机卡免流，手上又碰巧有一台国内的机子
所以就拿来测试了
# 部署
部署是很简单
没有安装docker?
看这里: http://get.daocloud.io/#install-docker
安装方法： docker pull 4kerccc/shadowsocksr
食用方法： docker run -itd -p 1000:22 -p 80:80 4kerccc/shadowsocksr
部署完成之后就可以直接连接了，默认配置在末尾，只需要把ip和端口换成对应的即可，其他保持默认。
详细解释： run : 运行 -i :即使没有附加也保持STDIN 打开 -t :分配一个伪终端 -d :分离模式: 在后台运行 -p : 端口映射，遵循 本地端口:容器端口映射 (上面为将本地1000端口映射为容器22端口，可自行修改) (务必注意，我默认把本地80端口映射为容器80端口，如果启动失败，请更换本地80端口为其他端口)
樱花容器安装方法： 镜像填入4kerccc/shadowsocksr 端口务必留下22和80端口用于远程登陆和ssr连接。
不懂的看这个图： https://4ker.cc/wp-content/uploads/2018/02/1.png
(图片里面镜像换成：4kerccc/shadowsocksr 再添加一个80端口)
OVER,没其他的了，
忘记说了件大事情： 
ssh用户名: root 密码: 4ker.cc
############################################################# 
非常重要：
默认配置为：
恭喜你！我们已为你完成了所有的安装，以下是连接信息！
服务器IP地址: youip
远程端口: 80 (此端口为容器端口，使用时请换位本地映射端口)
密码: 4ker.cc
认证协议: auth_sha1_v4
混淆方式: http_simple
加密方法: chacha20
如果想修改端口和密码请先远程登录之后
vi /etc/shadowsocks.json 来修改
里面80为端口，4ker.cc为连接密码，都可自行修改.
修改后请执行 /etc/init.d/shadowsocks restart
用于重启shadowskcsR服务。
#############################################################

# 项目地址
https://hub.docker.com/r/4kerccc/shadowsocksr/