---
title: Windows VPS如何修改远程桌面端口
date: 2015-03-19 06:44:11.0
updated: 2021-12-22 17:01:20.0
url: /archives/windows-vps如何修改远程桌面端口
categories: 
- 网站建设
tags: 
---

众所周知，Windows系统默认的远程桌面端口是3389，各种黑客软件首要扫描的端口即3389端口。因此，更改默认的远程桌面端口是尤为重要的。本文介绍如何修改Windows系统默认的远程桌面端口。
<span id="more-108"></span>
1、WIN+R打开运行窗口，输入regedit打开注册表编辑器。
2、找到以下子项：
<pre class="lang:reg decode:true " >[HKEY_LOCAL_MACHINESYSTEMCurrentControlSetControlTerminalServerWdsrdpwdTdstcpPortNumber</pre>
3、在编辑菜单中，单击修改，然后单击十进制.
4、将3389修改为其他端口号，例如9852。（请注意不要使用常见端口）
5、找到以下子项：
<pre class="lang:reg decode:true " >[HKEY_LOCAL_MACHINESYSTEMCurrentControlSetControlTerminal ServerWinStationsRDP-Tcp]</li>
</pre>
6、在编辑菜单中，单击修改，然后单击十进制.
7、将3389修改为其他端口号，例如9852。（请注意不要使用常见端口）
<a href="http://uu126.cn/wp-content/uploads/2015/03/yuancheng01.jpg"><img class="alignnone size-full wp-image-1618" src="http://uu126.cn/wp-content/uploads/2015/03/yuancheng01.jpg" alt="yuancheng01" width="322" height="178" /></a>
8、检查VPS是否设置了端口过滤：本地连接-属性-TCP/IP属性-高级-选项-TCP/IP筛选。如果启用了筛选功能，请务必将修改后的端口添加到允许列表。
<a href="http://uu126.cn/wp-content/uploads/2015/03/yuancheng02.jpg"><img class="alignnone size-full wp-image-1619" src="http://uu126.cn/wp-content/uploads/2015/03/yuancheng02.jpg" alt="yuancheng02" width="416" height="321" /></a>
9、重启VPS。
10、在远程桌面连接中，地址更改为：ip:端口