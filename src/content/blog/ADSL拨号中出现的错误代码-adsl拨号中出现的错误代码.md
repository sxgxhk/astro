---
title: ADSL拨号中出现的错误代码
date: 2012-11-18 22:28:57.0
updated: 2021-12-22 17:01:20.0
url: /archives/adsl拨号中出现的错误代码
categories: 
- 生活百态
tags: 
---

<pre id="best-content-269908413">ADSL拨号中出现的错误代码
Error 602 The port is already open
问题：拨号网络网络由于设备安装错误或正在使用，不能进行连接
原因：RasPPPoE没有完全和正确的安装
解决：卸载干净任何PPPoE软件，重新安装
Error 605 Cannot set port information
问题：拨号网络网络由于设备安装错误不能设定使用端口
原因：RasPPPoE没有完全和正确的安装
解决：卸载干净任何PPPoE软件，重新安装
Error 606 The port is not connected
问题：拨号网络网络不能连接所需的设备端口
原因：RasPPPoE没有完全和正确的安装，连接线故障，ADSL MODEM故障
解决：卸载干净任何PPPoE软件，重新安装，检查网线和 ADSL MODEM
Error 608 The device does not exist
问题：拨号网络网络连接的设备不存在
原因：RasPPPoE没有完全和正确的安装
解决：卸载干净任何PPPoE软件，重新安装
Error 609 The device type does not exist
问题：拨号网络网络连接的设备其种类不能确定
原因：RasPPPoE没有完全和正确的安装
解决：卸载干净任何PPPoE软件，重新安装
Error 611 The route is not available/612 The route is not allocated
问题：拨号网络网络连接路由不正确
原因：RasPPPoE没有完全和正确的安装，ISP服务器故障
解决：卸载干净任何PPPoE软件，重新安装，致电ISP询问
Error 617 The port or device is already disconnecting
问题：拨号网络网络连接的设备已经断开
原因：RasPPPoE没有完全和正确的安装，ISP服务器故障，连接线，ADSL MODEM故障
解决：卸载干净任何PPPoE软件，重新安装，致电ISP询问 ，检查网线和 ADSL MODEM
Error 619
问题：与ISP服务器不能建立连接
原因：ADSL ISP服务器故障，ADSL电话线故障
解决：检查ADSL信号灯是否能正确同步。致电ISP询问
Error 621 Cannot open the phone book file
Error 622 Cannot load the phone book file
Error 623 Cannot find the phone book entry
Error 624 Cannot write the phone book file
Error 625 Invalid information found in the phone book
问题：Windows NT或者Windows 2000 Server网络RAS网络组件故障
原因：软件安装问题
解决：卸载所有PPPoE软件，重新安装RAS网络组件和RasPPPoE
Error 630
问题：ADSL MODEM没有没有响应
原因：ADSL电话线故障，ADSL MODEM故障（电源没打开等）
解决：检查ADSL设备
Error 633
问题：拨号网络网络由于设备安装错误或正在使用，不能进行连接
原因：RasPPPoE没有完全和正确的安装
解决：卸载干净任何PPPoE软件，重新安装
Error 638
问题：过了很长时间，无法连接到ISP的ADSL接入服务器
原因：ISP服务器故障；在RasPPPoE所创建的不好连接中你错误的输入了一个电话号码
解决：运行其创建拨号的Raspppoe.exe检查是否能列出ISP服务，以确定ISP正常;把所使用的拨号连接中的 电话号码清除或者只保留一个0。
Error 645
问题：网卡没有正确响应
原因：网卡故障，或者网卡驱动程序故障
解决：检查网卡，重新安装网卡驱动程序
Error 650
问题：远程计算机没有响应，断开连接
原因：ADSL ISP服务器故障，网卡故障，非正常关机造成网络协议出错
解决：检查ADSL信号灯是否能正确同步，致电ISP询问；检查网卡，删除所有网络组件重新安装 网络。
Error 651
问题：ADSL MODEM报告发生错误
原因：Windows处于安全模式下，或其他错误
解决：出现该错误时，进行重拨，就可以报告出新的具体错误代码
Error 691
问题：输入的用户名和密码不对，无法建立连接
原因：用户名和密码错误，ISP服务器故障
解决：使用正确的用户名和密码，并且使用正确的ISP账号格式(name@service),致电ISP询问。
Error 718
问题：验证用户名时远程计算机超时没有响应，断开连接
原因：ADSL ISP服务器故障
解决：致电ISP询问
Error 720
问题：拨号网络无法协调网络中服务器的协议设置
原因：ADSL ISP服务器故障，非正常关机造成网络协议出错
解决：致电ISP询问，删除所有网络组件重新安装网络。
Error 734
问题：PPP连接控制协议中止
原因：ADSL ISP服务器故障，非正常关机造成网络协议出错
解决：致电ISP询问，删除所有网络组件重新安装网络。
Error 738
问题：服务器不能分配IP地址
原因：ADSL ISP服务器故障，ADSL用户太多超过ISP所能提供的IP地址
解决：致电ISP询问
Error 797
问题：ADSL MODEM连接设备没有找到
原因：ADSL MODEM电源没有打开，网卡和ADSL MODEM的连接线出现问题，软件安装以后相应的协议没有正确邦定，在创立拨号连接时，建立了错误的空连接
解决：检查电源，连接线；检查网络属性，RasPPPoE相关的协议是否正确的安装并正确邦定（相关协议），检查网卡是否出现?号或!号，把它设置为Enable;检查拨号连接的属性，是否连接的设备使用了一个“ISDN channel-Adapter Name(xx)” 的设备，该设备为一个空设备，如果使用了取消它，并选择 正确的PPPoE设备代替它，或者重新创立拨号连接。</pre>