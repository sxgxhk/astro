---
title: 快速恢复被破坏的XP系统文件
date: 2012-03-12 23:53:48.0
updated: 2021-12-22 17:01:20.0
url: /archives/快速恢复被破坏的xp系统文件
categories: 
- 生活百态
tags: 
---

<table cellspacing="0" cellpadding="0">
<tbody>
<tr>
<td id="postmessage_1497102">
<div>如果Windows XP的系统文件被病毒或其它原因破坏了，我们可以从Windows XP的安装盘中恢复那些被破坏的文件。
具体方法：在Windows XP的安装盘中搜索被破坏的文件，需要注意的是，文件名的最后一个字符用底线“_”代替，例如:如果要搜索“Notepad.exe”则需要用“Notepad.ex_”来进行搜索。
搜索需要的文件
搜索到了之后，打开命令行模式(在“运行”中输入“cmd”)，然后输入:“EXPAND 源文件的完整路径 目标文件的完整路径”。例如: EXPAND D:SETUPNOTEPAD.EX_ C:WindowsNOTEPAD.EXE。有一点需要注意的是，如果路径中有空格的话，那么需要把路径用双引号(英文引号)包括起来。
找到当然是最好的，但有时我们在Windows XP盘中搜索的时候找不到我们需要的文件。产生这种情况的一个原因是要找的文件是在“CAB”文件中。由于Windows XP把“CAB”当作一个文件夹，所以对于Windows XP系统来说，只需要把“CAB”文件右拖然后复制到相应目录即可。
如果使用的是其他Windows平台，搜索到包含目标文件名的“CAB”文件。然后打开命令行模式，输入:“EXTRACT /L 目标位置 CAB文件的完整路径”，例如: EXTRACT /L C:Windows D:I386Driver.cab Notepad.exe。同前面一样，如同路径中有空格的话，则需要用双引号把路径包括起来。</div></td>
</tr>
</tbody>
</table>