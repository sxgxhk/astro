---
title: Ghost1.X博客使用记一
date: 2017-09-28 23:24:05.0
updated: 2021-12-22 17:01:20.0
url: /archives/2491
categories: 
- 网站建设
tags: 
- Ghost
---

<p>之前用过中文版（应该叫汉化版）0.74，挺好的，很多功能都给你内置好了，比如图片存储直接可以通过修改Ghost目录下的config.js中的代码实现，就像我用七牛，只要把七牛的密钥、空间名等输入即可，可到了Ghost1.X之后，没要稍微复杂点了，加上目前还没出现汉化版（要幸苦王赛童鞋了，抓紧搞……），只能通过类似于插件的办法安装。Ghost1.X跟以往的版本一样，依旧没有评论系统，这点可真没办法跟Wordpress或Typecho等相比，可就是这样还是有很多人‘摩拜’它，还有很多很多可能都没法相比，但我还是选择了你—— Ghost。</p><ul><li>使用七牛等作为默认存储<br /><a href="https://docs.ghost.org/docs/using-a-custom-storage-module">官网</a>有说明，还列举了很多第三方存储、如亚马逊、又拍云、七牛、阿里云OSS等等，这里以七牛为例说明：</li></ul><p>安装方法有两种，分别为NPM和Git，具体如下：</p><ol><li>NPM方法安装<br />创建目录：</li></ol><pre><code>mkdir content/adapters/storage
cd [Ghost博客目录]/content/adapters/storage</code></pre><p>安装Qiniu存储模块</p><pre><code>npm install ghost-qn-store</code></pre><p>将模块复制到正确的位置</p><pre><code>cp -vR node_modules/ghost-qn-store content/adapters/storage/qn-store</code></pre><ol><li>Git方法安装<br />创建目录：</li></ol><pre><code>mkdir content/adapters/storage
cd [Ghost博客目录]/content/adapters/storage</code></pre><p>Git下载</p><pre><code>git clone https://github.com/Minwe/qn-store.git</code></pre><p>安装依赖关系</p><pre><code>cd qn-store
npm install</code></pre><p>任取一种办法安装，具体的可见<a href="https://github.com/Minwe/qn-store">官网</a>，安装好之后，就可以编辑Ghost目录下的<code> config.production.json </code>,并将如下代码删除（操作之前，建议先备份一份：</p><pre><code>  &quot;process&quot;: &quot;local&quot;,
  &quot;paths&quot;: {
    &quot;contentPath&quot;: &quot;/var/www/ghost/content&quot;
  }</code></pre><p>并插入以下代码：</p><pre><code>&quot;storage&quot;: {
   &quot;active&quot;: &quot;qn-store&quot;,
   &quot;qn-store&quot;: {
     &quot;accessKey&quot;: &quot;12345678&quot;,
     &quot;secretKey&quot;: &quot;12345678&quot;,
     &quot;bucket&quot;: &quot;bucketname&quot;,
     &quot;origin&quot;: &quot;https://cdn.qnsl.cn&quot;,
     &quot;fileKey&quot;: {
       &quot;safeString&quot;: true,
       &quot;prefix&quot;: &quot;YYYYMM/&quot;
     }
   }
 }</code></pre><p>记得改成自己的哈，要不然报错别找我哈。</p><ul><li>增加评论系统<br />前面说了Ghost自身不带评论系统，这东西没了，总感觉缺少点，还是先给它增加个。本来想用Disqus的，老牌的国外评论系统了，一般不太会倒吧，用的是fooleap提供的<code> disqus-php-api </code>，这个需要使用一台支持PHP的主机（还要在GFW以外的），之前在测试时也用过，说实话，挺好的，使用方便，如果有需要的，可以去<a href="https://github.com/fooleap/disqus-php-api">Github</a>上看看，大神更新很快的。后来在Deserts家看到还一款评论系统也很出色—— Valine评论，先看一下它的特点：</li></ul><p>Valine 的特点：</p><ol><li>无后端实现</li><li>高速，使用国内后端云服务提供商 LeanCloud 提供的存储服务</li><li>开源，自定义程度高</li><li>支持邮件通知</li><li>支持验证码</li><li>支持 Markdown<br />没办法，我又再一次倒戈了，并且Deserts还对其进行了优化适配（原开发者是基于Hexo的），且增加了后台、Akismet 的垃圾评论等等，参照了<a href="https://panjunwen.com/diy-a-comment-system/">Deserts的教程</a>，赶紧给自己换了，博客目前用的就是这款。</li></ol><p>Ghost1.X还有很多功能等着我去发觉（对于我自己来讲吧），就比如：标签、归档等，还需要抽空去折腾折腾。</p>