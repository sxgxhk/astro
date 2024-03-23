---
title: Wdcp在安装memcached出现错误的解决办法
date: 2014-11-01 18:50:34.0
updated: 2021-12-22 17:01:20.0
url: /archives/wdcp在安装memcached出现错误的解决办法
categories: 
- 网站建设
tags: 
---

今天在安装memcached时出现了以下错误（tar: libevent-1.4.14b-stable.tar.gz: Cannot open: No such file or directory），错误如下：
<ol>
	<li>tar: libevent-1.4.14b-stable.tar.gz: Cannot open: No such file or directory</li>
	<li>tar: Error is not recoverable: exiting now</li>
	<li>memcached_ins.sh: line 35: cd: libevent-1.4.14b-stable: No such file or directory</li>
	<li>memcached_ins.sh: line 36: ./configure: No such file or directory</li>
	<li>make: *** No targets specified and no makefile found. Stop.</li>
</ol>
经过查看.sh脚本，发现如下代码
<ol>
	<li>cd /tmp</li>
	<li>wget -c https://github.com/downloads/libevent/libevent/libevent-1.4.14b-stable.tar.gz</li>
	<li>wget -c http://memcached.googlecode.com/files/memcached-1.4.15.tar.gz</li>
	<li>wget -c http://pecl.php.net/get/memcache-2.2.7.tgz</li>
	<li>tar xf libevent-1.4.14b-stable.tar.gz</li>
	<li>cd libevent-1.4.14b-stable</li>
	<li>./configure –prefix=/usr</li>
	<li>make</li>
	<li>[ $? != 0 ] &amp;&amp; exit</li>
	<li>make install</li>
	<li>cd ..</li>
</ol>
瞬间就明白了，因为在国内网络无法访问Google所以无法下载libevent-1.4.14b-stable.tar.gz和memcached-1.4.15.tar.gz
解决办法：
手动把
<a title="" href="https://github.com/downloads/libevent/libevent/libevent-1.4.14b-stable.tar.gz" target="_blank" data-original-title="">https://github.com/downloads/libevent/libevent/libevent-1.4.14b-stable.tar.gz</a>
<a title="" href="http://memcached.googlecode.com/files/memcached-1.4.15.tar.gz" target="_blank" data-original-title="">http://memcached.googlecode.com/files/memcached-1.4.15.tar.gz</a>
下载到本机，然后再上传到服务器/tmp目录里。
最后再运行：
<pre class="prettyprint linenums">wget -c http://down.wdlinux.cn/in/memcached_ins.sh
chmod 755 memcached_ins.sh
/memcached_ins.sh
</pre>
之后出现以下页面，就表示安装成功了
<a href="http://uu126.cn/wp-content/uploads/2014/11/wdcp1.jpg"><img class="alignnone size-full wp-image-1187" src="http://uu126.cn/wp-content/uploads/2014/11/wdcp1.jpg" alt="wdcp1" width="300" height="91" /></a>
当然WDCP里也不会显示未安装了，OK了，顺便把一些WDCP里常见的安装组件代码放一下如下：
memcache的安装
<pre class="prettyprint linenums">wget -c http://down.wdlinux.cn/in/memcached_ins.sh
chmod 755 memcached_ins.sh
./memcached_ins.sh
</pre>
服务启动或停止
<pre class="prettyprint linenums">service memcached start
</pre>
服务停止
<pre class="prettyprint linenums">service memcached stop
</pre>
服务重启
<pre class="prettyprint linenums">service memcached restart
</pre>
或在WDCP后台启动也可
mysqli的安装
<pre class="prettyprint linenums">wget -c http://down.wdlinux.cn/in/mysqli_ins.sh
chmod 755 mysqli_ins.sh
./mysqli_ins.sh
</pre>
pdo_mysql的安装
<pre class="prettyprint linenums">wget -c http://down.wdlinux.cn/in/pdo_mysql_ins.sh
chmod 755 pdo_mysql_ins.sh
./pdo_mysql_ins.sh
</pre>
mysql innodb的安装
<pre class="prettyprint linenums">wget -c http://down.wdlinux.cn/in/mysql_innodb_ins.sh
chmod 755 mysql_innodb_ins.sh
./mysql_innodb_ins.sh
</pre>
libmcrypt的安装
<pre class="prettyprint linenums">wget -c http://down.wdlinux.cn/in/libmcrypt_ins.sh
chmod 755 libmcrypt_ins.sh
./libmcrypt_ins.sh
</pre>
php zip的支持
<pre class="prettyprint linenums">wget -c http://down.wdlinux.cn/in/zip_ins.sh
chmod 755 zip_ins.sh
./zip_ins.sh
</pre>