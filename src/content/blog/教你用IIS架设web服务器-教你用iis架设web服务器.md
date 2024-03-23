---
title: 教你用IIS架设web服务器
date: 2012-12-08 06:28:52.0
updated: 2021-12-22 17:01:20.0
url: /archives/教你用iis架设web服务器
categories: 
- 网站建设
tags: 
---

<p align="left"><strong>1.</strong><strong>从安全考虑，首先为您的</strong><strong>web</strong><strong>服务新建一个用户，并设置密码，笔者设置的密码为</strong><strong>123456</strong><strong>（后面开设</strong><strong>web</strong><strong>服务会用到这个密码）。</strong><strong></strong></p>
<p align="center">　</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/1.JPG" alt="" width="506" height="294" /></p>
<p align="center">图（1）建立服务账户</p>
<p align="left"><strong>2.安装完成后</strong><strong>,</strong><strong>我们打开控制面版的</strong><strong>-&gt;</strong><strong>管理工具</strong><strong></strong></p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/2.JPG" alt="" width="686" height="222" /></p>
<p align="center">　</p>
<p align="center">图（2）IIS服务器</p>
<p align="center">　</p>
<p align="center">　</p>
<p align="left">中国数据的主机租用和VPS默认是装好了IIS的，这就是我们安装好的IIS -&gt; intrnet 服务管理器</p>
<p align="left"><strong>3.打开</strong><strong>web</strong><strong>服务器扩展</strong><strong></strong></p>
<p align="center"><strong><img src="http://www.zgsj.com/vps/IISphoto/3.JPG" alt="" width="634" height="270" /></strong></p>
<p align="center">图（3）打开web服务器扩展</p>
<p align="left"><strong>4.打开</strong><strong>IIS</strong><strong>服务器——》网站</strong><strong></strong></p>
<p align="left">1）右键点击网站，点属性，选择主目录——》配置——》选项</p>
勾选上“启用父路径”
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/4.JPG" alt="" width="382" height="226" /></p>
<p align="center">图（4）启用父路径</p>
<p align="left">2）在文档标签里添加你的默认首页。</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/5.JPG" alt="" width="463" height="311" /></p>
<p align="center">图（5）添加默认首页</p>
<p align="left">3）弹出一个网站新建向导，直接下一步。输入你的网站描述，比如您的ftp名。这里输入test</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/6.JPG" alt="" width="477" height="365" /></p>
<p align="center">图（6）网站描述</p>
<p align="left">4）点击下一步。</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/7.JPG" alt="" width="469" height="353" /></p>
<p align="center">图（7）ip地址端口设置</p>
<p align="left">需要说明的是主机头即是你要绑定的域名，要想绑定多个域名，后面再说，参见第×××步</p>
<p align="left">5）网站主目录设置（即您网站文件的存储根目录）</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/8.JPG" alt="" width="479" height="365" /></p>
<p align="center">图（8）网站主目录设置</p>
<p align="left">6）点击下一步勾选上运行脚本和执行</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/9.JPG" alt="" width="478" height="366" /></p>
<p align="center">图（9）网站访问权限设置</p>
<p align="left">7）点击下一步，web服务基本架设完成。但是作为服务器，安全性是很重要的。</p>
<p align="left">8）右键点击刚才建立的test网站，选择属性——》目录安全性，在身份验证和访问控制下点击“编辑”——》对匿名访问使用下列Windows用户。</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/10.JPG" alt="" width="360" height="207" /></p>
<p align="center">图（10）匿名访问账户设置</p>
<p align="left">点击浏览——》高级——》立即查找，选择本文刚开始建立的test用户，并填入设置的密码123456.</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/11.JPG" alt="" width="372" height="285" /></p>
<p align="center">图（11）设置一个安全的匿名访问账户</p>
<p align="left">9）在地“5）”步提到的D:/wwwroot文件夹上也同样加上test用户权限，并删除除了系统和管理员之外的权限。</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/12.JPG" alt="" width="371" height="374" /></p>
<p align="center">图（12）设置网站程序安全权限</p>
<p align="center">现在一个安全好用的web服务器就基本建立好了，放入您的程序可以使用了。</p>
<p align="center"><img src="http://www.zgsj.com/vps/IISphoto/13.JPG" alt="" width="610" height="327" /></p>
<p align="center">图（13）主机开设成功</p>