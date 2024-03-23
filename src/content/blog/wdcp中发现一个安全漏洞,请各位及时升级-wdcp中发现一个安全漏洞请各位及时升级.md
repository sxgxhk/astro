---
title: wdcp中发现一个安全漏洞,请各位及时升级
date: 2014-10-31 22:13:11.0
updated: 2021-12-22 17:01:20.0
url: /archives/wdcp中发现一个安全漏洞请各位及时升级
categories: 
- 网站建设
tags: 
---

<span style="font-size: medium;"><span style="font-family: 微软雅黑;">近期<span id="rlt_8">WDCP</span>官方发现wdcp_v2.5.10之前的版本有一个严重<span id="rlt_4">安全</span><span id="rlt_7">漏洞</span>，目前已经发现多例因wdcp漏洞导致的用户ECS服务器被入侵的事件，还可能会导致更多的不安全因素，<b>为了网站的安全，请大家尽快<span id="rlt_6">升级</span>到最新版本。</b></span></span>
<span style="font-size: medium;"><span style="font-family: 微软雅黑;">       升级方法：          </span></span>
<span style="font-size: medium;"><span style="font-family: 微软雅黑;">       <span style="color: #800000;">1）直接在后台升级就可以            </span></span></span>
<span style="font-size: medium; color: #800000;"> <span style="font-family: 微软雅黑;">       2）如果无法在后台升级,可用如下方法 ，SSH登录<span id="rlt_2">服务器</span> ，<span id="rlt_5">操作</span>如下命令完成即可。</span></span>
<pre class="prettyprint linenums">wget http://down.wdlinux.cn/down/wdcp_v2.5.tar.gz
tar zxvf wdcp_v2.5.tar.gz -C /
</pre>
WDCP官方也出了补丁升级的通知，详见：<a href="http://www.wdlinux.cn/bbs/thread-37476-1-1.html" target="_blank">http://www.wdlinux.cn/bbs/thread-37476-1-1.html</a>