---
title: Apache用.htaccess来实现强制https访问
date: 2016-12-05 05:22:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/2400
categories: 
- 网站建设
tags: 
---

<p>我们可以用Apache的.htaccess来实现http强制跳转到https访问网站。<br />代码如下：</p><pre><code>RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://cdn.uu126.cn/$1 [R,L]</code></pre><p>如果是在子目录，可以用:</p><pre><code>RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteCond %{REQUEST_URI} subfolder
RewriteRule ^(.*)$ https://cdn.uu126.cn/blog [R,L]</code></pre>