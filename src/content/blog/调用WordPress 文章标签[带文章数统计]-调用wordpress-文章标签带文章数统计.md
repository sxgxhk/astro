---
title: 调用WordPress 文章标签[带文章数统计]
date: 2016-10-29 20:53:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/调用wordpress-文章标签带文章数统计
categories: 
- 网站建设
tags: 
- Wordpress
---

<p>我们都知道<code> the_tags </code>和<code> get_the_tags </code>可以调用文章标签，但也无非就是调用标签，其实每个标签都包含了很多参数，只调用名字和链接有点太浪费了，所以我们在加上一个小小的文章数统计，瞬间变的高大上起来。</p><h4>实现方法</h4><p>下面的代码加到<code> functions.php </code>中:</p><pre><code class="lang-php">    function fa_get_the_term_list( $id, $taxonomy ) {
    $terms = get_the_terms( $id, $taxonomy );
    $term_links = &quot;&quot;;
    if ( is_wp_error( $terms ) )
        return $terms;
    if ( empty( $terms ) )
        return false;
    foreach ( $terms as $term ) {
        $link = get_term_link( $term, $taxonomy );
        if ( is_wp_error( $link ) )
            return $link;
        $term_links .= '&amp;lt;a href=&quot;' . esc_url( $link ) . '&quot; class=&quot;js-loaded post--keyword&quot; data-title=&quot;' . $term-&amp;gt;name . '&quot; data-type=&quot;'. $taxonomy .'&quot; data-term-id=&quot;' . $term-&amp;gt;term_id . '&quot;&amp;gt;' . $term-&amp;gt;name . '&amp;lt;sup&amp;gt;['. $term-&amp;gt;count .']&amp;lt;/sup&amp;gt;&amp;lt;/a&amp;gt;';
    }
    return $term_links;
}</code></pre><p>调用方法:在loop中使用下面代码即可:</p>