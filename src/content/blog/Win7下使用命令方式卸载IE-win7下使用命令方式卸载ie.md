---
title: Win7下使用命令方式卸载IE
date: 2018-08-21 19:24:43.0
updated: 2021-12-22 17:01:20.0
url: /archives/win7下使用命令方式卸载ie
categories: 
- IT综合技术
tags: 
- 维修
---

<!-- wp:paragraph -->
<p>公司OA用的快普M6作为日常采购出库使用，感觉相比那些程序版的进销存软件，使用久了很占内存还卡，加上这软件版本有点老，只支持IE核心（好像推荐的是IE8.0），经常上网的亲应该都知道，IE向来不被人看好，网上能看到的所谓的加速浏览器大多数用的都是谷歌浏览器核心，这破东西竟然不支持……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最近感觉系统实在太慢太卡，于是想重装个系统看看，在所谓的“系统之家”是下载了个纯净版Win7（64位，自带IE已升到9）），下载安装一切顺利，装好一看果如描述说的——纯净，桌面上除了系统那几个熟悉的图标，啥也没有（给作者点个赞），当然IE默认首页是改过的，这点我能理解的。由于自带的是IE9，登陆公司的OA，感觉使用起来比原先的XP（IE8）感觉要快很多，不知道是不是系统刚装过的原因，反正速度上快了不少，只是有点遗憾，出库打单（用的是多联单，针式打印）出来，总有些字缺点笔画，比如“白”字中间少一横等，各种IE设置、也换过打印机驱动都无解，但是其它的像Word、Excel打印出来的都正常，无语了……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>无奈之中看到Q管家提示IE升级，一点再一重启，IE由9变11了，打开OA使用各功能感觉比9还快那么一丢丢（心里作用估计比较大），但打印出库单依旧是缺笔画，后来一忙就把这事耽搁了，等第二天打单才想起这故障还没解决，想想那就把IE卸载掉吧，可当我点开控制面板的程序，竟然没找到IE卸载项，查看已安装的更新也没有，郁闷（这Ghost封装的这么神乎），无解中找起了度娘，找到了使用命令方式卸载，试了试，果然好用，就是要一级一级的卸载，像我就是先卸载IE11，重启再次运行命令卸载IE9再重启才回到IE8，回到IE8后虽然使用上没有IE9或IE11，但打印出库单再也不会缺少笔画了，具体的卸载命令如下：</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><li>卸载IE11的命令：</li></ol>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>FORFILES /P %WINDIR%\servicing\Packages /M Microsoft-Windows-InternetExplorer-*11.*.mum /c "cmd /c echo Uninstalling package @fname &amp;&amp; start /w pkgmgr /up:@fname /norestart</code></pre>
<!-- /wp:code -->

<!-- wp:list {"ordered":true} -->
<ol><li>卸载IE10的命令：</li></ol>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>FORFILES /P %WINDIR%\servicing\Packages /M Microsoft-Windows-InternetExplorer-*10.*.mum /c "cmd /c echo Uninstalling package @fname &amp;&amp; start /w pkgmgr /up:@fname /norestart</code></pre>
<!-- /wp:code -->

<!-- wp:list {"ordered":true} -->
<ol><li>卸载IE19的命令：</li></ol>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>FORFILES /P %WINDIR%\servicing\Packages /M Microsoft-Windows-InternetExplorer-*9.*.mum /c "cmd /c echo Uninstalling package @fname &amp;&amp; start /w pkgmgr /up:@fname /norestart</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>以上命令可以直接复制粘贴到命令窗口中（根据自己卸载的版本哈），纳尼？命令窗口怎么打开？</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><li>第一种办法：点击左正解的“开始”-在搜索输入框中-输入cmd并以管理员运行命令窗口。</li></ol>
<!-- /wp:list -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/win7_ie_xz03.png" alt="win7_ie_xz03"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>2.第二种办法：按Win徽标+R键，然后打入cmd调出命令窗口</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/win7_ie_xz04.png" alt="win7_ie_xz04"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>命令粘贴完后按回车键，等其运行完后，再重启电脑（手动哈）</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/win7_ie_xz01.png" alt="win7_ie_xz01"/></figure>
<!-- /wp:image -->