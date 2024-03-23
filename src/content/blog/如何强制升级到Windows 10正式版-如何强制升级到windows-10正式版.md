---
title: 如何强制升级到Windows 10正式版
date: 2015-09-03 01:22:34.0
updated: 2021-12-22 17:01:20.0
url: /archives/如何强制升级到windows-10正式版
categories: 
- IT综合技术
tags: 
- Win10
---

<a href="http://uu126.cn/wp-content/uploads/2015/09/c1.jpg"><img class="aligncenter wp-image-1825" src="http://uu126.cn/wp-content/uploads/2015/09/c1.jpg" alt="c1" width="700" height="365" /></a>
<div id="aimg_933410_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
<span style="font-family: 新宋体;"><span style="font-size: medium;">不是所有的人都那么幸运，能第一时间得到Windows 10更新。很多人预订了更新，但仍会像上图那样，被通知等一段时间。
</span></span>
</div>
</div>
<span style="font-family: 新宋体;"><span style="font-size: medium;">微软说过，Windows 10的升级是分批次进行的，这就意味不一定能第一时间升级Windows 10。</span></span>
<span style="font-family: 新宋体;"><span style="font-size: medium;">
<strong>解决方案:</strong>
</span></span>
<strong><span style="font-family: 新宋体;"><span style="font-size: medium;">准备工作：备份好您的重要数据，确保网络畅通，为电脑提供稳定的供电，当然必不可少的是已经预约了Windows 10的升级。预约成功的用户右下角通知区域会有下图的图标。</span></span></strong>
<strong> <a href="http://uu126.cn/wp-content/uploads/2015/09/c2.jpg"><img class="aligncenter size-full wp-image-1826" src="http://uu126.cn/wp-content/uploads/2015/09/c2.jpg" alt="c2" width="195" height="85" /></a></strong>
<div id="aimg_933411_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
<strong>升级步骤：
</strong>Step1：关闭Windows Updte服务，Win+R（Win为空格键左侧第二个按键）输入services.msc回车，打开服务；
</div>
</div>
<a href="http://uu126.cn/wp-content/uploads/2015/09/c3.jpg"><img class="aligncenter size-full wp-image-1827" src="http://uu126.cn/wp-content/uploads/2015/09/c3.jpg" alt="c3" width="399" height="230" /></a>
<div id="aimg_933414_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
<a href="http://uu126.cn/wp-content/uploads/2015/09/c4.jpg"><img class="aligncenter wp-image-1828" src="http://uu126.cn/wp-content/uploads/2015/09/c4.jpg" alt="c4" width="700" height="373" /></a>
</div>
</div>
<div id="aimg_933416_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
Step2：找到“Windows Update”服务右键选择“属性”，查看当前服务状态，若为“正在运行”，点击“停止”，然后确认服务状态为“已停止”；
</div>
</div>
<a href="http://uu126.cn/wp-content/uploads/2015/09/c5.jpg"><img class="aligncenter wp-image-1829" src="http://uu126.cn/wp-content/uploads/2015/09/c5.jpg" alt="c5" width="450" height="558" /></a>
<div id="aimg_933417_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
<a href="http://uu126.cn/wp-content/uploads/2015/09/c6.jpg"><img class="aligncenter size-full wp-image-1830" src="http://uu126.cn/wp-content/uploads/2015/09/c6.jpg" alt="c6" width="472" height="598" /></a>
</div>
</div>
<div id="aimg_933421_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
<a href="http://uu126.cn/wp-content/uploads/2015/09/c7.jpg"><img class="aligncenter size-full wp-image-1831" src="http://uu126.cn/wp-content/uploads/2015/09/c7.jpg" alt="c7" width="472" height="598" /></a>
</div>
</div>
<div id="aimg_933422_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
Step3：打开“X:WindowsSoftwareDistributionDownload”文件夹，（其中X表示系统盘盘符，一般是C盘）删除其中所有文件；
</div>
</div>
<a href="http://uu126.cn/wp-content/uploads/2015/09/c8.jpg"><img class="aligncenter size-full wp-image-1832" src="http://uu126.cn/wp-content/uploads/2015/09/c8.jpg" alt="c8" width="550" height="282" /></a>
<div id="aimg_933423_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
Step4：点击Step2中最后一张图中的启动，确定服务状态为“正在运行”；
</div>
</div>
<a href="http://uu126.cn/wp-content/uploads/2015/09/c9.jpg"><img class="aligncenter size-full wp-image-1833" src="http://uu126.cn/wp-content/uploads/2015/09/c9.jpg" alt="c9" width="472" height="598" /></a>
<div id="aimg_933425_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
<span style="font-family: verdana, 宋体, Arial, Helvetica, sans-serif;">Step5：</span><span style="font-family: verdana, 宋体, Arial, Helvetica, sans-serif;">Win7 SP1：点开开始菜单搜索“cmd”然后选择右键“以管理员身份运行”打开“命令提示符”</span>
</div>
</div>
<span style="font-family: verdana, 宋体, Arial, Helvetica, sans-serif;"> <a href="http://uu126.cn/wp-content/uploads/2015/09/c10.jpg"><img class="aligncenter size-full wp-image-1834" src="http://uu126.cn/wp-content/uploads/2015/09/c10.jpg" alt="c10" width="405" height="498" /></a></span>
<div id="aimg_933426_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
<span style="font-family: verdana, 宋体, Arial, Helvetica, sans-serif;">Win8.1：Win+X选择“命令提示符（管理员）”</span>
</div>
</div>
<span style="font-family: verdana, 宋体, Arial, Helvetica, sans-serif;"> <a href="http://uu126.cn/wp-content/uploads/2015/09/c11.jpg"><img class="aligncenter size-full wp-image-1835" src="http://uu126.cn/wp-content/uploads/2015/09/c11.jpg" alt="c11" width="210" height="372" /></a></span>
<div id="aimg_933428_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
<span style="font-family: verdana, 宋体, Arial, Helvetica, sans-serif;">Step6：输入wuauclt.exe /updatenow回车；</span>
</div>
</div>
<a href="http://uu126.cn/wp-content/uploads/2015/09/c12.jpg"><img class="aligncenter size-full wp-image-1836" src="http://uu126.cn/wp-content/uploads/2015/09/c12.jpg" alt="c12" width="550" height="265" /></a>
<div id="aimg_933454_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
<span style="font-family: verdana, 宋体, Arial, Helvetica, sans-serif;">Step7：重新检查系统更新，发现已经可以下载Windows 10了。</span>
</div>
</div>
<a href="http://uu126.cn/wp-content/uploads/2015/09/c13.jpg"><img class="aligncenter wp-image-1837" src="http://uu126.cn/wp-content/uploads/2015/09/c13.jpg" alt="c13" width="700" height="347" /></a>
<div id="aimg_933456_menu" class="tip tip_4 aimg_tip">
<div class="xs0">
除了以上方案外，其实还可以更简单点，如果你的系统（Win7或Win8）是正版的话（非激活工具激活的），也可以直接下载好Win10系统（下载时请对应下载，比如原来是Win8.1专业版 64位的，那就下载Win10专业版64位），然后制作成U盘安装（具体制作方法可请教于度娘），接着直接在原系统里运行U盘里的setup.exe进么升级安装。Win10的系统安装还是很快的，本人固态硬盘下升级安装也才花了10几分钟，目前各功能都测试正常。
</div>
</div>
&nbsp;