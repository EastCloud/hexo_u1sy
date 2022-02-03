---
title: 记录Cloudreve搭建及修改过程
date: 2021-06-17 14:24:00
categories: 网站
urlname: record-the-construction-and-modification-process-of-cloudrev
tags:
---
<!--markdown--># 0,Cloudreve是什么？

![Screenshot](https://cdn.jsdelivr.net/gh/EastCloud/u1sy_blog_1@latest/usr/uploads/2021/06/3440101061.png)
一款私有云程序

本站搭建**DEMO**[pan.u1sy.cn][2]

### 特性

* 支持本机、从机、七牛、阿里云 OSS、腾讯云 COS、又拍云、OneDrive (包括世纪互联版) 作为存储端
* 上传/下载 支持客户端直传，支持下载限速
* 可对接 Aria2 离线下载
* 在线 压缩/解压缩、多文件打包下载
* 覆盖全部存储策略的 WebDAV 协议支持
* 拖拽上传、目录上传、流式上传处理
* 文件拖拽管理
* 多用户、用户组
* 创建文件、目录的分享链接，可设定自动过期
* 视频、图像、音频、文本、Office 文档在线预览
* 自定义配色、黑暗模式、PWA 应用、全站单页应用
* All-In-One 打包，开箱即用
* ......

# 1，安装！
### :hammer_and_wrench: 部署

下载适用于您目标机器操作系统、CPU架构的主程序，直接运行即可。

```shell
# 解压程序包
tar -zxvf cloudreve_VERSION_OS_ARCH.tar.gz

# 赋予执行权限
chmod +x ./cloudreve

# 启动 Cloudreve
./cloudreve
```

以上为最简单的部署示例，您可以参考 [文档 - 起步](https://docs.cloudreve.org/) 进行更为完善的部署。

# 2，修改！
### 2.1修改配置文件
```shell
vim ./conf.ini
```
修改数据库，在后面添加：
```shell
[Database]
; 数据库类型，目前支持 sqlite | mysql
Type = mysql
; MySQL 端口
Port = 3306
; 用户名
User = root
; 密码
Password = [mysql_db_root_passwd]
; 数据库地址
Host = localhost
; 数据库名称
Name = cloudreve
; 数据表前缀
TablePrefix = cd
```
上面用'[mysql_db_root_passwd]'替代mysq的root用户的密码，使用前需替换成自己的密码。

完整实例如下：
```shell
[System]
Mode = master
Listen = :5200
Debug = false
SessionSecret = [SessionSecret]
HashIDSalt = [HashIDSalt]

[Database]
Type = mysql
Port = 3306
User = root
Password = [mysql_db_root_passwd]
Host = localhost
Name = cloudreve
TablePrefix = cd_
```
上面的[SessionSecret]和[HashIDSalt]代替，在第一次启动生成的配置文件中已经自动生成，无需修改。

面用'[mysql_db_root_passwd]'替代mysq的root用户的密码，使用前需替换成自己的密码。

删除无用的sqlite生成的cloudreve.db
```shell
rm cloudreve.db
```
### 2.2再次测试运行
```shell
./cloudreve
```
首次运行会打印监听端口、用户名和密码，如果监听端口已经修，说明配置文件已经生效，用浏览器登录测试，没问题进行下一步。

需要注意的是这次的用户名和密码要牢记

### 2.3导出静态文件
```shell
./cloudreve -eject
```
这个命令，会生成一个叫statics的文件夹，在我的服务器上绝对路径：/home/[username]/cloudreve/statics/也就是nginx配置文件中静态资源代理的root，这里需要注意对应修改好。

# 3，后台运行！
### 3.1配置服务
通过vi打开服务配置：
```shell
vi /usr/lib/systemd/system/cloudreve.service
```
输入如下内容：
```shell
[Unit]
Description=Cloudreve
Documentation=https://docs.cloudreve.org
After=network.target
Wants=network.target

[Service]
Type=simple
WorkingDirectory=/home/[username]/cloudreve
ExecStart=/home/[username]/cloudreve/cloudreve
Restart=on-abnormal
RestartSec=5s
KillMode=mixed

StandardOutput=null
StandardError=syslog

[Install]
WantedBy=multi-user.target
```
由于我平时使用的都是非root用户，上面用户名都用'[username]'代替，使用前请替换成自己的用户名

### 3.2更新重启服务
```shell
# 更新配置
systemctl daemon-reload

# 启动服务
systemctl start cloudreve

# 设置开机启动
systemctl enable cloudreve
```
### 3.3管理命令
```shell
# 启动服务
systemctl start cloudreve

# 停止服务
systemctl stop cloudreve

# 重启服务
systemctl restart cloudreve

# 查看状态
systemctl status cloudreve
```
# 4，大功告成
现在，你就建成了和我一样的私有云
**DEMO**[pan.u1sy.cn][3]


  [1]: https://cdn.jsdelivr.net/gh/EastCloud/u1sy_blog_1@latest/usr/uploads/2021/06/3440101061.png
  [2]: http://pan.u1sy.cn:5212
  [3]: http://pan.u1sy.cn:5212