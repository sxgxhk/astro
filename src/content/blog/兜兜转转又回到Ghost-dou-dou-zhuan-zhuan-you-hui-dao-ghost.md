---
title: 兜兜转转又回到Ghost
date: 2022-10-22 21:31:00.0
updated: 2023-04-22 00:05:36.419
url: /archives/dou-dou-zhuan-zhuan-you-hui-dao-ghost
categories: 
- 网站建设
tags: 
- 随笔
- Ghost
---

博客已经长草好久了，虽然中间有很多次都想啰嗦一下，可到最后都…………。虽然博客内容没怎么更新，但折腾还是常用的，倒腾个主题、平台啥的——算是瞎折腾吧，把最主要的事——内容扔到脑后，，没办法这就是我。我的博客用过Wordpress，Typecho，Ghost等，虽然比较会折腾，但其实我也就只会抄抄写写，深层次的只能摊手了。
<!--more-->
<p><img src="https://image.uu126.cn/2022/10/Ghost.webp#vwid=960&amp;vhei=576" alt="" /></p>
<p>之所以这次又回到Ghost，那是因为骨子里的那股欣赏吧，我是从0.7.4中文版本（当时国内的汉化版本）开始用起的，后面因为一些原因又辗转到Wordpress，Typecho。这次回来除了正常部署外，还把图片从本地改成又拍云托管，同时取消了评论（具体什么时候恢复评论到时再看吧，至少短时间内不会有），下面就把折腾中碰到的一些问题记录一下。</p>
<p>又拍云的Ghost插件用的是这家的：<a href="https://github.com/leoskey/ghost-upyun-store">https://github.com/leoskey/ghost-upyun-store</a> ，但是部署我是按另外一个办法，这家给的办法我试了老是报错，可能是我哪里没弄好吧。</p>
<ul>
<li>
<p>通过 Git
在Ghost目录下的<code>content</code>在命名中创建一个新文件夹<code>adapters/storage</code></p>
</li>
<li>
<p>克隆到<code>storage</code>目录中</p>
</li>
</ul>
<pre><code class="language-python">cd [path/to/ghost]/content/adapters/storage
git clone https://github.com/leoskey/ghost-upyun-store.git</code></pre>
<ul>
<li>安装依赖项</li>
</ul>
<pre><code class="language-python">cd ghost-upyun-store
npm i</code></pre>
<ul>
<li>修改Ghost目录下的<code>config.production.json</code>，按格式加入下列代码：</li>
</ul>
<pre><code class="language-python">"storage": {
  "active": "ghost-upyun-store",
  "ghost-upyun-store": {
    "bucket": "&lt;your bucket name&gt;",
    "operator": "&lt;your operator&gt;",
    "password": "&lt;your password&gt;",
    "prefix": "YYYY/MM/",
    "domian": "&lt;your bucket domain&gt;"
  }
}</code></pre>
<h3>注意，这里的<code>&lt;your bucket domain&gt;</code>要写成 <code>https://绑定在又拍云的域名</code>或者<code>http://绑定在又拍云的域名</code>。如果不带<code>https://</code> 或<code>http://</code>的域名，那么图片上传后，文章显示的路径会出错导致不能正常显示！</h3>
<p>我这回部署的Ghost并没使用Docker，那是因为本人Docker玩的还不是很溜，经常搞崩容器导致出错，所以这次老老实实采用Ghost官方的教程，一步步配置而来。</p>
<p><img src="https://image.uu126.cn/2022/11/manwei.webp#vwid=500&amp;vhei=270" alt="" /></p>