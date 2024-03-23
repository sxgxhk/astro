---
title: Wordpress4.2头像不显示的处理方法
date: 2015-05-06 01:21:45.0
updated: 2021-12-22 17:01:20.0
url: /archives/wordpress4-2头像不显示的处理方法
categories: 
- 网站建设
tags: 
- Wordpress
---

<a href="http://uu126.cn/wp-content/uploads/2015/05/20130702135232-1466440144.jpg"><img class="aligncenter size-full wp-image-1760" src="http://uu126.cn/wp-content/uploads/2015/05/20130702135232-1466440144.jpg" alt="20130702135232-1466440144" width="500" height="200" /></a>
原来Wordpress版本头像不显示，都是修改wp-includes文件夹下的pluggable.php（之前的文章：<a href="http://uu126.cn/post/1554.html" target="_blank">http://uu126.cn/post/1554.html</a>），后来升级到4.2后，发现这个方法不行了，根本就找不到要更改的地，没办法又不想用插件，只好请教度娘，终于让我找到方法并解决了，下面就转述一下哈：
升级wordpress 之后去按照以前的方法找服务器设置，发现找不到了。蛋疼啊，但是最近又有点忙，所以一直没管它，今天搜索了一下发现新的头像服务器函数已经移动到”WordPress4.2.1wp-includeslink-template.php”(3604,29): $url = sprintf( ‘http://%d.gravatar.com/avatar/%s’, $gravatar_server, $email_hash );这里来了，如下：
<pre class="lang:php decode:true " >if ( $email_hash ) {
$args[‘found_avatar’] = true;
$gravatar_server = hexdec( $email_hash[0] ) % 3;
} else {
$gravatar_server = rand( 0, 2 );
}
$url_args = array(
‘s’ =&gt; $args[‘size’],
‘d’ =&gt; $args[‘default‘],
‘f’ =&gt; $args[‘force_default’] ? ‘y’ : false,
‘r’ =&gt; $args[‘rating’],
);
$url = sprintf( ‘http://%d.gravatar.com/avatar/%s’, $gravatar_server, $email_hash );
$url = add_query_arg(
rawurlencode_deep( array_filter( $url_args ) ),
set_url_scheme( $url, $args[‘scheme’] )
);</pre>
修改也很简单，将上面的3604行修改为：
<pre class="lang:php decode:true " >$url = sprintf( ‘http://cn.gravatar.com/avatar/%s’, $email_hash );</pre>
保存好上存覆盖，再刷新网页看看，是不是看见那小头像了，赶紧行动吧！