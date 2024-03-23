---
title: 博客弃用Comodo证书
date: 2018-08-25 19:27:37.0
updated: 2021-12-22 17:01:20.0
url: /archives/博客弃用comodo证书
categories: 
- 网站建设
tags: 
- 网站
- Ghost
---

<!-- wp:paragraph -->
<p>由于之前Symantec（赛门铁克）家的SSL证书问题，后在Namecheap家免费换了Comodo三年证书（好像那时候好多人都换了吧），后来才知道这证书也不是三年都免费的，只是第一年免费后续就要交钱了，这不一年时间转眼即逝，邮箱也连续收到了好多封Namecheap的续费邮件，看了一下一年要好几十块大洋就没续了（穷屌丝一个呀……），不过除了火狐浏览器会报错，其它像谷歌、IE都可以正常访问，安卓、苹果手机访问也OK，用SSL证书检测显示证书已被吊销，为了让火狐不报错，那就用免费证书Let's encrypt，反正用Oneinstack也不用担心三个月一续的事，那就动手吧。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/ssl_comodo_01.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/ssl_lets-encrypt_01.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>换好之后再上SSL证书检测网站查看，评级由原来的F变为A+了，不过<strong>PCI DSS </strong>这项显示不合规，原因是因为：开启TLS1.0将导致PCI DSS不合规，为了一些兼容性就无所谓了（其实刚才在折腾过程中，又把Ghost弄挂了，就是因为这项不合规的事，结果是越搞越错，越错就Over了）。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/ssl_jianche01.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/ssl_jianche02.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>目前博客已经可以正常访问了，俺们也可以歇歇了，看会电影吧。</p>
<!-- /wp:paragraph -->