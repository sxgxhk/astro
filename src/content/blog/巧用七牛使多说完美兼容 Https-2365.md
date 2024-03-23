---
title: 巧用七牛使多说完美兼容 Https
date: 2016-11-26 22:22:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/2365
categories: 
- IT综合技术
tags: 
- 网站
---

<p>之前写过一篇文章“让Typecho中的多说头像支持HTTPS"，头像是可以支持Https了，但里面的表情却不行，这不又看到好文说可以完美兼容Https，赶紧照样画葫芦用起来呗：<br />1、设置七牛，将镜像源设置为<a href="https://yourdomain.com/proxy/即可">https://yourdomain.com/proxy/即可</a>。<br />2、修改 Embed.js，首先从 <a href="https://static.duoshuo.com/embed.js">https://static.duoshuo.com/embed.js</a> 下载然后格式化。<br />3、修改头像，位于 580 行附近，搜索 avatarUrl: function(e) { 直达。</p><pre><code class="lang-java">    if (document.location.protocol == &quot;https:&quot;) {
    if (e.avatar_url) {
        var matched;
        if (matched = e.avatar_url.match(/^([^\/]*(\/\/q\.)*(\/\/app\.)*qlogo\.cn\/.+\/)\d{2}$/)) {
            e.avatar_url = matched[1] + &quot;100&quot;; // 50的图高分屏下会很模糊，改不改随你。不改的话整个 If 分支就不需要了。
            e.avatar_url = e.avatar_url.replace(/^http\:\/\//, &quot;https://&quot;);
        } else if (matched = e.avatar_url.match(/^(.*avatar\.duoshuo\.com\/avatar\-)\d{2}(\/.+)$/)) {
            e.avatar_url = matched[1] + &quot;100&quot; + matched[2]; // 50的图高分屏下会很模糊，改不改随你。不改的话整个 If 分支就不需要了。
            e.avatar_url = e.avatar_url.replace(/^http\:\/\//, &quot;https://&quot;);
        } else if (e.avatar_url.match(/^http:\/\/wx\.qlogo\.cn.*$/) || e.avatar_url.match(/^.*avatar\.duoshuo\.com.*$/)) {
            e.avatar_url = e.avatar_url.replace(/^http\:\/\//, &quot;https://&quot;);
        } else if (matched = e.avatar_url.match(/^(.*qlogo\.cn\/.+\/)\d{2}$/)) {
            e.avatar_url = matched[1] + &quot;100&quot;; // 50的图高分屏下会很模糊，改不改随你。不改的话整个 If 分支就不需要了。
        }  else if (e.avatar_url.match(/^.*img\d+\.douban\.com.*$/)) {
            e.avatar_url = e.avatar_url.replace(/img\d+\.douban\.com/, &quot;img2.doubanio.com&quot;);//豆瓣无需镜像
        }
        if (e.avatar_url.match(/^http:\/\/.+$/)) {
            e.avatar_url = &quot;https://yours.qnssl.com/&quot; + base64_encode(e.avatar_url);
            // 像大神们的那种反代大概就可以改成这样：
            // e.avatar_url = &quot;https://yours.qnssl.com/&quot; + e.avatar_url.replace(/^http\:\/\//, &quot;&quot;);
            // 普通的地址：
            // e.avatar_url = &quot;https://yourdomain.com/proxy?src=&quot; + e.avatar_url;
        }
    } else {
        var matched = rt.data.default_avatar_url.match(/^(.*avatar\.duoshuo\.com\/avatar\-)\d{2}(\/.+)$/);
        if (matched != null) {
            rt.data.default_avatar_url = matched[1] + &quot;100&quot; + matched[2]; // 50的图高分屏下会很模糊，改不改随你。不改的话整个 If 分支就不需要了。
        }
    }
}
// 默认头像现在多说已经支持 Https, 因此不需要修改。
return e.avatar_url || rt.data.default_avatar_url</code></pre><p>4、修改评论中的表情和图片，位于 740 行附近，搜索s.message直达。</p><pre><code class="lang-java">        var matched;</code></pre>