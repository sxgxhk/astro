---
title: 安装系统时使用DiskGenius分区软件造成的两种常见故障
date: 2015-11-18 02:15:38.0
updated: 2021-12-22 17:01:20.0
url: /archives/安装系统时使用diskgenius分区软件造成的两种常见故障
categories: 
- IT综合技术
tags: 
---

<strong>【故障1】</strong>
<strong>现象：用DiskGenius分区、Ghost系统，重启后硬盘不引导，左上角一个出现一个j。</strong>
<strong>原因：</strong>新版的DiskGenius软件在进行一键分区时，默认勾选了4K对齐选项，而有些老主板和老硬盘是不支持4K对齐的，如果分区时勾选了4K对齐选项，就会出现此种现象。
<strong>解决方法：</strong>一键分区时去掉4K对齐选项前面的对号，即去掉图中“对齐分区到此扇区数的整数倍”前面的对号。
<a href="http://uu126.cn/wp-content/uploads/2015/11/20150920214856_26200.jpg"><img class="aligncenter size-full wp-image-1883" src="http://uu126.cn/wp-content/uploads/2015/11/20150920214856_26200.jpg" alt="20150920214856_26200" width="750" height="507" /></a>
<strong>【故</strong><strong>障2】</strong>
<strong>现象：在winpe中用DiskGenius一键分区、Ghost系统，重启后分区丢失，硬盘变成没有分区状态。</strong>
<strong>原因及解决方案</strong><strong>：</strong>新版DiskGenius中改变了分区格式化的执行过程，老版DiskGenius中，只要格式化的进度条走完，分区就定型了，此时关闭DiskGenius软件不会造成分区丢失；新版DiskGenius中，格式化的进度条走完，却没有完分区操作，此时关闭DiskGenius软件，就会造成分区丢失，要等到DiskGenius软件逐个分区确认操作之后，才可以关闭软件。
如下图，会从第一个分区开始，逐个分区变蓝，最后恢复到没有分区变蓝的状态，才可以关闭软件。
<a href="http://uu126.cn/wp-content/uploads/2015/11/20150920215557_34835.jpg"><img class="aligncenter size-full wp-image-1884" src="http://uu126.cn/wp-content/uploads/2015/11/20150920215557_34835.jpg" alt="20150920215557_34835" width="750" height="508" /></a> <a href="http://uu126.cn/wp-content/uploads/2015/11/20150920215559_89204.jpg"><img class="aligncenter size-full wp-image-1885" src="http://uu126.cn/wp-content/uploads/2015/11/20150920215559_89204.jpg" alt="20150920215559_89204" width="750" height="509" /></a> <a href="http://uu126.cn/wp-content/uploads/2015/11/20150920215600_50269.jpg"><img class="aligncenter size-full wp-image-1886" src="http://uu126.cn/wp-content/uploads/2015/11/20150920215600_50269.jpg" alt="20150920215600_50269" width="750" height="510" /></a>