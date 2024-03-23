---
title: Ghost博客使用fancybox的正确姿势
date: 2017-10-06 01:49:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/2501
categories: 
- 网站建设
tags: 
- Ghost
---

<p>在Ghost博客后台，使用Markdown编辑器。</p><p><code> Ctrl + Shift + I </code>，图片快捷键，生成代码：<code> ![](https://) </code></p><p><code>Ctrl + K </code>，链接快捷键，生成代码：<code> [](https://) </code></p><p>正确格式</p><p>fancybox实现后实际上是个图片链接，So，把图片放入链接里。</p><p>格式：<code> [![](https://)](https://) </code></p><p>例如：<code> [![风景 - 1](http://xlbd.me/content/images/2016/05/vies1.jpg)](http://xlbd.me/content/images/2016/05/vies1.jpg) </code></p><p><a href="http://xlbd.me/content/images/2016/05/vies1.jpg"><img src="http://xlbd.me/content/images/2016/05/vies1.jpg" alt="风景 - 1" title="风景 - 1"></a></p><p><a href="http://xlbd.me/content/images/2016/05/view2.jpg"><img src="http://xlbd.me/content/images/2016/05/view2.jpg" alt="风景 - 2" title="风景 - 2"></a></p><p><a href="http://xlbd.me/content/images/2016/05/view3.jpg"><img src="http://xlbd.me/content/images/2016/05/view3.jpg" alt="风景 - 3" title="风景 - 3"></a></p><p>方式可能不一定适用于所有Ghost主题，反正本站目前在用的主题是这样子的。</p><p>本博文转载自：小蘿蔔丁 <a href="http://xlbd.me/how-to-use-fancybox-in-ghost-blog/"><a href="http://xlbd.me/how-to-use-fancybox-in-ghost-blog/">http://xlbd.me/how-to-use-fancybox-in-ghost-blog/</a></a></p>