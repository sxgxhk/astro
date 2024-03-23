---
title: 让TYPECHO评论头像旋转方法等
date: 2017-04-08 07:04:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/2456
categories: 
- 网站建设
tags: 
- typecho
---

<p>查找当前主题下的style.css。CSS文件根据主题自行选择可能名称不符。找到以下代码：</p><pre><code class="lang-css">#comments .comment-author .avatar{display:block;float:left;width:40px;height:40px;margin:1.4rem 1rem 0 0;border-radius:50%}</code></pre><p>修改为：</p><pre><code class="lang-css">#comments .comment-author .avatar{display:block;float:left;width:40px;height:40px;margin:1.4rem 1rem 0 0;border-radius:50%;transition: all 0.5s}
#comments .comment-author .avatar:hover{transform:rotate(360deg)}</code></pre><p>即可大功告成@(太开心)<br />具体演示效果，可参照本博客评论头像，如果你跟我一样使用Hran的主题，可以直接查找替换。</p><p><code> transition: all 0.5s </code>是表示旋转在0.5秒内完成，可自行修改速度<br /><code> transform: rotate(360deg) </code>表示图片旋转360度，可自行修改</p><p>到处逛博客圈，又发现好多好东西，赶紧收藏起来，感谢Destined博主的奉献！</p><h4>Typecho免插件实现博主认证</h4><p>打开<code> comments.php </code>，找到下面这条代码：</p><p>在后面加上如下代码：</p><h4>Typecho留言加上@</h4><ul><li>打开模板文件夹里的functions.php文件，添加以下代码:</li></ul><pre><code class="lang-php">/*评论增加@功能*/
function getPermalinkFromCoid($coid) {
$db       = Typecho_Db::get();
$options  = Typecho_Widget::widget('Widget_Options');
$contents = Typecho_Widget::widget('Widget_Abstract_Contents');
$row = $db-&gt;fetchRow($db-&gt;select('cid, type, author, text')-&gt;from('table.comments')
          -&gt;where('coid = ? AND status = ?', $coid, 'approved'));
if (empty($row)) return 'Comment not found!';
$cid = $row['cid'];
$select = $db-&gt;select('coid, parent')-&gt;from('table.comments')
          -&gt;where('cid = ? AND status = ?', $cid, 'approved')-&gt;order('coid');
if ($options-&gt;commentsShowCommentOnly)
    $select-&gt;where('type = ?', 'comment');
$comments = $db-&gt;fetchAll($select);
if ($options-&gt;commentsOrder == 'DESC')
    $comments = array_reverse($comments);
foreach ($comments as $key =&gt; $val)
    $array[$val['coid']] = $val['parent'];
$i = $coid;
while ($i != 0) {
    $break = $i;
    $i = $array[$i];
}
$count = 0;
foreach ($array as $key =&gt; $val) {
    if ($val == 0) $count++;
    if ($key == $break) break;
}
$parentContent = $contents-&gt;push($db-&gt;fetchRow($contents-&gt;select()-&gt;where('table.contents.cid = ?', $cid)));
$permalink = rtrim($parentContent['permalink'], '/');
$page = ($options-&gt;commentsPageBreak)
      ? '/comment-page-' . ceil($count / $options-&gt;commentsPageSize)
      : ( substr($permalink, -5, 5) == '.html' ? '' : '/' );
return array(
    &quot;author&quot; =&gt; $row['author'],
    &quot;text&quot; =&gt; $row['text'],
    &quot;href&quot; =&gt; &quot;{$permalink}{$page}#{$row['type']}-{$coid}&quot;
);
}  </code></pre><ul><li>然后打开你的<code> comment.php </code>文件，找到以下代码：</li></ul><p>在其前面加入如下代码：</p>