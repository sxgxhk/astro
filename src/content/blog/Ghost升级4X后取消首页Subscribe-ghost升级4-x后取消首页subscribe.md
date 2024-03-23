---
title: Ghost升级4.X后取消首页Subscribe
date: 2021-04-18 12:44:00.0
updated: 2021-12-23 13:58:43.0
url: /archives/ghost升级4-x后取消首页subscribe
categories: 
- 网站建设
tags: 
- Ghost
---

回归 Ghost 有一小段日子了，现在用 Docker 部署感觉非常方便（想想以前搭建各种环境啥的，那是一个累），当然 Docker 部署在日常使用中也碰到一些问题，有些已经解决了（比如首页默认显示 localhost:2368 等），有些还在摸索解决中，谁叫俺学艺不精呢。

<!--more-->

因为之前用过 Ghost，所以都有备份，搭建好之后只要在实验室中导入即可，之前用的是 3.9 的版本，这次升级到 4.2 之后，发现首页右下角老是都是显示“Subscribe",甚是不爽，如下图：

<img src="https://blog.uu126.cn/usr/uploads/2021/04/3660953661.png#vwid=652&vhei=397" alt="Ghost-4.x-01.png" />

百度一番果然有解决方法，在 <code>settings</code> 中的 <code>Code injection</code>添加一段 css 代码屏蔽了即可，具体如下：

<img src="https://blog.uu126.cn/usr/uploads/2021/04/2766528818.png#vwid=975&vhei=529" alt="Ghost-4.x-02.png" />

<pre><code class="language-css ">&lt;style&gt;
#ghost-portal-root {
  display: none;
}
.nav-login, .nav-subscribe {
    display: none;
  }
&lt;/style&gt;
</code></pre>

保存后，再刷新看一下，就可以发现首页右下角的<code>Subscribe</code>不见了，当然也就看着舒服了。

本文部分内容来自：https://www.bilimoe.com/ghost-4-x/