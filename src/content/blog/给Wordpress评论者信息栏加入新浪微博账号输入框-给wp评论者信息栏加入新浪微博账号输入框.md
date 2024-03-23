---
title: 给Wordpress评论者信息栏加入新浪微博账号输入框
date: 2016-10-29 20:48:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/给wp评论者信息栏加入新浪微博账号输入框
categories: 
- 网站建设
tags: 
- Wordpress
---

<p>首先就是无论你采用哪种方法，都要在<code> functions.php </code>中加入如下代码:</p><pre><code class="lang-php">    add_action( 'comment_post','save_comment_meta_data' );
    function save_comment_meta_data( $comment_id ) {
        add_comment_meta( $comment_id, 'sinawb', $_POST['sinawb'] );
        $expire = time() + 99999999;
        $domain = ($_SERVER['HTTP_HOST'] != 'localhost') ? $_SERVER['HTTP_HOST'] : false; // make cookies work with localhost
        setcookie('bigfa_sinawb',$_POST['sinawb'],$expire,'/',$domain,false);
    }
    add_filter( 'get_comment_author_link',    'attach_twitter_to_author' );
    function attach_twitter_to_author( $author ) {
        $tw = get_comment_meta( get_comment_ID(), 'sinawb', true );
        if($tw)
            $author .= &quot; / &amp;lt;a href='http://weibo.com/n/$tw' title='@$tw' target='_blank'&amp;gt;@$tw&amp;lt;/a&amp;gt;&quot;;
        return $author;
    }</code></pre><p>如果是自定义评论，则在<code> comments.php </code>相应位置:</p><p>如果是默认的comment_form，则下面的代码加到<code> functions.php </code>中:</p><pre><code class="lang-php">add_filter( 'comment_form_defaults',    'change_comment_form_defaults');
function change_comment_form_defaults($default) {
    $commenter = wp_get_current_commenter();
    $default['fields']['url'] .= '&amp;lt;p class=&quot;comment-form-author&quot;&amp;gt;&amp;lt;label id=&quot;author_sinawb&quot; for=&quot;sinawb&quot;&amp;gt;Weibo&amp;lt;input id=&quot;sinawb&quot; type=&quot;text&quot; tabindex=&quot;5&quot; value=&quot;';
    if(isset($_COOKIE['bigfa_sinawb'])) $default['fields']['url'] .= $_COOKIE['bigfa_sinawb'];
    $default['fields']['url'] .='&quot; name=&quot;sinawb&quot;&amp;gt;&amp;lt;/label&amp;gt;&amp;lt;/p&amp;gt;';
    return $default;
}</code></pre>