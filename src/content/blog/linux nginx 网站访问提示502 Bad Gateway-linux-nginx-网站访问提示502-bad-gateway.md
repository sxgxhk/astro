---
title: linux nginx 网站访问提示502 Bad Gateway
date: 2014-02-24 05:18:38.0
updated: 2021-12-22 17:01:20.0
url: /archives/linux-nginx-网站访问提示502-bad-gateway
categories: 
- 网站建设
tags: 
---

从日志报错分析，是php线程打开文件句柄受限导致的，解决办法：
1、提升服务器的文件句柄打开打开
vi /etc/security/limits.conf 底部加上
* soft nofile 51200
* hard nofile 51200
vi /etc/sysctl.conf  底部添加
fs.file-max=51200
2、提升nginx的进程文件打开数
vi /www/wdlinux/nginx/conf/nginx.conf
worker_rlimit_nofile 5120; 改成worker_rlimit_nofile 51200;
3、修改php-fpm.conf文件，主要需要修改2处。
vi /www/wdlinux/etc/php-fpm.conf
改成下面的值
&lt;value name="max_requests"&gt;10240&lt;/value&gt;
&lt;value name="rlimit_files"&gt;51200&lt;/value&gt;
4.设置php-fpm自动启动
vi /etc/rc.local 最后增加
/etc/init.d/php-fpm start
完成之后reboot重启下服务器
ulimit -n 查看