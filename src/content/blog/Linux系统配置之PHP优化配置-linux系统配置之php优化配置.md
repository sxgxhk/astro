---
title: Linux系统配置之PHP优化配置
date: 2014-03-06 07:17:28.0
updated: 2021-12-22 17:01:20.0
url: /archives/linux系统配置之php优化配置
categories: 
- 网站建设
tags: 
---

<div>尝试使用针对CPU型号的特殊编译参数 -msse -mmmx -mfpmath=sse
在编译的时候添加 -03参数
编译的时候调节CPU的参数 -march -mcpu Use Caution
尽量只编译你需要的模块，避免无用的扩展加载
对于很少使用的扩展模块，应该编译成共享模式，便于在运行的时候动态加载
也许有些时候 --disable-all 会是你的好朋友
把PHP静态编译到Apache可以提速20％</div>
# PHP
./configure --with-apache=/path/to/apache_source
<strong>优化你的PHP配置文件</strong>
确认你的 register_globals 配置为disabled
禁用 magic_quotes_* 选项
关闭 expose_php
关闭 register_argc_argv
除非绝对需要不要启用 always_populate_raw_post_data
保证主机内存下有足够的php线程数这样可以加快页面打开速度并有效防止502错误的发生。
<strong>提高缓存执行</strong>
使用PHP代码缓存机制
Turck MMCache 停止开发
APC 较慢，优化不够
Zend Cache 优化性能好，但付费
ionCube PHP Accelerator 免费但不开源
如果可以使用Zlib压缩
<strong>减少输出数据</strong>
用CSS替换HTML
压缩HTML页面