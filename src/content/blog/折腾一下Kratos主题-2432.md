---
title: 折腾一下Kratos主题
date: 2017-03-18 06:05:09.0
updated: 2021-12-22 17:01:20.0
url: /archives/2432
categories: 
- 网站建设
tags: 
- typecho
---

<p>前几日逛Typecho论坛，看到有朋友移植了原WP主题Kratos，看看挺喜欢的（其实是有点想念WP时用过的9IPHP主题了，能力有限移植不了），那就耍耍呗，换掉Hran的Mirages主题（不知道Hran童鞋会不会有意见呀），下载并上传，接着设置主题然后又…………（每次换主题都做着这些重复的事），大致还是OK的，就是有一些地方需要修改一下，先亮一下修改后的：</p><p>my_uu126_01.jpg</p><p>封面上修改的不多，主要的不是在内容页上，增加了文章二维码，打赏，另外对代码高亮进行了美化，对文章页广告代码小修改，自认为比原先的要好看。</p><h4>打赏</h4><p>网上找的我也只是略略修改一下，新建一个ds.js文件，内容如下：</p><pre><code class="lang-java">(function($){
    var id = Date.now();</code></pre>