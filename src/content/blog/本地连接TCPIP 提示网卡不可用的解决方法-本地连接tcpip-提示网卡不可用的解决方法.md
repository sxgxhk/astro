---
title: 本地连接TCP/IP 提示网卡不可用的解决方法
date: 2015-05-17 00:58:59.0
updated: 2021-12-22 17:01:20.0
url: /archives/本地连接tcpip-提示网卡不可用的解决方法
categories: 
- IT综合技术
tags: 
- 维修
---

下雨天没事正看着《特警力量》，朋友一台电脑拿来了，说是上不了网让我给瞧瞧（我的特特警们，待会再看哈），上电开机进入系统，虽然有点慢但还是可以进的，朋友电脑安装的XP，右击“网上邻居”属性过了好长时间才跳出本地连接来，看着图标是已经连接上的，双击“本地连接”-“支持”看时，傻眼了，不显示IP那项，看一下图就明白了：
<a href="http://uu126.cn/wp-content/uploads/2015/05/20150516164248.jpg"><img class="aligncenter size-full wp-image-1789" src="http://uu126.cn/wp-content/uploads/2015/05/20150516164248.jpg" alt="20150516164248" width="360" height="422" /></a>
&nbsp;
啥也没有，看看本地连接属性吧，结果在TCP/IP那项竟然属性打不开，还提示：
<a href="http://uu126.cn/wp-content/uploads/2015/05/b812c8fcc3cec3fd7365aebcd688d43f8694279b.png"><img class="aligncenter size-full wp-image-1790" src="http://uu126.cn/wp-content/uploads/2015/05/b812c8fcc3cec3fd7365aebcd688d43f8694279b.png" alt="b812c8fcc3cec3fd7365aebcd688d43f8694279b" width="315" height="123" /></a>
网卡我明明安装的呀，而且看看机箱后面网线连接时也是会亮灯的，折腾了服务和组策略都没有用，想想算了重装系统吧，结果被朋友否决了，好多软件他不想重装，唉，我继续修复吧……
既然不能重装系统，干脆就把网卡驱动卸载掉重新安装吧（以前安装DELL电脑时碰到过，网卡驱动装好了，连接上但不能上网的事），结果当我安装好网卡驱动后，一会功夫那”丢失“的IP就有了，当然那个TCP/IP属性也可以打开了，至此故障暂时就解决了（之所以说是暂时，因为也不确定以后会不会复发，就跟那西药一样，治标不治本，呵呵），交差，继续看俺的《特警力量》，GO！