---
title: Ghost博客时间汉化方案
date: 2017-10-06 20:45:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/2502
categories: 
- 网站建设
tags: 
- Ghost
---

<p>本站目前使用的Ghost主题是<code> Kaldorei </code>，感觉小蘿蔔丁做的主题还是非常不错的，而且这个主题目前已经支持Ghost1.X版本了（貌似我也是刚晓的，因为本站的Ghost版本已由<code> Ghsot0.7.4汉化版 </code>升级回<code> Ghost1.6.2 </code>,没有升到最新的<code> 1.11.1 </code>是因为在阿里云做的快照是 <code> 1.6.2 </code>，没升级而已），目前测试了一下，还没发现问题，归档当然是OK的了！就是由于是Ghost英文版的，所以显示的博文时间也是英文，这不按照小蘿蔔丁给的办法也汉化了，具体的看小蘿蔔丁原文：</p><blockquote><p>使用Ghost搭建博客已经有两年多了。就连自己开源的主题Kaldorei也已经一年零7个月，到今天为止ghost-theme-kaldorei已经获得了100个star。刚刚破百。感谢这100位coder的支持。ghost 从我开始用的的0.7.x版本已经升到了1.x版本。期待已久的ghost也已经发布了1.x正式版。最近看下稳定版本在1.8.4。发展迅猛。不过到现在貌似也没有看到文档中有关日期的国际化相关API。<br />如何让博客的日期汉化<br />那么只能自己想办法修改了。分析下博客中使用到日期的模版。阅读官方文档得知这里谈到的日期ghost提供的日期格式化助手<code> date.js </code>。而这个助手使用的是<code> moment.js </code>。这就好办了。前端同学对<code> moment.js </code>并不陌生。它是支持国际化的。我们找到date助手的代码，修改它就好了。</p></blockquote><p>路径：</p><pre><code class="lang-bash">/ghost/core/server/helpers/date.js</code></pre><p>打开这个文件，修改如下：</p><h4>&lt; 1.x版本（如果用的是Ghost0.7.4汉化版，可以不用修改）</h4><pre><code class="lang-bash">// # Date Helper
// Usage: `{{date format=&quot;DD MM, YYYY&quot;}}`, `{{date updated_at format=&quot;DD MM, YYYY&quot;}}`
// Formats a date using moment.js. Formats published_at by default but will also take a date as a parameter
var moment          = require('moment'),
    date;
moment.locale('zh-CN');            // 日期汉化  </code></pre><h4>&gt;= 1.x版本</h4><pre><code class="lang-bash">// # Date Helper
// Usage: `{{date format=&quot;DD MM, YYYY&quot;}}`, `{{date updated_at format=&quot;DD MM, YYYY&quot;}}`
//
// Formats a date using moment-timezone.js. Formats published_at by default but will also take a date as a parameter
var proxy = require('./proxy'),
    moment = require('moment-timezone'),
    SafeString = proxy.SafeString;
moment.locale('zh-CN');            // 日期汉化 </code></pre><p>保存之后，重启博客就会看到日期已经汉化了。</p>