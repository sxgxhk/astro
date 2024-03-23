---
title: Typecho搬家后文章、后台无法打开的解决方案
date: 2017-07-11 00:13:45.0
updated: 2021-12-22 17:01:20.0
url: /archives/2484
categories: 
- 网站建设
tags: 
- typecho
---

<p>说来都觉得自己有那么点无聊，当初从阿里云转到华为云，然后现在又转回去——折腾啊！搬回到阿里云，顺手把OSS也挂载了当硬盘使，这样下次再折腾就不用老是先备份下载了。老样子还是使用Oneinstack家的一键包搭建的LNMP环境（本来还想再折腾一下Ghost的，不过想想还是算了），配置好站点，然后接着导入数据库，再把博客相关文件上传到配好的目录，本以为大功造成时，结果……</p><p>不管是访问后台，还是文章，都报<code> Access denied </code>，好郁闷呀！找了度娘，没看到什么好的答案，结果在Segmentfault上找到了方法，那就是修改<code> php.ini </code>，将<code> cgi.fix_pathinfo </code>的值由<code> 0 </code>改为<code> 1 </code>，怎么找这个文件？可以在<code> phpinfo.php </code>里看到具体的路径。修改好之后，重启PHP和nginx即可或者也可以直接重启服务器。<br /><img src="https://blog.uu126.cn/usr/uploads/2017/07/2627704961.jpg" alt="typecho_cw1.jpg" title="typecho_cw1.jpg"></p><p>问题解决，可以正常使用了</p>