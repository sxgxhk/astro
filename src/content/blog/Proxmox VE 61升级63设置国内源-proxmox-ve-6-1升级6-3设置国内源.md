---
title: Proxmox VE 6.1升级6.3设置国内源
date: 2021-03-24 12:42:15.0
updated: 2021-12-22 17:01:20.0
url: /archives/proxmox-ve-6-1升级6-3设置国内源
categories: 
- IT综合技术
tags: 
- PVE
---

Proxmox VE 以下简称 PVE，相信折腾 All in one 或黑群晖、软路由，或多或少会有接触，作为底层平台各项功能还是不错，不过毕竟是老外的东西，在国内使用还是还会碰到一些问题，比如版本升级，下面就以我自己个人升级作一个简单教程（方便自己哪天忘了好查看），以下教程为网络整理所得，但经本人测试升级成功。

<!--more-->

<ol>
<li>删除企业源</li>
</ol>

<pre><code class="">rm -rf /etc/apt/sources.list.d/pve-enterprise.list
</code></pre>

<ol start="2">
<li>下载秘钥</li>
</ol>

<pre><code class="">wget http://mirrors.ustc.edu.cn/proxmox/debian/proxmox-ve-release-6.x.gpg -O /etc/apt/trusted.gpg.d/proxmox-ve-release-6.x.gpg
</code></pre>

<ol start="3">
<li>添加国内源</li>
</ol>

<pre><code class="">echo "deb http://mirrors.ustc.edu.cn/proxmox/debian/pve buster pve-no-subscription" &gt;/etc/apt/sources.list.d/pve-install-repo.list
</code></pre>

这里要注意下，很多教程会设置成错误 deb http://mirrors.ustc.edu.cn/proxmox/debian/pve strech pve-no-subscription 造成无法升级为 pve6.2

strech--debian 9--pve 5.x
buster--debian 10--pve 6.x

<ol start="4">
<li>建议同时使用国内 debian 源，修改 /etc/apt/sources.list 文件，添加如下内容：</li>
</ol>

<pre><code class="">echo "deb http://mirrors.ustc.edu.cn/debian buster main contrib
deb http://mirrors.ustc.edu.cn/debian buster-updates main contrib
deb http://mirrors.ustc.edu.cn/debian-security buster/updates main contrib" &gt; /etc/apt/sources.list
</code></pre>

pve_ceph 设置国内源
原配置文件：/etc/apt/sources.list.d/ceph.list

<pre><code class="">echo "deb http://mirrors.ustc.edu.cn/proxmox/debian/ceph-nautilus buster main" &gt; /etc/apt/sources.list.d/ceph.list
</code></pre>

<ol start="5">
<li>最后执行</li>
</ol>


```
apt update
apt update && apt dist-upgrade