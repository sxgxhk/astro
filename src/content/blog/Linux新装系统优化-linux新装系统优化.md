---
title: Linux新装系统优化
date: 2014-03-06 07:15:20.0
updated: 2021-12-22 17:01:20.0
url: /archives/linux新装系统优化
categories: 
- 网站建设
tags: 
---

<div><strong>1 系统安装好后，通过命令ntsysv关闭不需要的服务，建议只留下如下服务即可</strong></div>
<div>network：提供网络服务</div>
<div>syslog: 提供日志服务</div>
<div>crond: 计划任务</div>
<div>irqbalance:启用irqbalance服务，即可以提升性能，又可以降低性能耗，irqbalance用于优化中断分配，它会自动收集系统数据以及分许使用模式，并依据系统负载状况将工作置于performance mode或power-save mode状态，处于performance mode时irqbanlance会将中断尽可能均匀地分发给cpu core,以充分利用cpu的多核，提升性能，irqbalance会将中断集中分配给第一个cpu，以保证其他空闲cpu的睡眠时间，降低能耗。建议保留</div>
<div>sshd:远程连接</div>
<div>3.I/0优化，对于一台Nginx 1分钟高并发5000ip来说。建议磁盘最好用SAS 高转速硬盘，合理考虑好磁盘的空间，进行一个合适的分配，可以考虑磁盘用LVM来规划，放webroot的分区刚刚够多几个G就够，这样能更大的发挥磁盘的读写能力，节省了磁盘分区块的扫描时间，如果webroot只读取很少写入操作，建议关闭I/0写入操作，一个文件分为 atime:访问时间，ctime 文件inode发生改变的时间，mtime文件的修改时间，如果有多个小文件（比如web服务器的页面上有多个小图片），通常就没有必要记录文件的访问时间了，这样可以减少磁盘的I/O 具体实现如下：</div>
<div></div>
<div>首先，修改文件系统的配置文件 vim /etc/fstab 然后，在包含大量小文件的分区中使用noatime和nodiratime这2个命令。例如:</div>
<div></div>
<div>/dev/sda5  <wbr />/data/pics ext3 noatime,nodiratime 0 0 这样文件被访问时就不会再产生些磁盘的I/O了。</div>
<div></div>
<div></div>
<div><strong>2.关闭不必要的服务，这样可以节省cpu和内存的的使用率。通过ntsysv可以方便查看 server status 下面列出建议开启的服务，</strong></div>
<div></div>
<div>其余的可以一律关闭：</div>
<div></div>
<div>crond linux下的时间计划任务服务。</div>
<div>irqbalance</div>
<div>启用irqbalance服务，既可以提升性能，又可以降低能耗。irqbalance用于优化中断分配，它会自动收集系统数据以分析使用模式，并依据系统负载状况将工作置于Performance mode或Power-save mode状态。处于Performance mode时，irqbalance会将中断尽可能均匀地分发给各个CPU core，以充分利用CPU的多核，提升性能。处于Power-save mode时，irqbalance会将中断集中分配给第一个CPU，以保证其他空闲CPU的睡眠时间，降低能耗。现在的主流服务器都是双四核，所以这项我建议保留。</div>
<div>network：网络 ipaddress等</div>
<div>sshd：远程连接</div>
<div>syslog: linux下日志服务，主要查看一些日志。</div>
<div></div>
<div><strong>3.关闭不需要的tty</strong></div>
<div></div>
<div>先编辑/etc/inittab，找到如下一段命令：</div>
<div>1:2345:respawn:/sbin/mingetty tty1</div>
<div>2:2345:respawn:/sbin/mingetty tty2</div>
<div>3:2345:respawn:/sbin/mingetty tty3</div>
<div>4:2345:respawn:/sbin/mingetty tty4</div>
<div>5:2345:respawn:/sbin/mingetty tty5</div>
<div>6:2345:respawn:/sbin/mingetty tty6</div>
<div>这段命令会使init为你打开了6个控制台，分别可以用［ALT+F1］到［ALT+F6］进行访问。此6个控制台默认都驻留在内存中，用ps -aux这个命令就可以看到，这是6个进程，如下所示： <wbr /></div>
<div>［root@localhost ～］# ps -aux| grep tty</div>
<div>Warning: bad syntax, perhaps a bogus '-'? See /usr/share/doc/procps-3.2.7/FAQ</div>
<div>root　　　3219　0.0　0.0　 3792　 488 tty1　　 Ss+　Mar16　 0:00 /sbin/mingetty tty1</div>
<div>root　　　3220　0.0　0.0　 3792　 484 tty2　　 Ss+　Mar16　 0:00 /sbin/mingetty tty2</div>
<div>root　　　3221　0.0　0.0　 3792　 488 tty3　　 Ss+　Mar16　 0:00 /sbin/mingetty tty3</div>
<div>root　　　3222　0.0　0.0　 3792　 488 tty4　　 Ss+　Mar16　 0:00 /sbin/mingetty tty4</div>
<div>root　　　3224　0.0　0.0　 3792　 488 tty5　　 Ss+　Mar16　 0:00 /sbin/mingetty tty5</div>
<div>root　　　3226　0.0　0.0　 3792　 488 tty6　　 Ss+　Mar16　 0:00 /sbin/mingetty tty6</div>
<div>root　　　3325　0.0　0.1　90548　6264 tty7　　 Ss+　Mar16　 0:01 /usr/bin/Xorg :0 -br -audit 0 -auth /var/gdm/:0.Xauth -nolisten tcp vt7</div>
<div>root　　　6767　0.0　0.0　68284　1564 tty8　　 Ss+　Mar17　 0:00 /bin/bash</div>
<div>root　　 31179　0.0　0.0　63372　 756 pts/2　　S+　 17:03　 0:00 grep tty</div>
<div></div>
<div>事实上没有必要使用这么多。应如何关闭不需要的进程呢？通常我们保留前两个控制台就可以了，把后面4个用#注释掉，并且无需重启，只需要执行init q这个命令即可，如下所示：</div>
<div>init q</div>
<div></div>
<div><strong>4.对TCP/IP网络参数进行调整</strong></div>
<div>调整TCP/IP网络参数，可以增强抗SYN Flood的能力，命令如下所示：</div>
<div># echo 'net.ipv4.tcp_syncookies = 1' &gt;&gt; /etc/sysctl.conf</div>
<div># sysctl -p</div>
<div></div>
<div>.修改shell命令的history记录个数</div>
<div></div>
<div>修改history记录的命令如下所示：</div>
<div># vi /etc/profile</div>
<div></div>
<div>找到histsize=1000，将其改为histsize=100(这条可根据实际情况而定)。</div>
<div></div>
<div>不重启系统就可让其生效，如下所示：</div>
<div>source /etc/profile</div>
<div></div>
<div><strong>5.如果用不到ipv6尽量关闭ipv6的支持。以最大限度的保证安全和快速。</strong></div>
<div></div>
<div><strong>6.调整Linux的最大文件打开数。</strong></div>
<div>刚开始我采用vim/etc/security/limit.conf命令，在最后一行添加如下代码：</div>
<div>* soft nofile 60000</div>
<div>* hard nofile 65535</div>
<div></div>
<div>但重启后一切都还原了。</div>
<div>正解做法应该为在Centos5.5的/etc/rc.local文件里添加如下命令行：</div>
<div>ulimit -SHn 65535</div>
<div></div>
<div>当然了，我们也可以在Nginx的一些监控脚本里实时添加此命令行，达到重启也能生效的目的。</div>
<div></div>
<div>另外，ulimit -n命令并不能真正看到文件的最大文件打开数，大家可用如下脚本查看：</div>
<div>#!/bin/bash</div>
<div>for pid in 'ps aux |grep nginx |grep -v grep|awk '{print$2}''</div>
<div>do</div>
<div>cat /proc/${pid}/limits |grep 'Max open files'</div>
<div>done
<strong>7，如何关闭ipv6?</strong></div>
<div>
   ipv6目前我们还不需要，但系统安装完成后它会作为模块常驻核心，没有必要，
