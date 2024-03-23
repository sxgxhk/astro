---
title: 解决office2003，无法卸载也无法安装问题
date: 2012-03-11 00:08:51.0
updated: 2021-12-22 17:01:20.0
url: /archives/解决office2003-无法卸载也无法安装问题
categories: 
- 生活百态
tags: 
---

<div>解决office2003，无法卸载也无法安装问题</div>
<div></div>
<table>
<tbody>
<tr>
<td>
<div id="blog_text">
<span style="color: #000000;">Office2003，无法卸载也无法安装（我已成功解决,我已将文件上传,有需要的兄弟自行[<a href="http://dinghui.ys168.com/" target="_blank"><span style="text-decoration: underline;"><span style="color: #0000ff;">下载</span></span></a>]，近日被认估权证搞的晕头转向把上传的事给忘了请大家见谅）
——————————————————————————————
本想将代码放上来的但百度有字数限制无奈大家自己去我的上传空间下文件名为“卸载你的OFFICE.rar”压包</span>
<span style="font-size: medium;"><strong><span style="color: #ff6600;"><span style="font-size: small;">以下是转来的文</span>
*****************************************************************************</span></strong></span>
从<a href="http://download.microsoft.com/download/e/9/d/e9d80355-7ab4-45b8-80e8-983a48d5e1bd/msicuu2.exe"><span style="text-decoration: underline;"><span style="color: #0000ff;">http://download.microsoft.com/download/e/9/d/e9d80355-7ab4-45b8-80e8-983a48d5e1bd/msicuu2.exe</span></span></a>下载WindowsInstaller清理工具并安装运行，删除office的安装信息
然后从<a href="http://www.52z.com/soft/6569.Html"><span style="text-decoration: underline;"><span style="color: #0000ff;">http://www.52z.com/soft/6569.Html</span></span></a>下载免安装版Office2003
从从压缩包中提取Office设置.exe并运行，然后单击清理office按钮
再从<a href="http://www.caicai.org/downinfo/25565.html"><span style="text-decoration: underline;"><span style="color: #0000ff;">http://www.caicai.org/downinfo/25565.html</span></span></a>或<a href="http://www.e76.cn/down/system/2766.html"><span style="text-decoration: underline;"><span style="color: #0000ff;">http://www.e76.cn/down/system/2766.html</span></span></a>下载OFFICE顽固卸载工具进行清理即可。
office2003无法正常安装卸载问题解决
一、症状：
1。点OFFICE里面的任何一个,比如WORD就会弹出一个错误的提示筐,说的是:这个操作只对当前安装的产品有效,无法运行该命令。系统里面的一些OFFICE文档也是无法识别的。现在想把OFFICE2003删除,可在控制面板的"添加/删除程序"里面也找不到相应的删除项目,用优化大师删除,又说不能删除,这个与WINDOWS存在关联。
2。在需要卸载或者更新Office 2003的时候，Window提示：“无法打开次修补程序包”，然后出错，停止卸载，尝试再安装一次，再卸载但是卸载的时候总是被错误打断！而不会出现卸载的窗口，不知道如何才能卸载。
3。当您首次尝试安装 Microsoft Office 2000 或 Microsoft Office XP，或者运行某个 Office 程序时，可能收到一条错误信息。如果您是通过 Administrator 用户帐户登录计算机的，可能收到下面的错误信息：
Fatal error during installation
如果您是通过具有管理员权限的标准用户帐户登录计算机的，可能收到下面的错误信息：
This patch package could not be opened.Contact the application vendor to verify that this is a valid Windows Installer patch package.
二、原因：
如果注册表中包含来自安装的较低版本 Office 的 Microsoft Windows Installer 信息，可能会发生此问题。注册表中包含错误的有关office的信息。
三、解决方案
要解决此问题，请运行 Windows Installer 清理实用工具，删除 Windows Installer 注册表设置，然后重新安装 Office。为此，请按照下列步骤操作： 1.下载、安装、然后运行 Windows Installer 清理实用工具，删除与您的 Office 安装相关的 Windows Installer 注册表设置。
1.从 Microsoft 下载中心可以下载以下文件：
msicuu2.exe <a href="http://download.microsoft.com/download/e/9/d/e9d80355-7ab4-45b8-80e8-983a48d5e1bd/msicuu2.exe"><span style="text-decoration: underline;"><span style="color: #0000ff;">http://download.microsoft.com/download/e/9/d/e9d80355-7ab4-45b8-80e8-983a48d5e1bd/msicuu2.exe</span></span></a>
2.要使用 Windows 清理实用工具，请按下列步骤操作：
a. 单击“开始”，指向“程序”，然后单击“Windows 安装清理”。
该对话框共有 4 个按钮：
按钮名称                     用途
---------------------------------------------------------------------
“全选”                     选择列表中的所有程序。
“全部清除”                                  清除对列表中所有程序的选择。
“删除”                     删除与所选程序相关的 Windows Installer 注册表设置。
“退出”                                    退出 Windows Installer 清理实用工具。
您可以在列表中选择多个项目，方法是在选择项目的同时按住 Shift 键或 Ctrl 键。
b. 选择要删除的程序，然后单击“删除”。
c. 单击“确定”，然后单击“退出”。
3.运行 Office 安装程序，重新安装 Office。
注意：由于 Windows Installer 清理实用工具会删除与 Windows Installer 相关的注册表设置，而不会删除 Office 程序文件，因此，请确保将 Office 安装在它原来所在的文件夹中，以防止硬盘上的文件重复。
如果单击“删除”，Windows Installer 清理实用工具将显示以下提示：
警告 - 选定的所有项都将从 Windows Installer数据库中删除。要使这些项正常工作，必须分别重新安装所有选定项。选择“确定”继续删除产品，选择“取消”终止删除操作。
如果单击“确定”，Windows Installer 清理实用工具将删除与选定程序相关联的所有 Windows Installer信息，其中包括“控制面板”的“添加/删除程序”中的程序项。
如果删除计算机上当前安装的程序的设置，则该程序将无法再添加或删除组件或者进行自我修复。要避免这些问题，Microsoft 建议您在使用这些程序之前重新安装它们。
在出现错误信息时应该怎么办？
Windows Installer 清理实用工具在出现问题时会通知您。下表列出了Windows Installer 清理实用工具可能显示的错误信息及这些错误发生的原因。
该实用工具要求与 Msizap.exe版本 2 或更高版本位于同一文件夹中。原因：无法在 Msicuu.exe 所在的同一文件夹中找到Msizap.exe 版本 2。
您必须具有管理员权限才能运行此实用工具。
要运行 Msicuu.exe，必须使用管理员             权限登录。
此实用工具要求安装并正确注册Windows Installer。
Msicuu.exe 使用 Windows Installer 对象模型标识已安装的产品。要更正此问题，请尝试重新注册Msi.dll。
Msi.dll进程解释：
msi - msi.dll - DLL文件信息
DLL 文件： msi 或者 msi.dll
DLL 名称： Windows Installer Library
描述：msi.dll是Windows安装程序MSI(Microsoft Installer)相关模块。
属于： Windows Installer
系统 DLL文件： 是
如何删除 Windows Installer 清理实用工具？
当安装 Windows Installer 清理实用工具时，它将在“控制面板”的“添加/删除程序”工具中创建该实用工具项。要删除 WindowsInstaller 清理实用工具，请在已安装的程序列表中单击该项，然后单击“添加/删除”。
四、其它工具下载：
<a href="http://bbs.macd.cn/viewthread.php?tid=898216"><span style="text-decoration: underline;"><span style="color: #0000ff;">http://bbs.macd.cn/viewthread.php?tid=898216</span></span></a>
OFFICE2003顽固卸载〖绿色版〗
<a href="http://www.e76.cn/down/system/2766.html"><span style="text-decoration: underline;"><span style="color: #0000ff;">http://www.e76.cn/down/system/2766.html</span></span></a>
软件名称：OFFICE2003顽固卸载
<a href="http://www.175pc.cn/article/31/2006/20061217405.html"><span style="text-decoration: underline;"><span style="color: #0000ff;">http://www.175pc.cn/article/31/2006/20061217405.html</span></span></a>
&nbsp;
&nbsp;
Office 2003精彩问答集
<a href="http://post.baidu.com/f?kz=91040575"><span style="text-decoration: underline;"><span style="color: #0000ff;">http://post.baidu.com/f?kz=91040575</span></span></a>
</div></td>
</tr>
</tbody>
</table>