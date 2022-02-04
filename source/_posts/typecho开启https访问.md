---
title: typecho开启https访问
date: 2021-02-03 10:56:00
categories: 网站
cate_eng: web
urlname: typecho-use-https-to-access
tags:
---
<!--markdown-->
Typecho程序启用https访问详细教程。
注意事项：Typecho启用https访问需要修改一些文件，在修改之前必须做好网站的备份工作，千万记得备份！
编辑Typecho站点根目录下的文件config.inc.php加入下面一行配置，否则网站后台还是会调用HTTP资源。

```php
/** 开启HTTPS */
define('__TYPECHO_SECURE__',true);
```
