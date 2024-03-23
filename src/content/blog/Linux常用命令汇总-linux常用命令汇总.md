---
title: Linux常用命令汇总
date: 2015-03-21 05:22:55.0
updated: 2021-12-22 17:01:20.0
url: /archives/linux常用命令汇总
categories: 
- 网站建设
tags: 
---

自从从WDCP迁徙到LNMPA后，输命令便免不了，经常一个命令忘了（其实自己也就是个半路出家的和尚）还要去找度娘，所以今天就把这常用命令收集一下，以后也能方便一点。
<strong>1、目录操作：</strong>
rm -rf mydir /*删除mydir目录*/
cd mydir /*进入mydir目录*/
cd – /*回上一级目录*/
cd .. /*回父目录，中间有空格*/
cd ~ /*回根目录*/
mv tools tool /*把tools目录改名为tool */
ln -s tool bac /*给tool目录创建名为bac的符号链接,最熟悉的应该就是FTP中www链接到public_html目录了*/
cp -a tool /home/vpser/www /*把tool目录下所有文件复制到www目录下 */
<strong>2、文件操作：</strong>
rm go.tar /* 删除go.tar文件 */
find mt.cgi /* 查找文件名为mt.cgi的文件 */
df –h /* 查看磁盘剩余空间,好像没这个必要，除非你太那个了 */
<strong>3、解压缩：</strong>
tar xvf wordpress.tar /* 解压tar格式的文件 */
tar -tvf myfile.tar /* 查看tar文件中包含的文件 */
tar cf toole.tar tool /* 把tool目录打包为toole.tar文件 */
tar cfz vpser.tar.gz tool /* 把tool目录打包且压缩为vpser.tar.gz文件，因为.tar文件几乎是没有压缩过的，MT的.tar.gz文件解压成.tar文件后差不多是10MB */
tar jcvf /var/bak/www.tar.bz2 /var/www/ /*创建.tar.bz2文件，压缩率高*/
tar xjf www.tar.bz2 /*解压tar.bz2格式*/
gzip -d ge.tar.gz /* 解压.tar.gz文件为.tar文件 */
unzip phpbb.zip /* 解压zip文件，windows下要压缩出一个.tar.gz格式的文件还是有点麻烦的 */
<strong>下载：</strong>
wget http://www.vpsyou.com/lnmp/lnmp.zip / *下载远程服务器上的文件到自己的服务器，连上传都省了，服务器不是100M就是1000M的带宽，下载一个2-3兆的MT还不是几十秒的事 */
wget -c http://www.vpsyou.com/lnmp/lnmp.zip /* 继续下载上次未下载完的文件 */
<strong>4、进程管理：</strong>
ps -aux /*ps 进程状态查询命令*/
ps命令输出字段的含义：
[*]USER，进程所有者的用户名。
[*]PID，进程号，可以唯一标识该进程。
[*]%CPU，进程自最近一次刷新以来所占用的CPU时间和总时间的百分比。
[*]%MEM，进程使用内存的百分比。
[*]VSZ，进程使用的虚拟内存大小，以K为单位。
[*]RSS，进程占用的物理内存的总数量，以K为单位。
[*]TTY，进程相关的终端名。
[*]STAT，进程状态，用(R–运行或准备运行；S–睡眠状态；I–空闲；Z–冻结；D–不间断睡眠；W-进程没有驻留页；T停止或跟踪。)这些字母来表示。
[*]START，进程开始运行时间。
[*]TIME，进程使用的总CPU时间。
[*]COMMAND，被执行的命令行。
ps -aux | grep nginx /*在所有进程中，查找nginx的进程*/
kill 1234 /*1234为进程ID，即ps -aux 中的PID*/
killall nginx /*killall 通过程序的名字，直接杀死所有进程，nginx为进程名*/
<strong>5、Vim操作：</strong>
移动类的：
h/j/k/l: 左/下/上/右　移一格
w : 向后词移动　（前面加数字移动多少个词）
b : 向前词移动　（前面加数字移动多少个词）
e : 向后移到词末
ge : 向前移到词末
$ : 行末
0 : 行首
tx : 向右查找本行的x并移到那儿（大写时向左）
33G : 移到文件的第33行
gg : 文件首行
G : 文件尾行
33% : 文件的33%处
H/M/L : 屏幕的首/中/尾行
zt/zz/zb : 当前行移到屏幕的首/中/底部
跳转：
” : 回到跳转来的地方
CTRL-O : 跳到一个 “较老” 的地方
CTRL-I : 则跳到一个 “较新” 的地方
查找：
/ : 向下查找（后加关键字）
? : 向上查找（后加关键字）
n : 下一条符合的记录
<strong>6、编辑：</strong>
i : 转换到插入模式
x : 删除当前字符
. : 重复最后一次的修改操作(同PS里ctrl+f执行滤镜)
u : 撤销操作
CTRL-R : 重做
p : 将删除的字符插入到当前位置(put)
退出保存：
:q : 退出
:q! : 不保存退出
ZZ : 保存后退出
:e! : 放弃修改重新编辑