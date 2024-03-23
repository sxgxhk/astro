---
title: 阿里公共DNS 正式发布
date: 2014-06-07 06:19:14.0
updated: 2021-12-22 17:01:20.0
url: /archives/阿里公共dns-正式发布
categories: 
- 网站建设
tags: 
- 服务器
- 淘宝
---

<p style="color: #333333;">喜大普奔！集阿里巴巴集团众多优秀工程师开发维护的公共DNS---AliDNS终于上线啦！作为国内最大的互联网基础服务提供商，阿里巴巴在继承多年优秀技术的基础上，通过提供性能优异的公共DNS服务，为广大互联网用户提供最可靠的递归解决方案。AliDNS：稳定！快速！智能！</p>
<p style="color: #333333;">是否还记得年初那场轰轰烈烈的DNS异常劫持，让很多正在淘宝买东西的各位亲无法正常浏览和下单。DNS作为互联网的入口，越来越受到大家的重视。如此重要的东西，也常常被那些隐藏在角落里的黑客惦记着，主动攻击每天都在发生着.攻击一旦成功，整个互联网的访问就瘫痪了</p>
<p style="color: #333333;">阿里巴巴作为国内最大的互联网公司，有义务有能力为大家提供更好的DNS服务，让全国小伙伴都能更好的访问到互联网上的资源，不论是逛淘宝玩游戏刷微博看视频，还有每天都存在的秒杀！要快要好！</p>
<p style="color: #333333;"><a href="http://uu126.cn/wp-content/uploads/2014/06/20140606221508.jpg"><img class="alignnone wp-image-674 size-full" src="http://uu126.cn/wp-content/uploads/2014/07/20140606221508.jpg" alt="20140606221508" width="780" height="228" /></a></p>
<p style="color: #333333;">我们有什么优势？</p>
<p style="color: #333333;">1：我们有国内最好的网络资源，无论是电信联通还是移动教育网，都能快速访问到DNS，并返回最优质的资源访问。</p>
<p style="color: #333333;">2：国内一流的IP库信息，提供最为准确的解析效果。</p>
<p style="color: #333333;">3：国内一流的安全性：AliDNS拥有独立的防攻击体系。</p>
<p style="color: #333333;">4：使用简单：采用Anycast技术,全球统一服务ip：223.5.5.5 223.6.6.6，全国多数据中心冗余.</p>
<p style="color: #333333;">使用设置方法如下：</p>
<ul class="media-list" style="color: #1b1b1b;">
	<li class="media">
<div id="windows" class="media-body">
<h5 id="win8-setup" style="color: #1982d1;">Windows 8</h5>
<div class="media">
<ol>
	<li>打开Windows 8系统控制面板，点击右上角的以图标方式显示，点击“网络和共享中心”选项。<img src="http://uu126.cn/wp-content/uploads/2014/07/win8-1.jpg" alt="" /></li>
	<li>点击网络和共享中心左侧的“更改适配器设置”链接，如下图：<img src="http://uu126.cn/wp-content/uploads/2014/07/win8-2.jpg" alt="" /></li>
	<li>选中正在联网的网络连接,我这里是，鼠标右键菜单里选择“属性”<img src="http://uu126.cn/wp-content/uploads/2014/07/win8-3.jpg" alt="" /></li>
	<li>在网络连接属性窗口中选中“Internet 协议版本 4 (TCP/IPv4)”，然后点击“属性”。<img src="http://uu126.cn/wp-content/uploads/2014/07/win8-4.jpg" alt="" /></li>
	<li>选择使用指定的DNS，在DNS服务器地址中输入223.5.5.5 和 223.6.6.6，输入后确定退出即设置完成。<img src="http://uu126.cn/wp-content/uploads/2014/07/win8-5.jpg" alt="" /></li>
</ol>
</div>
<h5 id="win7-setup" style="color: #1982d1;">Windows 7</h5>
<div class="media">
<ol>
	<li>通过单击「开始」按钮 「开始」按钮的图片，然后单击“控制面板”，打开“网络连接”。 在搜索框中，键入适配器，然后在“网络和共享中心”下，单击“查看网络连接”</li>
	<li>右键单击要更改的连接，然后单击“属性”。 需要管理员权限 如果系统提示您输入管理员密码或进行确认，请键入该密码或提供确认</li>
	<li>单击“联网”选项卡。在“此连接使用下列项目”下，单击“Internet 协议版本 4 (TCP/IPv4)”或“Internet 协议版本 6 (TCP/IPv6)”，然后单击“属性”
<img src="http://uu126.cn/wp-content/uploads/2014/07/tcp-ip-0.jpg" alt="" /></li>
	<li>单击“使用下面的 DNS 服务器地址”，然后在“首选 DNS 服务器”和“备用 DNS 服务器”框中，键入主 DNS 服务器和辅助 DNS 服务器的地址
<img src="http://uu126.cn/wp-content/uploads/2014/07/tcp-ip.jpg" alt="" /></li>
</ol>
</div>
<h5 id="vista-setup" style="color: #1982d1;">Windows VISTA</h5>
<div class="media">
<ol>
	<li>点击“开始”按钮，然后选择控制面板</li>
	<li>点击“查看网络状态和任务”。</li>
	<li>点击“查看状态”。</li>
	<li>点击“ 属性 ”按钮。</li>
	<li>Vista可能会要求您的许可才能进行更改。如果是这样，单击“ 继续”按钮。</li>
	<li>选择Internet协议版本4（TCP/IPv4） ，然后单击“属性”按钮 。</li>
	<li>单击“使用下面的DNS服务器地址”，然后在首选DNS服务器和备用DNS服务器中输入 223.5.5.5 和223.6.6.6。</li>
	<li>点击OK按钮，然后点击“关闭”按钮，再次点击“关闭”按钮，关闭网络和共享中心的窗口 。</li>
</ol>
</div>
<h5 style="color: #1982d1;">Windows XP</h5>
<div class="media">
<ol>
	<li>从开始菜单中选择控制面板</li>
	<li>从控制面板选项中单击网络连接。</li>
	<li>从网络连接窗口中选择您的连接。如果你有不止一个连接，选择你的默认/当前连接。</li>
	<li>右键点击属性</li>
	<li>选择internet协议（TCP/IP）然后单击属性。</li>
	<li>单击“使用下面的DNS服务器地址”， 在首选DNS服务器和备选DNS服务器中输入223.5.5.5 和223.6.6.6。</li>
</ol>
</div>
</div></li>
</ul>