---
title: Win 7系统登陆密码破解方法
date: 2012-11-20 00:35:09.0
updated: 2021-12-22 17:01:20.0
url: /archives/win-7系统登陆密码破解方法
categories: 
- 生活百态
tags: 
---

Win 7系统登陆密码破解方法：
1. 进入pe微型系统
2.进入c:windowssystem32下
更改magnify.exe和cmd.exe的所有者为administrator，（右键属性-安全-高级-所有者-在“目前该项目的所有者更改为administration”）
更改magnify.exe和cmd.exe的权限为administration完全控制。
3.改名magnify.exe为mangify1.exe，改cmd.exe为magnify.exe
4.重启进入win7登陆界面，左下有个功能键，点击启用放大镜。
输入 net user administrator （当前管理员）1111（改后的密码） 回车
<div>net user administrator /active:yes （由于Vista以上系统默认情况下都是停用Administrator帐户的，可通过该命令启用Administrator。如果要停用该帐户只需将后面参数改成 /active:no ）</div>
<div>注：这些操作需要重启系统方可生效</div>
<div>5、使用Administrator进入系统，直接在“用户帐户”中将要破解的帐户密码删除就可以了</div>