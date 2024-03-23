---
title: Wordpress使用cloudfs4oss挂载OSS
date: 2015-12-22 22:36:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/wordpress使用cloudfs4oss挂载oss
categories: 
- 网站建设
tags: 
- Wordpress
- 阿里云
---

<p>本站一直用的阿里云的ECS，图片也都是存在云磁盘上，依托在七牛免费资源上，感觉速度不是很理想，可能是没有优化好的缘故吧，最近对阿里云的OSS感兴趣了（一直都想用，只不过在价格和使用上有点……），前几天用了OSS插件，用着也挺好，可能是因为我是个非插件控吧，总想找个办法可以不用插件，所以就找到了cloudfs4oss，这是款可以将OSS直接挂载到ECS上，就像一个目录一样方便访问，那就动手吧：</p><p>1、安装配置环境：</p><pre><code>yum install libcurl libcurl-devel openssl-devel fuse fuse-libs fuse-devel libxml2-develoss-cn-qingdao-internal.aliyuncs.com</code></pre><p>2、下载cloudfs4oss文件并解压（这个可以在阿里云的云市场里购买（免费的）后也会有链接下载的），解压后再进太cloudfs4oss目录：</p><pre><code>wget http://blog.cloudtalkers.com/wp-content/uploads/CloudFS_Centos64_0273.tar.gz
tar -zxf CloudFS_Centos64_0273.tar.gz
yum install libunwind-devel
cd CloudFS_Centos64</code></pre><p>3、安装cloudfs4oss，这里有默认安装和自定义安装</p><ul><li>默认安装是指cloudfs的安装目录是<code> /usr/local/cloudfs </code>，oss的挂载目录是<code>  /mnt/oss </code>，操作如下：<br /><code> ./CloudFS_Install.sh </code></li><li>自定义安装（个人建议这个，方便），可以直接挂载到<code> /home/wwwroot/ </code>网站目录<code> /wp-content/uploads </code>，操作如下：</li></ul><pre><code>./CloudFS_Install.sh INSTALL_DIR=/usr/local/cloudfs MOUNT_POINT=/home/wwwroot/网站目录/wp-content/uploads</code></pre><h3>这里需要注意的是：网站目录/wp-content/uploads中的uploads目录必须为空，否则会出错！</h3><p>4、挂载后再配置cloudfs.conf文件，一般在<code> /usr/local/cloudfs/conf </code>下，具体需要配置如下：<br /><img src="https://cdn.uu126.cn/wp-content/uploads/2015/12/cloud4fss.png" alt="请输入图片描述" title="请输入图片描述"></p><p>根据自己的OSS情况进行配置即可。<br />5、运行cloudfs4oss，输入：<code> service cloudfs start </code><br />然后可以在Wordpress的多媒体里添加文件，再在OSS里看一下有没有刚添加的文件，如果有的话说明就成功了。</p><p>为了这玩意，折腾了蛮长时间，总算是功德圆满了。</p>