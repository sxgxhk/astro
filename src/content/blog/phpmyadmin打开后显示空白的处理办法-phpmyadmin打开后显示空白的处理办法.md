---
title: phpmyadmin打开后显示空白的处理办法
date: 2016-01-24 02:09:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/phpmyadmin打开后显示空白的处理办法
categories: 
- 网站建设
tags: 
- phpmyadmin
---

<p>一直都在使用军哥的LNMP，从1.0到1.3测试版，可以说是一个非常不错的PHP环境部署程序，因为1.3测试版的缘故，所以目前在用的是LNMP1.2，也因为一直用的都是阿里云的RDS，所以Phpmyadmin就没去登过，这不RDS快到期了，续费又感觉贵，只好重新用起MySQL了，那用MySQL最方便的当然就是Phpmyadmin了，结果打开后一片空白，还以为是改目录名的问题，把目录名改回去也不行，重启LNMP也不行，后又重启服务器（用上阿里云基本就不知道重启了），可还是不行，想想反正也顺便整理一下，索性重装系统再重装LNMP吧，那就干吧……</p><p>等重装好系统，且装好LNMP后就赶紧试了一下Phpmyadmin，可以访问，那接着装缓存加速类扩展吧，一直都用的有：eAccelerator、Memcached等，装好之后，问题又来了，依旧是白屏，看来是某个加速有问题，逐个排除后，发现只要当eAccelerator安装好之后就会出现显示空白，哪怕你重启LNMP还是主机都之样，卸载后就OK了，只能果断割爱了。</p><p><img src="https://cdn.uu126.cn/wp-content/uploads/2016/01/lnmp.png" alt="请输入图片描述" title="请输入图片描述"> </p><p>其实说起来确实也蛮奇怪了，按理来说不应该呀，Centos下出现这样问题，换成Debian也这样，唉，搞定就行，不管这么多了，什么记得跟军哥反映反映。</p>