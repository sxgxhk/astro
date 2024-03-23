---
title: 笔记本自带Win8改装Win7的操作步骤及常见问题（转自联想论坛）
date: 2014-04-13 18:37:44.0
updated: 2021-12-22 17:01:20.0
url: /archives/笔记本自带win8改装win7的操作步骤及常见问题
categories: 
- 生活百态
tags: 
- 系统安装
---

故障现象
修改前的注意事项：
若您确定要将您笔记本预装的Windows8系统改装为Windows7系统，请注意如下重要事项：1.     由于您笔记本预装的Windows8系统需要使用BIOS中的UEFI功能及GPT分区表，所以在您将系统改装为Windows7系统时，需要将随机Windows8系统的所有分区全部删除（包括Windows8引导分区、Windows8系统修复分区、GPT分区表的保留分区、一键恢复的功能分区、Windows8系统系统分区、用户数据分区及一键恢复的数据分区）因为这些分区都是在GPT分区表下建立的，而Windows7使用的是MBR分区表，两者互不兼容。所以您在将您笔记本预装的Windows8系统改装为Windows7系统的过程中就会失去您硬盘中所有分区的数据及预装的Windows8系统的一键恢复功能（即无法通过联想的一键恢复功能恢复至预装的Windows8系统，若您想恢复为预装的Windows8系统，可以联系联想服务站恢复到预装的Windows8系统）。所以请您再进行您笔记本预装的Windows8系统改装为Windows7系统的操作前将您笔记本硬盘中所有的重要数据备份到移动存储介质中（如：U盘、移动硬盘等）。2.     为了保证系统顺利安装，我们强烈推荐您使用正版的Windows7操作系统光盘进行（若您的笔记本没有光驱，我们强烈推荐您使用USB光驱来完成操作）。不要使用GHOST版的Windows7或其他非正版的Windows7操作系统光盘。否则会造成您操作无效。主要原因还是与第一条描述的分区方式相关。
解决方案
一、下文分别描述联想Y400、G480与扬天V480、昭阳K49等机型的具体操作步骤1、消费YZGN机型预装的Windows8系统改装为Windows7系统的具体操作步骤（Y400、G480等）
IdeaPad Y480、Y580、Y400、Y500、Z380、Z480、Z580、Z485、Z585
Erazer N480、N580、Z400、Z500
Lenovo G480、G580、G485、G585
1.先重新启动计算机，并按下笔记本键盘上“F2”键或“Fn键+”F2“键进
入笔记本的BIOS设置界面（若您的笔记本为Y400、Y500请您先关闭计算机，按下”一键恢复按钮”开机，通过选择启动菜单中的“BIOS Setup”项目进入BIOS设置界面）
2.进入BIOS设置界面后，按下键盘上“→”键将菜单移动至“EXIT“项目，按下键盘上“↓”按键选择到” OS Optimized Defaults“选项，按下“回车”键打开该选项的设置菜单，按下键盘上“↓”按键，将该选项默认的”Win8 64bit“修改为”Others“之后，按下“回车”键确认。之后按下键盘上“↑”按键选择到”Load Default Setting“选项，按下回车键启动恢复BIOS默认功能窗口，在该窗口中直接按下笔记本键盘上的”回车“键启动BIOS恢复默认功能。之后再按下笔记本键盘上“F10”键或“Fn键+”F10“键启动BIOS保存设置窗口，在该窗口中直接按下笔记本键盘上的”回车“键启动BIOS保存设置并诚信启动计算机功能。（如下图）
<img id="aimg_1120" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125920rhrkurjuvlvh7cho.jpg" width="494" />
3.在计算机重新启动至“Lenovo“LOGO画面时，并按下笔记本键盘上“F2”键或“Fn键+”F2“键进入笔记本的BIOS设置界面（若您的笔记本为Y400、Y500请您在计算机重新启动至“Lenovo“LOGO画面时按下笔记本的电源开关关闭计算机之后，按下”一键恢复按”钮开机，通过选择启动菜单中的“BIOS Setup”项目再次进入BIOS设置界面）将按下键盘上“→”键菜单移动至“Boot“项目，找到该项目下的”Boot Mode“选项，按下“回车”键打开该选项的设置菜单，按下键盘上“↓”按键，将该选项默认的”UEFI“修改为”Legacy Support“之后按下“回车”键确认，再按下键盘上“↓”按键选择”Boot Priority“选项，按下键盘上“↓”按键将该选项默认的”UEFI First“修改为”Legacy First“之后按下“回车”键确认。之后再按下笔记本键盘上“F10”键或“Fn键+”F10“键启动BIOS保存设置窗口，在该窗口中直接按下笔记本键盘上的”回车“键启动BIOS保存设置并重新启动计算机功能。（如下图）
<img id="aimg_1121" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125920bc1ubajpjc0az5cj.jpg" width="504" />
4.在计算机重新启动至“Lenovo“LOGO画面时，并按下笔记本键盘上“F12”键或“Fn键+”F12“键进入笔记本的引导设置界面（若您的笔记本为Y400、Y500请您在计算机重新启动至“Lenovo“LOGO画面时按下笔记本的电源开关关闭计算机之后，按下”一键恢复按钮”开机，按下键盘上“↓”按键选择启动菜单中的“Boot Menu”项目之后按下“回车”键进入引导设置界面）。在此时将您笔记本的光驱托盘弹出，放入正版的Windows7操作系统光盘之后将光驱托盘推回，同时选择该界面中的“SATA ODD“或“USB ODD”项目并按下”回车“键，以实现光驱启动。（如下图）
<img id="aimg_1122" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125920wfccv4ydocpiccea.jpg" width="554" />
2、扬天VBKEM机型预装的Windows8系统改装为Windows7系统的具体操作步骤（V480、E49等）
扬天V480、V480c、V480s、V580、B480、B580、B490、B590、B43xx、M490、M490s、M590、M495
昭阳E49、K49、K29
1.先重新启动计算机，并按下笔记本键盘上“F1”键进入笔记本的BIOS设置
界面。
2.进入BIOS设置界面后，按下键盘上“→”键将菜单移动至“Restart“项目，按下键盘上“↓”按键选择到” OS Optimized Defaults“选项，按下“回车”键打开该选项的设置菜单，按下键盘上“↑”按键将该选项默认的”Enabled“修改为”Disabled“之后，按下“回车”键确认。按下键盘上“↑”按键选择到”Load Setup Defaults“选项，按下回车键启动恢复BIOS默认功能窗口，在该窗口直接按下笔记本键盘上的”回车“键启动BIOS恢复默认功能。之后再按下笔记本键盘上“F10”键启动BIOS保存设置窗口，在该窗口中直接按下笔记本键盘上的”回车“键启动BIOS保存设置并重新启动计算机功能。（如下图）
<img id="aimg_1123" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125921sk60dddkdusy5dsv.jpg" width="560" />
&nbsp;
<div><img id="aimg_1124" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125921mjzmnginvs5bnbbj.jpg" width="560" /></div>
3.在计算机重新启动至“Lenovo“LOGO画面时，并按下笔记本键盘上“F1”键进入笔记本的BIOS设置界面，按下键盘上“→”键将菜单移动至“Startup“项目，按下键盘上“↓”按键选择到”UEFI/Legacy Boot“选项，按下“回车”键打开该选项的设置菜单，按下键盘上“↓”按键并将该选项默认的”Both“修改为”Legacy Only“之后按下“回车”键确认。再按下笔记本键盘上“F10”键启动BIOS保存设置窗口，在该窗口中直接按下笔记本键盘上的”回车“键启动BIOS保存设置并诚信启动计算机功能。（如下图）
<div><img id="aimg_1125" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125921bwowadady3f55zid.jpg" width="560" /></div>
4.在计算机重新启动至“Lenovo“LOGO画面时，并按下笔记本键盘上“F12”键进入笔记本的引导设置界面。在此时将您笔记本的光驱托盘弹出，放入正版的Windows7操作系统光盘之后将光驱托盘推回，同时选择该界面中的“ATAPI CD1“项目并按下”回车“键，以实现光驱启动。（如下图）
<div><img id="aimg_1126" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125921nvz1efbxcypwl4jl.jpg" width="554" /></div>
二、如上为BIOS调整方法，下面为系统安装相关的方法
1、在进入Windows7系统安装画面后，按照如下步骤进入到Windows7系统分区画面，具体步骤如下：
<img id="aimg_1127" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125922hl525o5vx5c2fitz.jpg" width="589" />
&nbsp;
<div><img id="aimg_1128" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125922czkv3ik33oi209ii.jpg" width="589" /></div>
&nbsp;
<div><img id="aimg_1129" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125922h1jk00sv328fsjv3.jpg" width="600" /></div>
2、进入Windows7系统分区画面后，请将其中的全部分区都删除，然后再重新创建新的分区即可。
请您再次注意：以上操作会将您笔记本硬盘中的分区全部删除，所以您笔记本
您笔记本硬盘中所有数据将会丢失，请您再进行此操作前您笔记本硬盘中所有
的重要数据备份到移动存储介质中（如：U盘、移动硬盘等）。
<img id="aimg_1130" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125922iu0kroj1iojkfupl.jpg" width="554" />
将全部分区都删除后，单击“新建”，重新创建新的分区。（受MBR硬盘的限制，您在系统安装界面对多只能分出4个主分区，如果您需要更多的分区，请系统安装完成后在系统中划分分区）
<img id="aimg_1131" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125922a0hz825l5bbslile.jpg" width="458" />
分区创建完成后，先将分区全部格式化，格式化完成后，
选择好您要安装系统的分区，点击“下一步“进行系统安装即可。
Windows 7详细安装步骤请参考：
<span style="color: #336699;">h<a href="http://uu126.cn/post/593.html" target="_blank">ttp://blog.kl357.com/post/593.html</a></span>
3、若您使用上述方法依旧无法进行分区操作，请按照如下步骤进行：
A. 在进入Windows7系统安装的首画面，按下键盘上“Shift”键+“F10”键或Shift”键+“Fn”键+“F10”键。启动CMD命令行模式窗口：
<img id="aimg_1132" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125922uucll6gtcuz3ccdl.jpg" width="584" />
<img id="aimg_1133" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125923r2m0s2zrx0ou6mfe.jpg" width="600" />
B．在CMD命令行窗口中直接输入“diskpart”命令，之后按下“回车”键，就会自动进入Diskpart模式：
<img id="aimg_1134" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125923t1zngo6wm0eg09wg.jpg" width="600" />
C．进入Diskpart模式后，再输入“list disk”命令并按下“回车”键来确认您笔记本中硬盘的数量及位置，如下图中的笔记本只有一块硬盘，位置在：
<img id="aimg_1135" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125923r764f7u24u4x3u2f.jpg" width="600" />
D．输入“select disk 0”命令并按下“回车”键来选择您笔记本中的硬盘：
<img id="aimg_1136" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125923m9rk0dr09w4pogpk.jpg" width="600" />
E．输入“clean”命令并按下“回车”键来请除您笔记本的硬盘中的所有分区及数据：
<img id="aimg_1137" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125924k6vpzyvxhwryprr2.jpg" width="600" />
F．输入“convert mbr”命令并按下“回车”键来将您笔记本的硬盘的分模式从GPT模式转换为MBR模式：
<img id="aimg_1138" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125924hms3m6zwuwruvmu3.jpg" width="600" />
G．输入“exit”命令并按下“回车”键退出Diskpart模式，之后，再次“exit”命令并按下“回车”键退出退出CMD命令行模式：
<img id="aimg_1139" alt="" src="http://lenovobbs.lenovo.com.cn/data/attachment/forum/201309/18/125924ho4xucjths0acdqf.jpg" width="600" />
H．操作完成后，请您点击Windows7系统安装的首画面窗口右上角的“红叉”，之后在弹出的窗口中选择“是”，即可重新启动您的笔记本，在计算机重新启动至“Lenovo“LOGO画面时，并按下笔记本键盘上“F12”键或“Fn键+”F12“键进入笔记本的引导设置界面（若您的笔记本为Y400、Y500请您在计算机重新启动至“Lenovo“LOGO画面时按下笔记本的电源开关关闭计算机之后，按下”一键恢复按钮”开机，通过选择启动菜单中的“Boot Menu”项目再次进入引导设置界面）。在此时将您笔记本的光驱托盘弹出，放入正版的Windows7操作系统光盘之后将光驱托盘推回，同时选择该界面中的“SATA ODD“项目并按下”回车“键，以实现光驱启动。之后再按照前6步的操作分区即可（此时您无需再进行删除分区操作，因为在重启计算机之前，分区已经被全部删除了）。