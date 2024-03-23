---
title: 黑群晖显示真实CPU核心信息补丁
date: 2020-05-06 12:38:31.0
updated: 2021-12-22 17:01:20.0
url: /archives/黑群晖显示真实cpu核心信息补丁
categories: 
- 智能终端
tags: 
- 黑群晖
---

使用黑群晖（这里以 DS918+ 为例）会发现一个问题，就是信息中心的 CPU 信息跟实物不吻合，对于强迫证的我们来说，这也是需要改正的，下面就来说说如何让它显示正确的 CPU 信息：

<!--more-->

<ul>
<li>首先下载补丁文件：到电脑上，解压出来得到一个文件夹 ch_cpuinfo，里面有一个“ch_cpuinfo”文件；</li>
<li>然后将 ch_cpuinfo 文件夹上传到黑群晖的共享文件夹，如 docker 目录下；</li>
<li>使用诸如 putty 等工具连接 SSH，并以 root 权限登录（可以先用 admin 账号登录，再使用<code>sudo -i</code>切换到 root 账号，提示输密码时直接输 admin 的密码），分别输入以下命令：</li>
</ul>

<pre><code class="language-python ">cd /volume1/docker/ch_cpuinfo
./ch_cpuinfo
</code></pre>

接着先选择数字<code>1</code>，再选择<code>y</code>。

<img src="https://cdn.lancn.cn/usr/uploads/2020/05/1840053542.jpg" alt="heiqunhui01.jpg" />

<ul>
<li>输完后就可以关闭 SSH 工具，退出当前群晖登录的用户，并且重新登录；</li>
<li>重新登录到桌面以后，打开控制面板的信息中心，就可以显示实际硬件信息了。</li>
</ul>

<img src="https://cdn.lancn.cn/usr/uploads/2020/05/1999277547.png" alt="heiqunhui02.png" />