可以用这个步骤来关闭它:
首先编辑网络配置文件：
vi /etc/sysconfig/network
修改
NETWORKING_IPV6=yes
为
NETWORKING_IPV6=no
然后关闭其模块：vi /etc/modprobe.conf
在文件中添加以下两行
alias net-pf-10 off
alias ipv6 off
修改完成后需重启机器使之生效
<strong>8,如何关闭atime?</strong>
一个linux文件默认有3个时间：
atime:对此文件的访问时间
ctime:此文件inode发生变化的时间
mtime:此文件的修改时间
如果有多个小文件时通常没有必要记录文件的访问时间，
这样可以减少磁盘的io,比如web服务器的页面上有多个小图片
如何进行设置呢？
修改文件系统的配置文件：vi /etc/fstab
在包含大量小文件的分区中使用noatime,nodiratime两项
例如：
/dev/md5                /data/pics1           ext3    noatime,nodiratime 0 0
这样文件被访问时就不会再产生写磁盘的io
<strong>9,一定要让你的服务器运行在level 3上</strong>
做法：
vi /etc/inittab
id:3:initdefault:
让服务器运行X是没有必要的
6,优化sshd
X11Forwarding no        //不进行x图形的转发
UseDNS no               //不对IP地址做反向的解析
<strong>10，优化shell</strong>
修改命令history记录
# vi /etc/profile
找到 HISTSIZE=1000 改为 HISTSIZE=100
然后 source /etc/profile
</div>