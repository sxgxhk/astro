---
title: 永久解决“红米IMEI无效”的方法（亲测有效）
date: 2014-03-27 00:12:10.0
updated: 2021-12-22 17:01:20.0
url: /archives/永久解决红米imei无效的方法-亲测有效
categories: 
- 智能终端
tags: 
- 刷机
- 红米
- 驱动
---

由于之前对手机进行了分区，后来又不满意，又重新分了一下，结果就出大问题了（中间也曾变板砖过，后来线刷弄好了），系统是倒腾好了，可是一开机就提示“IMEI无效”，打电话也可以，就是显示不了“中国移动”，后来用Root的方法，用RE替换了文件后，“中国移动”也显示出来了，IMEI也正常了，貌似一切都太平的时候，系统又提示更新了，看着有点烦就点了更新，由于之前Root过了，也用移动叔叔刷入了第三方Recovery，现在就卡在这了（用官方的Recovery也更新不了），想想这么麻烦也就不更新了，结果实在烦了（三不三的提示系统更新），就在这第三方Recovery里双Wipe刷了最新的刷机包，刷机过程一切顺利，进入系统后麻烦又来了，又提示“IMEI无效”，这才想起原来是Root后更换文件解决的，这系统一装，那文件不就也跟着没了……（后悔呀……）。在网上找了很多关于永久解决IMEI无效的帖子，都不太靠谱（可能不同机子有点不同吧）。下面来介绍一下我的解决方法吧，先准备好官方固件的线刷包，这里提供一个红米5.0的线刷固件（下载地址：<a href="http://pan.baidu.com/s/1o6nZQRo">http://pan.baidu.com/s/1o6nZQRo</a>），还有驱动（下载地址：<a href="http://pan.baidu.com/s/1o6z5iOE" target="_blank">http://pan.baidu.com/s/1o6z5iOE</a>），写入IMEI的工具（下载地址：<a href="http://pan.baidu.com/s/1jGunAUq" target="_blank">http://pan.baidu.com/s/1jGunAUq</a>），工具的使用看图（这图是转的，我是按这个来的，有注意的地方我会说明的）。
<a href="http://uu126.cn/wp-content/uploads/2014/03/01.jpg"><img class="alignnone wp-image-537 size-full" src="http://uu126.cn/wp-content/uploads/2014/03/01.jpg" alt="01" width="687" height="686" /></a><a href="http://uu126.cn/wp-content/uploads/2014/03/02.jpg"><img class="alignnone wp-image-538 size-full" src="http://uu126.cn/wp-content/uploads/2014/03/02.jpg" alt="02" width="687" height="697" /></a>
<span style="color: #ff0000;">关键步骤，这个时候关掉手机再用数据线和电脑相连，电脑会提示找到新硬件，用刚才准备的驱动，按电脑提示找到合适的驱动即可（网上有很多帖子都是说要拿掉电池的，本人实际测试过，拿掉电池后接下来的步骤一直下不去，换过电脑也换过系统都不行，但装上电池（关机的情况下），是可以出现下图中变绿的提示）</span>
<a href="http://uu126.cn/wp-content/uploads/2014/03/03.jpg"><img class="alignnone wp-image-539 size-full" src="http://uu126.cn/wp-content/uploads/2014/03/03.jpg" alt="03" width="721" height="694" /></a>
经过两次绿色后，断开与电脑连接，手机开机，进入系统后就可以看到“中国移动”字样了，因为用的刷机包是5.0的（最新的13.0刷机包没试成功），直接在“关于手机”中系统更新到13.0，经过重启安装再到系统，依旧是显示“中国移动”，再也不会提示“无效的IMEI”了，终于彻底解决了这个问题，也不用再担心刷机了^-^
以上的办法是在红米移动版中测试通过，其它版本手头上没有，所以并不一定都适用，最后一句：<span style="color: #ff0000;">刷机有风险，需慎重！</span>