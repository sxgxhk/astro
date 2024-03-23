---
title: 教你用Serv－U架设个人FTP
date: 2012-12-08 06:29:37.0
updated: 2021-12-22 17:01:20.0
url: /archives/教你用serv-u架设个人ftp
categories: 
- 网站建设
tags: 
---

<p align="left">首先下载安装Serv-U，运行，将出现“设置向导”窗口，我们就来跟随着这个向导的指引，一步步进行操作</p>
<p align="left"><strong>1. 设置Serv－U的IP地址与域名</strong>
右键点击“域”，来到“新建域”窗口（如图1），这里要求输入本机的IP地址。</p>
　
<img src="http://www.zgsj.com/vps/ftpphoto/1.JPG" alt="" width="613" height="259" />
<p align="center">
图(1) 新建域</p>
<p align="justify">输入你的IP地址。</p>
<p align="justify">下一步，进行“域名”设定。这个域名只是用来标识该FTP域，没有特殊的含义，比如笔者输入“ftp.zgsj.com”。</p>
<p align="justify">下一步，域端口号设定。使用默认的21端口。单击下一步。</p>
<p align="justify">下一步，设置域类型。选择存储与计算机注册表</p>
<img src="http://www.zgsj.com/vps/ftpphoto/2.JPG" alt="" width="584" height="245" />
<p align="center">图（2）设置域类型</p>
<p align="center">　</p>
<p align="left">接下来在本地服务器里勾上“自动开始（系统服务）”的复选框这样当你的电脑一启动，服务器也会跟着开始运行。</p>
<img src="http://www.zgsj.com/vps/ftpphoto/3.JPG" alt="" width="566" height="238" />
<p align="center">图（3）设置系统服务</p>
　
<p align="left"><strong>2.设置匿名登录</strong></p>
<p align="left">第一步右击用户，新建用户</p>
<img src="http://www.zgsj.com/vps/ftpphoto/4.JPG" alt="" width="583" height="300" />
<p align="center">图（4）新建用户</p>
　
下一步，输入您要建立的用户名和密码，如图（5）笔者用的用户名是“11”
<img src="http://www.zgsj.com/vps/ftpphoto/5.JPG" alt="" width="587" height="246" />
<p align="center">图（5）建立用户名</p>
<p align="left">下一步，会要求你指定FTP主目录，并询问是否将用户锁定于主目录中，选“是”，这样登录的用户将只能访问你指定的主目录及以下的各级子目录，而不能访问上级目录，便于保证硬盘上其他文件的安全。</p>
<p align="center"><img src="http://www.zgsj.com/vps/ftpphoto/6.JPG" alt="" width="587" height="246" /></p>
<p align="center">图（6）建立主目录（文件存放路径）</p>
下一步，配置账户信息。如图（7）根据您的需要选上写入追加删除权限。
<p align="center"><img src="http://www.zgsj.com/vps/ftpphoto/7.JPG" alt="" width="623" height="216" /></p>
<p align="center">图（7）配置账户信息</p>
<p align="center">　</p>
<p align="left">账号：如果有用户违反FTP的规定，你可以点击此处的“禁用账号”，让该用户在一段时间内被禁止登录。另外此处的“锁定用户于主目录”一定要勾选，否则你硬盘的绝对地址将暴露。
常规：根据自身的实际需要，在此设置最大的下载和上传速度、登录到本服务器的最大用户数、同一IP的登录线程数等。
IP访问：你可以在此拒绝某个讨厌的IP访问你的FTP服务器，只要在“编辑规则”处填上某个IP地址，以后该IP的访问将会全部被拦下。
配额：勾选“启用磁盘配额”，在此为每位FTP用户设置硬盘空间。点击“计算当前”，可知当前的所有已用空间大小，在“最大”一栏中设定最大的空间值。
最后，请在有改动内容的标签卡上点击右键，选择“应用”，如此才能使设置生效！
好了！现在，一个简单的个人FTP服务器就已经完整地呈现在你面前了。不过这时还要测试一下能否成功地下载和上传。</p>
<p align="left"><strong>3.提高安全性</strong></p>
<p align="left">为了提高安全性，在本地服务器——》设置——》高级填上PASV端口范围，笔者使用的是50000—50001，另外注意防火墙和安全策略要打开这两个端口。</p>
<p align="left"><strong>4.上传下载</strong></p>
<p align="left">要使用FTP服务器下载和上传，就要用到FTP的客户端软件。常用的FTP客户端软件有CuteFTP、FlashFXP、FTP Explorer等等。对于它们的具体使用，这里就不细讲了。基本上只要在这些软件的“主机名”处中填入您的FTP服务器IP地址，而后依次填入用户名，密码和端口（一般为21），点击连接，只要能看到你设定的主目录并成功实现文件的下载和上传，就说明这个用Serv-U建立起来的FTP服务器能正常使用了！</p>
<p align="left">需要指出的是上传的时候要去掉PASV（被动）方式的连接，具体以flashfxp3.4.1为例</p>
<p align="left"><strong>“选项——》参数选择-》链接-》代理去掉使用被动模式前的勾”</strong></p>