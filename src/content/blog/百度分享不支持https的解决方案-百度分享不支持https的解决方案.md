---
title: 百度分享不支持https的解决方案
date: 2016-10-29 22:30:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/百度分享不支持https的解决方案
categories: 
- 网站建设
tags: 
- Wordpress
---

<p>博客自从开启 Https 之后 ，百度分享就不能用了！百度自己虽然天天在喊要Https，可自己的很多功能却以不支持（是不是有那么点自相矛盾的感觉），虽然网上也有很多分享工具，可是给我的感觉还是百度的好一点，偏爱一点吧（呵呵），网上找了很多，终于发现有办法可以解决，那就是使用替代办法，将百度分享的文件（包括所有的JS，CSS等统统Down下来，放在自己的博客里面使用，当然也可以放在比如七牛、又拍云等），俺比较穷，还是先扔在博客目录里使用吧，先下载：</p><p>Github地址（推荐，2016.10.2更新）：<a href="https://github.com/hrwhisper/baiduShare">https://github.com/hrwhisper/baiduShare</a></p><p>static 解压后丢到站点根目录下即可。</p><p>然后对应的百度分享代码中，把<a href="http://bdimg.share.baidu.com/改为">http://bdimg.share.baidu.com/改为</a> ：</p><pre><code>.src='http://bdimg.share.baidu.com/static/api/js/share.js?v=89860593.js?cdnversion='+~(-new Date()/36e5)];&amp;lt;/script&amp;gt;
改为
.src='/static/api/js/share.js?v=89860593.js?cdnversion='+~(-new Date()/36e5)];&amp;lt;/script&amp;gt;
</code></pre><p>丢完之后别忘了刷新一下，如果使用了CDN等缓存工具的，还要再清一下缓存，这时你可以发现：地址栏上的小绿锁，同时百度分享也出来了，试了一下，可以成功分享，说明一切OK了。</p>