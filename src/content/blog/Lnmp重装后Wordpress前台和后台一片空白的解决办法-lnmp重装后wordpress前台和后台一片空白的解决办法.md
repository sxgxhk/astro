---
title: Lnmp重装后Wordpress前台和后台一片空白的解决办法
date: 2016-01-26 05:16:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/lnmp重装后wordpress前台和后台一片空白的解决办法
categories: 
- 网站建设
tags: 
- Wordpress
---

<p>系统出了一些问题。所以折腾了下。重新安装LNMP环境后，发现wordpress前台和后台一片空白。<br />弄了半天以为是系统升级造成的。网上查了下貌似是wordpress版本和主题的原因。小记一下。</p><p><img src="https://cdn.uu126.cn/wp-content/uploads/2016/01/update-wordpress.jpg" alt="请输入图片描述" title="请输入图片描述"></p><h3>可能原因</h3><p>这个问题，一般是在进行以下操作后出现的：</p><ul><li>更换新主题</li><li>安装或升级插件</li><li>升级Wordpress版本</li></ul><h3>问题的根源在于 主题、插件和wordpress自身 三者之间的不兼容：</h3><ul><li>某些主题集成了很多强大的功能，可能与现在使用的插件冲突</li><li>某些插件版本或主题不兼容你现在使用的Wordpress版本</li></ul><h3>解决办法</h3><blockquote><p>方法一：通过 FTP 重新命名当前启用的主题</p></blockquote><p>把当前安装的主题文件夹重命名的话，会强制 WordPress 自动选择默认的主题，然后就可以正常载入了。</p><ul><li>通过 FTP 找到 wp-contents/themes 文件夹，重命当前安装的主题文件夹。例如：把 yusi1.0 命名为 yusi</li><li>登录 WordPress 后台， 禁用所有插件，然后 FTP 将原来的主题名字改回来，重新激活，</li><li>如果一切正常，说明是这个主题和某插件冲突，逐个激活插件，找出冲突的插件并禁用；</li><li>如果重新激活主题又出现问题，说明这个主题和你现在使用的wordpress版本不兼容，或者主题存在错误。</li></ul><blockquote><p>方法二：通过 FTP 重设插件文件夹</p></blockquote><ul><li>通过 FTP 登录，将 wp-contents 下的 plugins 文件夹重命名为 plugins-temp</li><li>在同一目录下创建一个新的文件夹为 plugins ，重新登录 WordPress 后台，</li><li>如果问题依旧，说明是现用主题和你的 WordPress 不兼容，或主题存在错误；</li><li>如果一切正常，说明是某个插件与当前 wordpress 版本或主题冲突，把插件从 plugins-temp 移到 plugins ，然后逐个重新激活，找出不兼容的插件并禁用。</li></ul><p>本文转载自：wordpress之家</p>