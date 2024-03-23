---
title: Ghost由1.X升级到2.0了
date: 2018-08-24 19:25:58.0
updated: 2021-12-22 17:01:20.0
url: /archives/ghost由1-x升级到2-0了
categories: 
- 网站建设
tags: 
- Ghost
---

<!-- wp:paragraph -->
<p>据说我的博客已经长草好一会了，的确如此，最近不知道是懒了还是懒了，又或是懒了（这不还是懒嘛233）。小博经历了很多，不论是空间还是程序，可谓是历经沧桑呀（越扯越远了……）。就像现在用的是Ghost作为博客程序，由于Ghost官方更新太频繁了，后来就犯懒没更新了，这不今天上线一瞧，人家都已经更新到2.0.3了，我还是1.21.5，差的好像有点大嘛，那咋办？咱也升呗！~</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>为了保险起见，还是在后台对硬盘做了个快照（感谢腾讯云，快照目前还是免费的，这点要批评一下套路云，啥啥都开始收费），接着翻翻Ghost官网的说明，还好瞄了一眼，要不然可能会出事，原来我还不能直接升级到2.0，得先升级到1.X的最高版，然后才能升级到2.0，具体的看官网操作说明：</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><p>安装最新的Ghost CLI版本。Ghost 2.0升级需要Ghost-CLI 1.9.0或更高版本。我们支持的服务器设置具有单个系统范围的node.js版本，因此install / update命令如下所示：</p></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><p>如果您未遵循支持的安装指南，请根据需要调整此步骤。</p></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><p>2. 运行update命令</p></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><p>从您的发布目录中（通常cd /var/www/ghost/但相应地调整）运行以下命令：</p></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><p>Ghost CLI将检查所有内容是否已准备好进行升级，并告知您是否需要执行任何额外步骤，如果一切正常，则升级将继续进行。如果您遇到任何问题，请参阅一般的升级指南，如果这对我们的社区论坛没有帮助。</p></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><p>如有必要，请升级到1.x的最新版本。如果您的出版物尚未在最新的Ghost 1.x版本上，CLI将通知您需要先升级到此版本。这应该快速而轻松，升级到最新的1.x版本的命令如下：</p></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><p>完成后，您可以` ghost update `再次运行从最新的1.x升级到最新的2.x.</p></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>以上就是使用大名鼎鼎的谷歌翻译来的，凑合着看吧，玩Ghost的应该能看懂吧，有问题欢迎留言，升级到2.0后最大的变化就是编辑器，简洁到都不像是个编辑器了，可谓是不体验不晓得呀，官网也给出了相关的介绍，照搬截图看吧：</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/ghost2-0_01.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/ghost2-0_02.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cdn.uu126.cn/201808/ghost2-0_03.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>除了后台编辑器，其它的好像也没出啥变化，可能是体验还不够，总之还是那句话：没事多翻翻、多折腾。</p>
<!-- /wp:paragraph -->