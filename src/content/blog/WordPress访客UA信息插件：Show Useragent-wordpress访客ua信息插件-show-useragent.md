---
title: WordPress访客UA信息插件：Show Useragent
date: 2016-07-06 06:08:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/wordpress访客ua信息插件-show-useragent
categories: 
- IT综合技术
tags: 
- Wordpress
---

<p>一直想给自己的博客加个访客UA信息（如下图），可……，不能再拖了，赶紧动手添加吧，网上逛了逛，就选Show Useragent吧，因为本人不是太喜欢插件的形式，所以能代码化就……（其实代码多了也会影响程序的执行率的，多少的问题）。</p><p><img src="https://cdn.uu126.cn/wp-content/uploads/2016/07/woredpress-ua.png" alt="请输入图片描述" title="请输入图片描述"><br />先下载张戈提供的汉化包，然后将解压后的<code>show-useragent</code>文件夹上传到正在使用的主题目录下，接着在主题<code>functions.php</code>里添加如下代码,###注意就添加在``之间：</p><pre><code class="lang-php">//显示访客信息
include(&quot;show-useragent/show-useragent.php&quot;);</code></pre><p>接着在主题目录下的<code>comments.php</code>里查找<code>wp_list_comments</code>，如：本站使用的是知更鸟的begin主题 ，返回的是：</p><pre><code class="lang-php">?php wp_list_comments( 'type=comment&amp;amp;callback=mytheme_comment' ); </code></pre><p>如果发现<code>callback=XXXXX</code>回调函数时，说明主题是自定义了评论列表，那么直接去查找后面回调函数位置，然后在合适的位置加入以下代码：</p><pre><code class="lang-php">?php CID_print_comment_flag(); echo ' ';CID_print_comment_browser(); </code></pre><p>本站（知更鸟的begin主题）的位置是在主题目录的<code>inc/function</code>里的<code>comment-template.php</code>里，改好之后的位置如下：</p><pre><code class="lang-php">span class=&quot;comment-meta commentmetadata&quot; php CID_print_comment_flag(); echo ' ';CID_print_comment_browser(); </code></pre><p>全部弄好之后刷新一下，就可以在评论里看到相关访客的UA信息了。补充一下，里面有一个IP文件是需要更新的，详细的更新办法可参考这个：<a href="http://www.speedfly.cn/9488.html"><a href="http://www.speedfly.cn/9488.html">http://www.speedfly.cn/9488.html</a></a></p>