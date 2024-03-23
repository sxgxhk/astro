---
title: 另类的只能上QQ不能打开网页上网的故障解决方法(非传统的DNS解析出错)
date: 2015-04-23 05:06:14.0
updated: 2021-12-22 17:01:20.0
url: /archives/另类的只能上qq不能打开网页上网的故障解决方法
categories: 
- IT综合技术
tags: 
- 维修
---

有点空逛了逛2345，发现论坛的有一则技术贴蛮不错，或许今后可能自己也会碰上，先转载了它，以下内容转载自2345论坛：
<strong>今天接到一客户电话说</strong><strong>电脑</strong><strong>现在只能登QQ不能打开网页进行上网，昨天晚上还用的好好的，我的第一反应就是大家都知道的只能上QQ不能打开网页的故障原因是因为dns解析错误造成的，于是让客户加我的QQ，用QQ的远程协助功能来帮他处理解决。
客户的上网环境是直接连在宽带猫上进行拨号上网的，没有用路路器等设备！
按照预想的故障环境思路去操作了，首先打开本地连接的属性查看了一下，IP地址和DNS地址都是自动获取，于是把DNS改成手动指定：114.114.114.114    8.8.8.8 如下图：
</strong><strong><a href="http://uu126.cn/wp-content/uploads/2015/04/20150418162042_68445.jpg"><img class="aligncenter size-full wp-image-1730" src="http://uu126.cn/wp-content/uploads/2015/04/20150418162042_68445.jpg" alt="20150418162042_68445" width="750" height="531" /></a>
</strong><strong>然后确定，然后在开始菜单运行中打了一个清理dns缓存的命令：</strong>
<strong>ipconfig /flushdns</strong>
<strong>清理了一下缓存，接着打开浏览器点网页试了一下还是不能上网，出错提示如下图：</strong>
<a href="http://uu126.cn/wp-content/uploads/2015/04/20150418162326_17360.jpg"><img class="aligncenter size-full wp-image-1733" src="http://uu126.cn/wp-content/uploads/2015/04/20150418162326_17360.jpg" alt="20150418162326_17360" width="750" height="421" /></a>
<strong>提示代理服务器无响应。怪了客户说没设置什么代理服务器，于是就检查IE浏览器的有关代理服务器的相关设置：</strong>
<a href="http://uu126.cn/wp-content/uploads/2015/04/20150418162715_15886.jpg"><img class="aligncenter size-full wp-image-1734" src="http://uu126.cn/wp-content/uploads/2015/04/20150418162715_15886.jpg" alt="20150418162715_15886" width="750" height="421" /></a>
<strong>大家可以看到，代理服务器的相关参数设置没有任何问题，那就奇了怪了，没有设代理服务器却提示代理服务器没有响应，至此，明白一件事，此客户的能上QQ不能打开网页不是传统DNS解析出错造成的！</strong>
<strong>可是代理服务器的相关投置检查过了没有问题呀，怎么上网还是提示出错呢？！限入思索中，于是上baidu搜了一下相关的问题，没有找到什么有价值的答案，都是说进上图上提到的相关窗口进行代理服务器的相关设置就行了！</strong>
<strong>由于这里的代理服务器设置参数没有问题，所以没有办法就用了QQ管家工具箱里的“网络修复”功能进行修复了一下，不过还是不行，依旧提示代理服务器出错。</strong>
<a href="http://uu126.cn/wp-content/uploads/2015/04/20150418162040_54659.jpg"><img class="aligncenter size-full wp-image-1729" src="http://uu126.cn/wp-content/uploads/2015/04/20150418162040_54659.jpg" alt="20150418162040_54659" width="750" height="504" /></a>
<strong>没有办法了，该查的该用的都用上了！又陷入了思索中，停在那里，又看了看出错页面发现了一个突破缺口就是上面提示的代理服务器的IP地址：127.0.0.1:8877</strong>
<strong>可是上面相关的代理服务器IP也址一栏中明明是空着的呀，不管了先用它来找突破口，微软的操作系统有一个特点，系统的任何参数设置都是存放于注册表中的，于是在运行中输入：</strong>
<strong>regedit　命令　如下图：</strong>
<a href="http://uu126.cn/wp-content/uploads/2015/04/20150418161945_77728.png"><img class="aligncenter size-full wp-image-1726" src="http://uu126.cn/wp-content/uploads/2015/04/20150418161945_77728.png" alt="20150418161945_77728" width="427" height="261" /></a>
<strong>进入注册编缉器后，用查找功能查找“127.0.0.1:8877”　找到相关键值，见下图：<a href="http://uu126.cn/wp-content/uploads/2015/04/20150418161946_23445.jpg"><img class="aligncenter size-full wp-image-1727" src="http://uu126.cn/wp-content/uploads/2015/04/20150418161946_23445.jpg" alt="20150418161946_23445" width="750" height="487" /></a></strong>
<strong>果然注册表中有相关选项，见下图：<a href="http://uu126.cn/wp-content/uploads/2015/04/20150418161946_62672.jpg"><img class="aligncenter size-full wp-image-1728" src="http://uu126.cn/wp-content/uploads/2015/04/20150418161946_62672.jpg" alt="20150418161946_62672" width="750" height="487" /></a></strong>
<strong>将图中箭头所旨的键值删除或者将键值清空就行了！</strong>
<strong>"ProxyServer"的值清空</strong><strong>不过还要将这几个键值也要设置一下，见下图：</strong>
<a href="http://uu126.cn/wp-content/uploads/2015/04/20150418162044_83413.jpg"><img class="aligncenter size-full wp-image-1731" src="http://uu126.cn/wp-content/uploads/2015/04/20150418162044_83413.jpg" alt="20150418162044_83413" width="750" height="492" /></a>
<strong>"ProxyEnable"键值原来为1将它改成0</strong>
<strong>"ProxyHttp1.1"键值原来也为1也改成0</strong>
<strong>上面的“autoconfigproxy”键值最好也清空！</strong>
<strong>上面的操作全部完成后，打开浏览器测试了一下，熟悉的主页画面又出现在我们的眼前：</strong>
<a href="http://uu126.cn/wp-content/uploads/2015/04/20150418162046_27850.jpg"><img class="aligncenter size-full wp-image-1732" src="http://uu126.cn/wp-content/uploads/2015/04/20150418162046_27850.jpg" alt="20150418162046_27850" width="750" height="421" /></a>
<strong>总结：</strong>
<strong>今天碰到的这个情况和我们平时正常碰到的不太一样，不能用平常的思路去解决问题，要善于从出错提示中寻找突破口，当然这里面也需要一定的系统底层相关的知识做支撑！今天把碰到的这个另类的能上QQ不能打开网页的故障分享给大家，让大家以后再碰到此类问题时可以少走弯路！！！同时也可以让客户对我们的水平刮目相看，此类问题可以用重装系统来解决，不过在不重装系统的前提前将问题解决才叫真本事有水平，要是万一碰到是财务用的电脑，系统不能重装的情况下，我们的优势就体现出来了！</strong>