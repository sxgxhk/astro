---
title: Typecho后台增加极验证
date: 2017-06-27 03:22:06.0
updated: 2021-12-22 17:01:20.0
url: /archives/2480
categories: 
- 网站建设
tags: 
- typecho
---

<p>得空逛了一下Typecho社区，看见有后台登录验证插件，那就赶紧给自己的后台武装一下吧，省的一天到晚的裸奔（多少总会提升一点安全性吧@(你懂的)）。注册的步骤咱就不说了（不知道网址？百度搜索<code> 极验证 </code>），插件之前用的是摸鱼的（下载地址：<a href="https://www.moyu.win/archives/28.html">https://www.moyu.win/archives/28.html</a>），可是我从头到尾试了好几遍也没成功过，老是显示启用中，考虑到他也是修改前者的，那我就去找前者看看吧。</p><ol><li>先下载插件（链接: <a href="http://pan.baidu.com/s/1pLx52tX">http://pan.baidu.com/s/1pLx52tX</a> 密码: i7u5），我修改了Plugin.php，把其中一个JS文件的路径由http改为https（不改过的话，像我这种使用https 的站点会提示安全风险）</li><li>开始魔改代码了</li></ol><ul><li>增加/admin/geetest-code.php文件，用来返回极验服务响应数据：</li></ul><pre><code class="lang-php">
        Typecho</code></pre>