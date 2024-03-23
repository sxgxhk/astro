---
title: Hexo一键部署到阿里云OSS
date: 2020-03-18 22:21:45.0
updated: 2021-12-22 17:01:20.0
url: /archives/hexo一键部署到阿里云oss
categories: 
- 网站建设
tags: 
- 网站
- 阿里云
- hexo
---

鉴于最近github从中国大陆访问网速较慢，而且现在国内阿里云oss、腾讯云对象储存等的开始支持将静态网站部署在上面，而且访问速度还可以，加上最近本博主又开始在折腾Hexo了，Hexo的好处是可以生成静态文件，这样就可以多个地方同时在线，比如Github、Coding、OSS等，目前本站已经部署在前面说的那个地方，今天顺便把阿里云的OSS也上了吧。另外像腾讯云的COS上部署也差不多，改天也可以再尝试一下。

<!--more-->

想部署在OSS上，还得满足如下几个条件（有点废话）：

<ul>
<li>本地已经安装好了hexo(即可以通过http://localhost:4000可以访问)</li>
<li>拥有阿里云账号（部署静态网站需要实名认证）和备案的域名</li>
</ul>

本次废话教程将重点从第二部分开始，本地安装Hexo博客就不再多说了，网上类似的教程很多，貌似也不是很难

<ul>
<li>在您的hexo项目目录下执行：</li>
</ul>

<pre><code class="language-python ">npm install hexo-deployer-ali-oss --save
</code></pre>

<ul>
<li>在Hexo项目配置文件<code>_config.yml</code>中添加如下部署配置：</li>
</ul>

<pre><code class="language-python ">deploy:
  type: ali-oss
  region: &lt;您的oss 区域代码&gt;
  accessKeyId: &lt;您的oss  accessKeyId&gt;
  accessKeySecret: &lt;您的oss accessKeySecret&gt;
  bucket: &lt;您的bucket name&gt;
</code></pre>

小说明：
<code>type</code>：不用改
<code>region</code>：OSS所在区域，按实际修改成如：<code>oss-cn-hangzhou</code>的格式
<code>accessKeyId</code> 和 <code>accessKeySecret</code>：这个登录阿里云后，点击右边的头像下 <code>AccessKey管理</code>，就可以找到
<code>bucket</code>：Bucket 名称

<ul>
<li>改好之后记得保存，保存好之后再执行<code>hexo d</code>，一般没问题的话就可以将Hexo生成的静态文件上传到OSS中了，刷新一下你的小域名就可以看到最新动态了。</li>
</ul>

注：默认情况下，将文件上传到阿里云OSS bucket的根目录下，如果需要部署到其他目录，请在deploy下添加remotePath选项进行指定

<pre><code class="language-python ">remotePath:&lt;您要部署的目录&gt;
</code></pre>

另外在创建阿里云OSS存储桶（Bucket)时，应将存储权限设置为公共读。如果碰到网站菜单点击没反应，比如点击归档、友链等，但在本地测试又是好的，一般都是OSS基础设置中的子目录首页功能没有开始，具体开通如下图：
<img src="https://cdn.lancn.cn/usr/uploads/2020/03/1663135651.png" alt="hexo-aliyun01.png" />
<img src="https://cdn.lancn.cn/usr/uploads/2020/03/772832735.png" alt="hexo-aliyun02.png" />