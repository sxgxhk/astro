---
title: VMware（ESXI）官网账号注册报错的解决办法
date: 2022-12-10 21:25:00.0
updated: 2023-04-22 00:03:05.632
url: /archives/vmwareesxi-guan-wang-zhang-hao-zhu-ce-bao-cuo-de-jie-jue-ban-fa
categories: 
- 我的地盘
tags: 
- ESXI
---

最近想给我的小主机换个平台，之前用过PVE、Unraid，就是没用过ESXI，这不好奇心驱使，想去官网下载个耍耍，结果生生卡在注册大关上，不管是中文还是英文，都是报错，如：
<!--more-->
<p><img src="https://image.uu126.cn/2022/12/view.jpg#vwid=978&amp;vhei=493" alt="" /></p>
<ul>
<li>
<p>中文验证码死活输不进，一直大写。</p>
</li>
<li>
<p>Postal code一直报错。</p>
</li>
</ul>
<p>找了一圈教程，终于在CSDN上找到了解决办法，关于中文验证码：</p>
<ul>
<li>
<p>可以限制记事本输入在复制到验证码框。</p>
</li>
<li>
<p>把语言切换成English。</p>
</li>
</ul>
<p>关于Postal code一直报错：</p>
<ul>
<li>
<p>在地址前面加个数字。</p>
</li>
<li>
<p>输入霉国的城市。</p>
</li>
</ul>
<pre><code class="language-python">Address 1    1ONE
Address 2    
City    SACRAMENTO
Postal code    94203-0001
Country/Territory    United States
State or province    California</code></pre>
<p>这地址前面加个<code>1</code>，如果好使，终于注册上账号，可以去下载耍耍了（对官网的依赖性重，其它途径下载来的总有点……）</p>