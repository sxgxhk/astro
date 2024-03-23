---
title: 教你在IIS中绑定网站域名
date: 2012-12-08 06:30:54.0
updated: 2021-12-22 17:01:20.0
url: /archives/教你在iis中绑定网站域名
categories: 
- 网站建设
tags: 
---

我们以站点名为test的站点为例讲解下下iis绑定域名的操作过程
<strong>1、右击刚才新建的test站点——》选择选择属性</strong> <a href="http://www.zgsj.com/vps/iis.asp" target="_blank"><span style="color: #ff0000;">请点击如何新建站点</span></a><span style="color: #ff0000;">
<img src="http://www.zgsj.com/vps/IISphoto/14.jpg" alt="" />
<strong>2、切换到网站选项——》点击高级</strong>
<img src="http://www.zgsj.com/vps/IISphoto/15.jpg" alt="" />
<strong>3、这里你可以看到你之前绑定的所有域名，如果需要绑定新的域名，点击添加</strong>
<img src="http://www.zgsj.com/vps/IISphoto/16.jpg" alt="" />
<strong>4、这里的IP地址添加你自己服务器的IP</strong>
TCP端口就是要使用的web端口，默认是80
主机头值：就是你要绑定的域名，注意这里不是加http://的
另外有一点值得注意的是zgsj.com和www.zgsj.com是两个不同的主机头，如果想要能使用zgsj.com和www.zgsj.com两个域名都能访问你的网站的话，必须把两个都绑定上去！
填写好以后确定返回上一界面
<img src="http://www.zgsj.com/vps/IISphoto/17.jpg" alt="" />
<strong>5、可以看到刚才绑定的域名了，如果还想继续绑定其他域名的话，重复添加就可以了，添加结束后点击 确定返回</strong>
<img src="http://www.zgsj.com/vps/IISphoto/18.jpg" alt="" />
<strong>6、回到这个界面后不要忘记点击 应用 保存，确定后即完成了对test站点的域名绑定工作</strong>
<img src="http://www.zgsj.com/vps/IISphoto/19.jpg" alt="" /><!-- 正文结束 --></span>