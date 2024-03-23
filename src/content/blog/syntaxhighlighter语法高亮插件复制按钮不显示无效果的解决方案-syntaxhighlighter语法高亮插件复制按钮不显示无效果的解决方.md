---
title: syntaxhighlighter语法高亮插件复制按钮不显示无效果的解决方案
date: 2016-01-04 00:56:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/syntaxhighlighter语法高亮插件复制按钮不显示无效果的解决方
categories: 
- IT综合技术
tags: 
- Wordpress
---

<p>用了一段时间发现，syntaxhighlighter好用是好用，就是不能复制，上网搜了一下，发现有很多人遇到了这个问题，后来知道是clipboard.swf惹的祸，后台安装好以后，自带的clipboard.swf是个空文件0KB，找到了一个可用的clipboard.swf，替换以后就可以了，简单滴很~~（所以可以先往下看【二、替换文件】如果替换以后还不行，再看【一、修改文件】照着修改）<br />一、找到这个目录<code>/wp-content/plugins/syntaxhighlighter/syntaxhighlighter.php</code>，然后修改文件：</p><p><code>SyntaxHighlighter.all();</code></p><p>前加</p><pre><code class="lang-php">SyntaxHighlighter.config.clipboardSwf = ‘syntaxhighlighter2/scripts/clipboard.swf’;</code></pre><p>请根据个人情况自行修改<br />二、也可以找到这个文件进行替换，具体的目录在：<br /><code>/wp-content/plugins/syntaxhighlighter/syntaxhighlighter2/scripts/clipboard.swf</code><br />下载地址：<a href="https://pan.baidu.com/s/1kU1hQXT"><a href="https://pan.baidu.com/s/1kU1hQXT">https://pan.baidu.com/s/1kU1hQXT</a></a></p>