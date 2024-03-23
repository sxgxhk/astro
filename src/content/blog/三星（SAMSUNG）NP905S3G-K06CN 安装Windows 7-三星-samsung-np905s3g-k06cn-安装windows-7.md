---
title: 三星（SAMSUNG）NP905S3G-K06CN 安装Windows 7
date: 2015-12-20 23:41:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/三星-samsung-np905s3g-k06cn-安装windows-7
categories: 
- IT综合技术
tags: 
- 维修
---

<p>朋友来电说自己买的三星笔记本想换个系统，原来是Win8的用不习惯想装Win7，结果弄来弄去也装不上去，就送到我这求解决了。到手一看，原来是三星NP905S3G-K06CN，还是个超薄的本本，由于自带Win8的缘故，BIOS都是快速引导的，那么先修改一下引导吧，具体的操作如下：</p><ul><li>进入BIOS：开机过程中不断地按F2，就进入了BIOS；</li></ul><ul><li>通过方向键和Enter，选择 Boot，把 Secure Boot 和 Fast BIOS Mode 都设置为 Off 状态，这两项如果不关掉的话，无法U盘引导的；<br /><img src="https://cdn.uu126.cn/wp-content/uploads/2015/12/20151220143842.jpg" alt="请输入图片描述" title="请输入图片描述"></li><li>按下F10（保存并退出）BIOS</li><li>重启过程再按下F2进入BIOS</li><li>再次找到 Boot，选择从 U盘启动</li><li>按下F10（保存并退出）BIOS，之后就进入了 U盘启动界面了### 注意哦，一定要把U盘插到 USB2.0口上<br />U盘可以引导之后，余下的功夫就很简单了，将硬盘由原来的GPT方式改成MBR方式，另外分区时记得4K对齐哈，装系统就不多说了。需要注意的是，三星这款本本在官网找不到驱动的（至少我没找到），驱动都是由驱动精灵完成的，后来因为快捷键不能用（亮度不能调，受不了吧），又百度又官网的，发现原来三星之所以找不到驱动，是因为它也有一个类似于联想驱动管理一样的程序：SW UPdate，这个下载安装后，可以安装或升级驱动的，下载地址：<a href="http://downloadcenter.samsung.com/content/SW/201404/20140411143248145/SWUpdate_2.1.25.4.ZIP">点击下载</a>，安装后再安装FN驱动（Easy Settings/Easy Display Manager）就可以了调节亮度了，也有快捷键显示的。</li></ul><p>好了，这超薄本也算是都弄好了，交差结稿。</p>