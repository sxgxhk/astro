---
title: 可以Ping通和DNS解析，但打不开网页的解决办法
date: 2016-03-13 19:09:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/可以ping通和dns解析-但打不开网页的解决办法
categories: 
- IT综合技术
tags: 
- 维修
---

<p>早上收到朋友电话，说家里电脑因为安装了一个控件后来删除了，就出现电脑不能上网，具体的故障表现为：可以Ping通地址（不管是DNS，还是如网关、域名等都可以Ping通）；经检查，DNS设置也都正常（包括本地连接中的IP地址等信息都正确）；目前就是无法打开网页（感觉是网页打开的一瞬间就显示无网络连接），像QQ等也都上不去。一般碰到比较多的都是网页打不开，但QQ能上，那种DNS设置一下就OK了，这个嘛……一步一步排除解决吧。</p><p>首先，通过重启路由、sfc修复命令、重装驱动、更换网络等方式修复均无果，只好用带网络功能的PE来，结果发现在该系统下，网络正常。不知怎么的想起很久前用的一种修复网络方法，但很模糊，只记得"winsock"这个关键字，查了下微软的文档，然后解决啦，然后解决办法如下：</p><p>开始——运行——输入<code>cmd</code>回车——输入<code>netsh winsock reset</code>命令(重置winsock文件)——重启系统。</p><p><img src="https://cdn.uu126.cn/wp-content/uploads/2016/03/20160313105425.jpg" alt="请输入图片描述" title="请输入图片描述"> </p><p>其次，若按上面的复后仍然不行，那么尝试如下的修复方式：</p><p>1、删除下面这两个的注册表项(删除前先备份：右键——&gt;导出，如若有问题，可以恢复;删除后重启系统)：</p><pre><code class="lang-python">HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Winsock
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Winsock2</code></pre><p><img src="https://cdn.uu126.cn/wp-content/uploads/2016/03/20160313110358.jpg" alt="请输入图片描述" title="请输入图片描述"> </p><p>2、重装TCP/IP协议</p><p>1）右键单击网络连接，然后单击“属性”。</p><p>2）单击“安装”。</p><p>3）单击“协议”，然后单击“添加”。</p><p>4）单击“从磁盘安装”。</p><p>5）键入 <code>C:\Windows\inf</code>，然后单击“确定”。</p><p>6）在可用协议列表中，单击 <code>Internet 协议 (TCP/IP)</code>，然后单击“确定”。</p><p>7）重新启动系统。</p><p>注意：以上处理方式不是针对DNS解析问题(如能上QQ,不能打开网页)的，如果是DNS解析问题，尝试ping DNS服务器、更改DNS服务器、检查DNS Client服务状态登操作，DNS解析问题是不需要如上操作步骤。</p><p><img src="https://cdn.uu126.cn/wp-content/uploads/2016/03/20160313110556.jpg" alt="请输入图片描述" title="请输入图片描述"> <br />一般按照这么修复下来，大部分都是可以解决的，至少朋友的电脑已经可以上网了（对了，修得好记得要重启一下电脑哦）</p><p>顺带补充：（动态）公网IP环境80端口被封的几种解决方法</p><p>1）更换访问端口：将访问端口由80更改为其他端口，如70，更改后，访问网站时，需要带端口号访问。</p><p>2）URL显性转发：使用nat123域名解析的URL显性转发。</p><p>3）URL隐性转发：使用nat123域名解析的URL隐性转发。</p><p>4）80映射：使用nat123的80映射，并配置使用本地公网IP加速，发挥本地带宽优势。</p><p><img src="https://cdn.uu126.cn/wp-content/uploads/2016/03/20160313110741.jpg" alt="请输入图片描述" title="请输入图片描述"></p>