---
title: IOS 高版本保资料降级(未关验证)
date: 2018-11-21 19:35:20.0
updated: 2021-12-22 17:01:20.0
url: /archives/ios-高版本保资料降级未关验证
categories: 
- 智能终端
tags: 
- iphone
---

<!-- wp:paragraph -->
<p>用iPhone的朋友都知道，IOS（iPhone手机的灵魂）更新还是蛮快的，不管是修补漏洞也好，还是增加新功能也罢，给我的感觉就是完胜安卓系统，至少同年代的机型，iPhone可以用的更流畅些，而且只要你肯刷，新版本的系统始终都是可以轻松得到（除非跨越太大会限制版本更新，但相比安卓新系统的普及率来讲，IOS的新牒普及率已经高出很多了）。在日常使用中还是会碰到例如：新版本不适应了，费电等原因需要降级（IOS只能降级到未关闭验证的系统版本，这点相比安卓有点打脸了，这也算是封闭式系统的特性吧），一般正常的操作，苹果家的iTunes是不允许高版本的备份恢复到低版本的系统中，估计是怕出现问题或者是有意为之等原因，好在各路大神给出了解决方案，本人也亲身体验了iPhone6S Plus由IOS12.1降级到12.0.1，同时将12.1的备份恢复到12.0.1，中间出现了点点小插曲，不过最终还是完美搞定，下面就来啰嗦一下：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>将手机连接iTunes，并备份当前iPhone 12.1资料，这里据有些大神说不设置密码会好一点，反正我是没设置（比较听话型）</li><li>备份好之后开始刷机（备份比较费时间，建议备份的途中就可以下载固件，目前能降的也只有12.0.1），手机进入DFU模式（在确保与电脑连接好、iTunes也打开的情况下，将手机关闭后再开机，屏幕上显示苹果图标时按住Home键，大概10秒左右屏幕再次黑掉，这时松开开关键、继续按住Home键，再等大概10秒，iTunes会提示处于恢复模式的iPhone（大概这个意思吧，原话忘了），这时松开手机按住键盘上的Shift键找到固件刷入</li><li>开始最关键的步骤，修改备份资料，先找到备份目录（选最新的那个），一般默认目录为：</li></ul>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>C:\Users\电脑用户名\AppData\Roaming\Apple Computer\MobileSync\Backup</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>‌‌</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201811/iosjiangji_01.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:list -->
<ul><li>打开备份文件夹.找到 Info.plist 用记事本/写字板（推荐使用plist Editor Pro）打开。先搜索<code>Build Version</code>修改为<code>16A404</code>（我的是这个，具体看你下载的固件名：<code>iPhone_5.5_12.0.1_16A404_Restore</code>版本号12.0.1后面就是<code>Build Version</code>）</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>‌‌</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201811/iosjiangji_buildversion.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>‌‌</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>接着修改<code>Product Version</code>，将其修改为：12.0.1</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>‌‌</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201811/iosjiangji_productversion.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>‌‌</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>两处修改完成之后保存一下，等iPhone进入系统就可以在iTunes中恢复了。说说我这边碰到的事，点击恢复一切正常，手机重启后卡在白屏幕界面上好长时间，我以为是挂了，就直接重启了，好在重启后一会就进入系统了，可能是我耐心不够好吧233，待手机进入系统后就是软件的恢复安装，过程还是需要点时间的，不过这些等待还是值得的，毕竟相比不能恢复备份来讲还是可以忽略不计的。目前手机使用正常，耗电相比12或12.1也没什么大的感觉，可能我原来就是一天一充吧（换过第三方大容量电池了）。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>聊点题外话</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>顺便记录一下刷ipcc（运营商文件）的过程，虽然电信在大浙江已经开始VOLTE的测试了，本人也申请开通了（我是微信关注浙江电信，找人工服务开通的，发短信指令好多回一次没成功过），但一直没地试，加上手上的6SP是12版本，目前好像刷ipcc也不能实现，但还是想更新一下。12.0.1的带的是<code>中国电信33.0</code>，在论坛上已经有34.1了，本着试验精神果断的刷上了（昨晚刷的，体验了一天也没啥感觉233），顺附上网上移来的教程，昨晚刷的过程中也遇到了，就当给自己记录一下吧：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>第一步： 安装iTunes，最好是最新版。<br>苹果官网的链接：&nbsp;<a href="http://www.apple.com/cn/itunes/download/">http://www.apple.com/cn/itunes/download/</a><br>如果你32位win系统，就装32位iTunes；64位win系统装64位iTunes；Mac系统自己带了iTunes。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>第二步：需要允许你的iTunes可以加载ipcc文件。<br>本操作在当前电脑只需执行一次就够了，之后一直有效。重新安装或升级iTunes可能需要再来一遍。<br>下面的命令执行完毕后，不会有任何提示。反而出错的话会有提示，一般是iTunes路径不对。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>windows32位的用户：首先请打开命令提示符。然后完整复制下方代码（含引号），回车执行。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>"%ProgramFiles%\iTunes\iTunes.exe" /setPrefInt carrier-testing 1
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果提示错误，请换下面一种代码执行。之前iTunes安装到非C盘的话，自己改盘符。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>"C:\Program Files\iTunes\iTunes.exe" /setPrefInt carrier-testing 1
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>windows 64位的用户：<br>首先请打开命令提示符。然后完整复制下方代码（含引号），回车执行。如果之前iTunes安装到非C盘的话，自己改盘符</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>"C:\Program Files\iTunes\iTunes.exe" /setPrefInt carrier-testing 1
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果提示错误，请换下面一种代码执行。如果之前iTunes安装到非C盘的话，自己改盘符。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>"C:\Program Files (x86)\iTunes\iTunes.exe" /setPrefInt carrier-testing 1
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>MacOS用户：<br>请打开<code>Terminal</code>终端。然后完整复制下方代码，回车执行。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>defaults write com.apple.itunes carrier-testing -bool true
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果不行，请换下面一种代码执行。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>defaults write com.apple.iTunes carrier-testing -bool YES
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>第三步：刷入IPCC<br>先打开itunes，连上你的iPhone或者iPad。选择好当前已经连接的设备。<br>然后按住shift键的同时，用鼠标选择“更新”。如图。（Mac用户的话，则需要按住Option键的同时，用鼠标选择“更新”）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>‌‌</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201811/iosjiangji_03.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>‌‌</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然后会出现一个对话框，可以右下角选择文件类型为ipcc，如图。(Mac系统不需要手动选文件类型为ipcc）<br>如果没有ipcc可以选择，说明刚才第2步操作有误。请重复第2步。之后选好路径和要刷的ipcc，点击确认就行了。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>‌‌</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201811/iosjiangji_04.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>‌‌</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>后面两张图片有点老了（5S的机型，不过现在也差不多的，将就着看吧），附上中国电信34.1的ipcc文件官方下载地址：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://updates.cdn-apple.com/2018/carrierbundles/041-00618-20181030-36B3100E-D989-11E8-9C49-1F9D2C4EE937/ChinaTelecom_USIM_cn_iPhone.ipcc">https://updates.cdn-apple.com/2018/carrierbundles/041-00618-20181030-36B3100E-D989-11E8-9C49-1F9D2C4EE937/ChinaTelecom_USIM_cn_iPhone.ipcc</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>没事想折腾一下的亲，可以放马去试了，我决不拦着?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>‌</p>
<!-- /wp:paragraph -->