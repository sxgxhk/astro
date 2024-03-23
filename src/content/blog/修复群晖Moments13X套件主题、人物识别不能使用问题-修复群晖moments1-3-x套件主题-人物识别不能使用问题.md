---
title: 修复群晖Moments1.3.X套件主题、人物识别不能使用问题
date: 2020-10-12 12:40:10.0
updated: 2021-12-22 17:01:20.0
url: /archives/修复群晖moments1-3-x套件主题-人物识别不能使用问题
categories: 
- 智能终端
tags: 
- 黑群晖
---

最近碰到自己家的黑群晖（DS918+）新装的 Moments 存在无法智能识别人物和主题分类等功能，如果你的黑群晖系统是 6.2.2 以下的系统，可以直接点击下载 Moments1.2 旧版本解决问题。6.2.3 系统无法安装 1.2 版本的 Moments，会提示版本不兼容，下面我们就来修复 1.3Moments 套件智能识别的问题。

<!--more-->

修复原理：将 Moments1.2 版本的 libsynophoto-plugin-detection.so 文件替换到 Moments1.3 版本中使用。

<ol>
<li>停止 Moments 套件，群晖控制面板-终端机和 SNMP-启用 SSH 功能。</li>
<li>通过 SSH 登录群晖，我使用的是 WinSCP 结合 putty，登录 root 账号，6.2.2 切换 root 用户指令</li>
</ol>

<pre><code class="">//管理员切换root用户
sudo -i
</code></pre>

这里切换到 root 帐户会让你输入密码，就输入当前管理员密码（比如：admin 的密码）或有管理员权限的密码

<ol start="3">
<li>备份原文件（万一替换出问题了，还可以换回去）</li>
</ol>

<pre><code class="">cd/var/packages/SynologyMoments/target/usr/lib
//备份原文件
mv libsynophoto-plugin-detection.so libsynophoto-plugin-detection.so.bak
//下载libsynophoto-plugin-detection.so
wget https://wp.gxnas.com/wp-content/uploads/2019/10/libsynophoto-plugin-detection.so
//修改libsynophoto-plugin-detection.so文件拥有者为SynologyMoments
chown SynologyMoments:SynologyMoments libsynophoto-plugin-detection.so
chmod a+x libsynophoto-plugin-detection.so
</code></pre>

如果是用 Winscp 等工具连接的话，可以看到备份好的原文件
<img src="https://cdn.lancn.cn/usr/uploads/2020/10/3852246509.png" alt="qh_moments01.png" />

如果在执行 wget 命令出错时，可在后面加上参数或者手动上传文件到指定目录。一般修改完成后退出，启动 Moments 套件，并重新建立索引，就可以正常 AI 识别人物和主题了。